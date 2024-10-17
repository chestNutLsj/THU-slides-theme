---
marp: true
theme: "gaia"
size: 16:9
paginate: "true"
footer: "Marp Theme for THU Presentation Slides by Lee Sen.J"
style: |
  section footer{color:blue;font-size:20px;}
---

<style scoped>
section h1 {
  text-align: center;
  font-size: 80px;
  color:black;
}
section p {
  text-align: left;
  font-size: 40px;
  color: black;
  margin-top: 35px;
}
section {
  background-image: url('../assets/fm.png');
  background-size: cover;
}
footer {
  color:black;
  font-size: 20px;
}
</style>

<!-- _class: lead gaia -->

# Marp Theme for THU Slides

**Paper:** ESync: Accelerating Intra-Domain Federated Learning in Heterogeneous Data Centers

**Reporter:** Lee Sen.J

**Date:** 17st / October / 2024

---

<style >
section{
  background-image: url('../assets/bg.png');
  background-size: cover;
  position: absolute;
}

section h2 {
  font-size: 50px;
  color: black;
  margin-top: 100px;
}

section h3{
  font-size: 35px;
  margin-top: 10px;
}

section h4{
  font-size: 30px;
  margin-top: 10px;
}

section p {
  font-size: 28px;
  color:black;
}

section table {
  text-align: center;
  font-size: 32px;
  color:black;
}

section a {
  font-size: 25px;
  color:black;
}

li {
  font-size: 27px;
  text-align: left;
}

img {
    margin-left: auto;
    margin-right:auto;
    display:block;
    margin:0 auto;
    width:25cm;
    }
</style>

<style scoped>
li {font-size: 40px;text-align: left;}
</style>

<!-- header: Outline -->

## Outline

1. Background and Related Works
2. Architecture Design
3. Modeling and Algorithm
4. Convergence Analysis
5. Experimental Evaluation
6. Conclusion and Future Work

---

<!--header: Background-->

## Background

### Today's Federated Learning

- How does FL proposed?
- Cross-device FL & Cross-Silo FL
- Noval FL scenarios: intra-domain FL in heterogeneous data centers
    - cross-device&cross-silo FL vs intra-domain FL
    - why we need new algorithms for intra-domain FL?

---

<!--header: Related Works-->

### Other algos' features

- Sync algos:
    - FedAvg:
    - SSGD:
- Async algos:
    - ASGD

---

<!--header: Goals-->

### Goals of Our work

- Coordinate the training of multiple devices in a heterogeneous data center.

---

<!--header: Architecture-->

## Architecture Design

### Overview

![w:15cm bg right](https://senjlearning.space/4-Scholar/1-Data-Center/Federated-Learning/assets/Esyncnotes-fig2-overview.png)

worker 在本地数据上对本地模型进行多次迭代训练，迭代次数由 State Server 自适应地协调，然后将更新推送到 Parameter Server 进行同步。Parameter Server 会对更新进行平均处理，并将平均后的更新同步给所有工作者。请注意，当 worker 数量较多时，可以使用多个 Parameter Server 来平衡流量负载。在这种情况下，每个 Parameter Server 管理不同部分的同步更新。

---

### State Server

如 Fig 3 所示，State Server 包含消息接收方、消息发送方、FIFO 消息队列、消息路由器、状态数据库、以及一系列消息管理者（掌管报告、重置、查询等职）。在实现中，基于 ZeroMQ 消息库构建了发送方和接收方。

---

### Message Format & Message Types

---

### State Database

---

<!--header: Algorithm -->

## Modeling and Algorithm

### Problem Modeling

The goal of this paper is to minimize (a) the global loss and (b) the blocking time.

---

### Algorithm Design

![](https://senjlearning.space/4-Scholar/1-Data-Center/Federated-Learning/assets/Esyncnotes-fig6-SSGD-Esync.png)

---

<!--header: Convergence-->

## Convergence Analysis

---

<!--header: Evaluation-->

## Experimental Evaluation

### Experimental Setup

---

### Numerical Results

#### ESync vs. Traditional DML

> We found simplicity to be a virtue as TIMELY evolved to Swift and removed some complexity, e.g., by **using the difference between the RTT and target delay rather than the RTT gradient**.


---

#### ESync vs. Cross-Silo FL Algorihtms

---

<!--header: Conclusion-->

## Conclusion and Future Work

---
