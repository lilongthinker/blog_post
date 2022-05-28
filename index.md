---
layout: default
---

## 关注的架构topic
* 高可用
  * 结构高可用 & 故障演练
  * 服务高可用 & 压力测试
  * 发布高可用
* Infrastructure As Code
  * 主要看terraform +  k8s 的组合 + k8s
* 可观测体系
  * metrics
  * tracing
  * logging，目前主要有发展的比较成熟的ELK（EFK）体系，以及
  * 结合方案
    * metrics & tracing -- 以metrics做为切入点
    * tracing & metrics, logging
    * logging & tracing
    * 关于拓扑数据的来源
      * 分析metrics信息来构建拓扑，典型的以kiali、aliyun arms Kubernetes 监控（基于对ebpf数据的分析） ps：相比普通的metrics信息，kiali的metics信息多一个client 信息  即一个方法的调用，按照不同的来源进行区分
      * 分析tracing信息来构建拓扑，典型的是对jaeger的tracing数据进行分析进而绘制拓扑
  * 看门狗机制 -- 没有问题的时候，发消息，保证告警机制是正常的。 -- 这个一般需要平台提供，而不要自己实现，比较消耗精力。
  * 除了针对系统的可观测体系以外，目前还在扩展外延，通过数字化来评估运维本身的响应速度-- MTTA、MTTR
* 微服务体系
  * 注册中心，非常的多，国内主要看nacos
  * 动态配置能力
  //* 负载均衡，框架需要支持
  * 可观测体系（包括日志）的构建 callback
  * 典型场景
    * 瞬时业务峰值，意料内的峰值-秒杀场景、意料之外的峰值-微博的热搜，如何保证系统的高可用
    * 中大规模微服务体系（部署不同镜像的应用个数在100以上）中
      * 如何构建低成本的多分支并行研发环境
      * 如何构建可运维的多套全链路灰度环境
    * 优雅上线 -- 尤其是Java应用的启动
    * 优雅下线 --
### 结构高可用
结构上的高可用基本都是基于冗余来构建的。
* 虚拟机打散
* 物理机打散 -- 部署集的概念
  * 方法一，k8s的worker使用物理机，部署在不同worker上的应用自然获得物理机打散效果
  * 方法二，使用ECS的情况，需要能够将ECS在物理机上打散（ECS、节点池支持部署集的概念）
* AZ打散 -- az信息的透传和打散策略，通AZ优先策略的支持
* Region打散 -- 即部署应用到不同的region.


[another page](./another-page.html)

[file](2022/05/06/first-blog.html)
