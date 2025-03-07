# GO

use GVM to execute go program

```shell


wrk -t12 -c1000 -d30s http://localhost:8080/
Running 30s test @ http://localhost:8080/
  12 threads and 1000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    13.27ms    0.89ms  31.73ms   78.93%
    Req/Sec     6.26k   355.23     6.89k    94.19%
  2240958 requests in 30.01s, 277.83MB read
  Socket errors: connect 0, read 3436, write 0, timeout 0
Requests/sec:  74662.32
Transfer/sec:      9.26MB

wrk -t12 -c2000 -d30s http://localhost:8080/
Running 30s test @ http://localhost:8080/
  12 threads and 2000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    53.82ms   22.72ms 564.59ms   96.16%
    Req/Sec    56.30     62.47   303.00     87.01%
  10845 requests in 30.05s, 1.34MB read
  Socket errors: connect 0, read 557619, write 0, timeout 0
Requests/sec:    360.94
Transfer/sec:     45.82KB

wrk -t12 -c100 -d30s http://localhost:8080/
Running 30s test @ http://localhost:8080/
  12 threads and 100 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     1.24ms  364.70us  14.66ms   81.36%
    Req/Sec     6.47k   191.66     7.53k    74.56%
  2326384 requests in 30.10s, 288.42MB read
Requests/sec:  77286.72
Transfer/sec:      9.58MB 



# Rust

wrk -t12 -c1000 -d30s http://localhost:8080/
Running 30s test @ http://localhost:8080/
  12 threads and 1000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     5.16ms    2.10ms  35.09ms   74.93%
    Req/Sec    14.15k     1.30k   30.16k    82.82%
  5079541 requests in 30.10s, 431.14MB read
  Socket errors: connect 0, read 3406, write 0, timeout 0
Requests/sec: 168742.11
Transfer/sec:     14.32MB

wrk -t12 -c2000 -d30s http://localhost:8080/
Running 30s test @ http://localhost:8080/
  12 threads and 2000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    49.20ms   24.25ms 593.13ms   97.82%
    Req/Sec   120.37     92.31   363.00     62.80%
  16910 requests in 30.04s, 1.44MB read
  Socket errors: connect 0, read 608841, write 0, timeout 0
Requests/sec:    562.98
Transfer/sec:     48.93KB

wrk -t12 -c100 -d30s http://localhost:8080/
Running 30s test @ http://localhost:8080/
  12 threads and 100 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   584.44us   68.55us   4.98ms   92.74%
    Req/Sec    13.55k   249.64    15.35k    86.49%
  4869641 requests in 30.10s, 413.32MB read
Requests/sec: 161782.20
Transfer/sec:     13.73MB

# Python

wrk -t12 -c1000 -d30s http://localhost:8080/
Running 30s test @ http://localhost:8080/
  12 threads and 1000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    99.46ms    7.55ms 164.71ms   83.91%
    Req/Sec   834.12     55.81     1.19k    76.39%
  299572 requests in 30.10s, 43.43MB read
  Socket errors: connect 0, read 5886, write 8, timeout 0
Requests/sec:   9954.02
Transfer/sec:      1.44MB

wrk -t12 -c2000 -d30s http://localhost:8080/
Running 30s test @ http://localhost:8080/
  12 threads and 2000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   199.98ms   44.35ms 636.37ms   94.70%
    Req/Sec   823.77    155.35     1.20k    81.13%
  295583 requests in 30.10s, 42.85MB read
  Socket errors: connect 0, read 27456, write 0, timeout 0
Requests/sec:   9819.98
Transfer/sec:      1.42MB

wrk -t12 -c100 -d30s http://localhost:8080/
Running 30s test @ http://localhost:8080/
  12 threads and 100 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     9.34ms    0.96ms  23.92ms   88.58%
    Req/Sec     0.86k    58.30     2.14k    78.58%
  308933 requests in 30.09s, 44.78MB read
Requests/sec:  10265.84
Transfer/sec:      1.49MB


# Performance Comparison



| Language | Connections | Threads | Duration | Requests/sec | Transfer/sec | Latency (Avg) | Latency (Stdev) | Latency (Max) |
|----------|-------------|---------|----------|--------------|--------------|---------------|-----------------|---------------|
| Rust     | 100         | 12      | 30s      | 161782.20    | 13.73MB      | 584.44us      | 68.55us         | 4.98ms        |
| Go       | 100         | 12      | 30s      | 77286.72     | 9.58MB       | 1.24ms        | 364.70us        | 14.66ms       |
| Python   | 100         | 12      | 30s      | 10265.84     | 1.49MB       | 9.34ms        | 0.96ms          | 23.92ms       |
| Rust     | 1000        | 12      | 30s      | 168742.11    | 14.32MB      | 5.16ms        | 2.10ms          | 35.09ms       |
| Go       | 1000        | 12      | 30s      | 74662.32     | 9.26MB       | 13.27ms       | 0.89ms          | 31.73ms       |
| Python   | 1000        | 12      | 30s      | 9954.02      | 1.44MB       | 99.46ms       | 7.55ms          | 164.71ms      |
| Rust     | 2000        | 12      | 30s      | 562.98       | 48.93KB      | 49.20ms       | 24.25ms         | 593.13ms      |
| Go       | 2000        | 12      | 30s      | 360.94       | 45.82KB      | 53.82ms       | 22.72ms         | 564.59ms      |
| Python   | 2000        | 12      | 30s      | 9819.98      | 1.42MB       | 199.98ms      | 44.35ms         | 636.37ms      |