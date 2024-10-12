# Introduction to Kafka Streams

Kafka Streams is a powerful stream-processing library built on top of Apache Kafka. It allows you to build real-time applications that process data streams with high throughput and low latency. Kafka Streams provides developers with an easy way to perform transformations, aggregations, joins, and more using a simple and declarative API.

## Key Concepts

### Streams and Tables
- **Streams** represent the unbounded sequence of data that is continuously received from Kafka topics.
- **Tables** represent the stateful storage of data, which can be materialized from streams by performing aggregations or joins.

### Stateless vs Stateful Processing
- **Stateless processing** refers to transformations that do not require any knowledge of past or future records. Common stateless operations include `map()`, `filter()`, and `flatMap()`.
- **Stateful processing** involves maintaining state across records, such as performing aggregations, joins, or windowed computations. The state is backed by Kafka’s internal changelog topics.

## Exactly-Once Semantics in Kafka Streams

Kafka Streams supports **exactly-once semantics (EOS)**, meaning that each record in a stream is processed exactly once, even in the case of failures. This is crucial for maintaining consistency in real-time applications. Kafka achieves EOS by tracking offsets and committing them atomically with the state updates.

To enable EOS, you can configure your application with:

```properties
processing.guarantee=exactly_once_v2

