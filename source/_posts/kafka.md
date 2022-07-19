---
title: kafka producer consumer模型
tags:
---

## Kafka Topic & Producer & Consumer 模型

![20220511162842](https://cdn.jsdelivr.net/gh/jongrow/img/tech/设计模式/20220511162842.png)

1. topic 只有一个分区:
2. 每个(不同 groupId 的)consumer会 subscribe 全量数据

## Kafka Topic多partition & Producer & Consumer Group 模型

![20220511162904](https://cdn.jsdelivr.net/gh/jongrow/img/tech/设计模式/20220511162904.png)

1. topic 分为 p0~p3 4个分区
2. p0~p3 分区的所有message构成全量数据
3. 每个 consumer group都会消费全量数据
4. 同一个consumer group内的consumer被assign到不同的 partition, 他们不会处理相同的数据

## consumer offset:消息偏移量

offset 与 partition 一一对应：每个partition有自己独立的 offset 偏移量