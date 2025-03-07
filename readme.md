# GO

use GVM to execute go program

```shell
go run main.go
```

# Python

execute the following command:

```shell
python main.py
```

# Rust

execute the following command:

```shell
cargo run
```


# WRK HTTP test tool

execute the following command to start benchmark test:

```shell
wrk -t12 -c1000 -d30s http://localhost:8080/
```


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