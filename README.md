# How the Selection of a Programming Language and Runtime Influences Resource and Electricity Consumption

**Author:** System7

## Abstract

This study explores how programming language and runtime selection can affect computational resource utilization and electricity consumption. By analyzing execution performance, CPU utilization, memory usage, and energy-related metrics, we aim to better understand the environmental and operational impact of software technology choices.

The research combines theoretical analysis with practical benchmarking, including comparisons between different programming languages and runtime environments such as Bun and Node.js.

---

# Analysis: Understanding the Context

Programming languages and runtime environments play a critical role in determining how efficiently software utilizes hardware resources. While developers often prioritize productivity, maintainability, and ecosystem support, resource consumption has become increasingly important due to growing concerns about energy efficiency, operating costs, and environmental sustainability.

This analysis examines:

- The evolution of programming languages and runtimes.
- Their influence on CPU and memory utilization.
- Performance implications across different workloads.
- Energy consumption and operational costs.
- Sustainability considerations in modern software engineering.

---

# State of the Art

Programming languages and runtime environments have evolved significantly over the past decades.

Early computing systems prioritized direct hardware access and execution efficiency through languages such as Assembly and C. Modern development has introduced higher-level languages and managed runtimes that improve developer productivity while introducing additional abstraction layers.

Recent advancements include:

- Just-In-Time (JIT) compilation.
- Advanced garbage collection techniques.
- Runtime optimizations.
- Native compilation approaches.
- Energy-aware computing strategies.

Emerging technologies continue to reshape the balance between performance, resource utilization, and developer experience.

---

# Hypothesis

Different programming languages and runtime environments exhibit measurable differences in resource consumption and energy efficiency.

By selecting technologies that execute workloads more efficiently, organizations may:

- Reduce CPU utilization.
- Lower electricity consumption.
- Decrease infrastructure costs.
- Improve environmental sustainability.

---

# Computing Resources

Before examining benchmark results, it is important to define the primary computing resources involved in program execution.

## Memory (RAM)

Memory stores the data and instructions required by a program during execution. Efficient memory management can significantly impact application performance and energy consumption.

## CPU (Central Processing Unit)

The CPU serves as the primary processing unit of a computer. It executes instructions, performs calculations, and manages data flow throughout the system.

Since CPU activity directly influences power consumption, it is the primary focus of this study.

---

# Exploration

## Programming Language Benchmark

A simple benchmark was implemented in multiple programming languages using the same algorithm:

```text
for (i = 0; i < 1,000,000,000; i++) {
    sum += 1;
}
```

The benchmark measured:

- Total execution time
- User CPU time
- System CPU time

Each implementation was executed 20 times.

The objective was to evaluate relative performance differences while keeping the workload identical across languages.

> Note: Results may vary depending on workload characteristics. Performance observed in this benchmark should not be generalized to all applications.

---

# Runtime Analysis: Bun vs Node.js

To further investigate runtime efficiency, benchmarking was conducted using Bun and Node.js servers running under identical conditions.

---

## Test Environment

### Hardware Specifications

| Component | Specification |
|------------|---------------|
| CPU | Intel Core i5-9400T @ 1.80 GHz |
| TDP | 35 W |
| Low Power State | 25 W |

Source:

- Intel ARK: https://ark.intel.com/content/www/us/en/ark/products/134893/intel-core-i5-9400t-processor-9m-cache-up-to-3-40-ghz.html

---

## Benchmark Methodology

Benchmarking was performed using `wrk`:

```bash
wrk -c 1000 -d 30s --latency http://redacted:5000
```

Configuration:

- 2 worker threads
- 1000 concurrent connections
- 30-second duration

Additional measurements were collected using system performance monitoring tools and CPU profiling.

---

# Bun Server Results

## CPU Utilization

| Metric | Value |
|----------|----------|
| Average | 46.1% |
| Maximum | 48.5% |
| Minimum | 45.9% |

## Performance

| Metric | Value |
|----------|------------|
| Latency (99th percentile) | 16.95 ms |
| Requests per Second | 105,757.97 |
| Transfer Rate | 12.00 MB/s |

## Energy Consumption

| Metric | Value |
|----------|----------|
| Daily Consumption | 0.4 kWh |
| Daily Cost | $0.124 |
| Annual Consumption | 132.1 kWh |
| Annual Cost | $45.33 |

---

# Node.js Server Results

## CPU Utilization

| Metric | Value |
|----------|----------|
| Average | 53.4% |
| Maximum | 60.4% |
| Minimum | 49.9% |

## Performance

| Metric | Value |
|----------|------------|
| Latency (99th percentile) | 55.22 ms |
| Requests per Second | 22,338.60 |
| Transfer Rate | 3.43 MB/s |

## Energy Consumption

| Metric | Value |
|----------|----------|
| Daily Consumption | 0.4 kWh |
| Daily Cost | $0.154 |
| Annual Consumption | 163.7 kWh |
| Annual Cost | $56.16 |

---

# Results and Discussion

The benchmark results demonstrate measurable differences between runtime environments operating under identical hardware conditions.

Key observations include:

- Bun achieved substantially higher throughput.
- Bun exhibited lower latency.
- Bun required less average CPU utilization.
- Node.js consumed more CPU resources while delivering lower throughput.
- Operational costs differed despite similar workload conditions.

These findings suggest that runtime selection can influence both performance efficiency and long-term infrastructure costs.

However, it is important to acknowledge that:

- Different workloads may produce different results.
- Ecosystem maturity remains an important consideration.
- Performance is only one factor in technology selection.
- Maintainability and developer productivity must also be evaluated.

---

# Conclusion

This study highlights the impact that programming language and runtime choices can have on resource utilization and energy consumption.

### Bun

- Average CPU usage: **46.1%**
- Latency (99th percentile): **16.95 ms**
- Throughput: **105,757.97 requests/sec**
- Annual energy consumption: **132.1 kWh**
- Annual operating cost: **$45.33**

### Node.js

- Average CPU usage: **53.4%**
- Latency (99th percentile): **55.22 ms**
- Throughput: **22,338.60 requests/sec**
- Annual energy consumption: **163.7 kWh**
- Annual operating cost: **$56.16**

Under the tested conditions, Bun demonstrated superior throughput and lower CPU utilization compared to Node.js.

The results emphasize the importance of considering not only developer experience and ecosystem support, but also performance efficiency, infrastructure costs, and environmental impact when selecting software technologies.

---

# Future Work

Future research could expand this study by:

- Testing additional programming languages.
- Comparing more runtime environments.
- Measuring memory consumption in greater detail.
- Evaluating real-world application workloads.
- Conducting long-term energy monitoring.
- Investigating carbon footprint implications across cloud providers.

Such research would contribute to a deeper understanding of sustainable software engineering practices.

---

# References

1. Intel ARK – Intel Core i5-9400T Processor  
   https://ark.intel.com/content/www/us/en/ark/products/134893/intel-core-i5-9400t-processor-9m-cache-up-to-3-40-ghz.html

2. Global Petrol Prices – Electricity Prices in Switzerland  
   https://www.globalpetrolprices.com/Switzerland/electricity_prices/
