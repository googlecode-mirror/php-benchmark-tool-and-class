A class and tool to facilitate easy benchmarking of php scripts

## Demo ##
http://www.rensebakker.com/projects/benchmark/?blocks=3

## Usage ##

### Instantiate the class ###
```
include('Benchmark.php');
$benchmark = new Benchmark();
```

### Start and end the benchmark ###
```
for($n=0;$n<1000;$n++){
	$benchmark->start();
	hash('md5', 'test');
	$benchmark->finish();
}
$hash_time = $benchmark->get_time();
$hash_mem = $benchmark->get_mem();
```

### Flush the object and start a new benchmark ###
```
$benchmark->flush();
for($n=0;$n<1000;$n++){
	$benchmark->start();
	md5('test');
	$benchmark->finish();
}
$md5_time = $benchmark->get_time();
$md5_mem = $benchmark->get_mem();
```