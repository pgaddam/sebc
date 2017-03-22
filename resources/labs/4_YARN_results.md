* Parameters used for test
	*  Mappers = 4, 6, 8, 10
	*  Reducers = 1, 2, 3, 4
	*  Memory = 512, 1024
* Fastest Run

```
	Mappers: 10
	Reducers: 4
	mapreduce.map.memory.mb: 512
    
    Teragen:
	real	1m4.910s
	user	0m6.346s
	sys	0m0.316s

	Terasort:
	real	1m42.498s
	user	0m8.076s
	sys	0m0.367s
	
```

* Slowest Run

```
	Mappers: 4
	Reducers: 1
	mapreduce.map.memory.mb: 1024
	
	Teragen:
	real	1m7.916s
	user	0m6.344s
	sys	0m0.294s
	Terasort:
	real	2m30.615s
	user	0m8.147s
	sys	0m0.346s
```