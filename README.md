# Overview

## Project introduction
This project uses a multiple page replacement strategy to implement a thread-safe cache:
- LRU: has not been used for the most recent time
- LFU: This parameter is not used frequently recently
- ARC: indicates adaptive replacement

For LRU and LFU policies, I have optimized their basic cache policies accordingly, such as:

- LRU optimization:
- LRU fragmentation: optimizes the performance of highly concurrent access in multithreading
- LRU-k: prevents hot data from being squeezed out of the container by cold data, which may cause cache contamination

- LFU optimization:
- LFU sharding: optimizes performance for high concurrent access in multithreading
- Introduction of the maximum average access frequency: solve the problem that the hotspot data in the past has not been accessed recently, but still occupies the cache

## System environment

Ubuntu 22.04 LTS

## Compile
Create a build folder and go to
```
mkdir build && cd build
```
Generate build file
```
cmake ..
```
Build project
```
make
```
If you want to clean the generated executable file
```
make clean
```

## Run
```
./main
```

## Test results
The cache hit ratio of different cache policies is compared as follows:
(ps: The test code only simulates the real access scenario as much as possible, but there is still a certain gap with the real scenario, and the test results are for reference only.)

! [alt text](images/image.png)
