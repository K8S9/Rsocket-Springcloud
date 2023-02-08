# skyer技术中台 技术底座 Rsocket Spring Cloud微服务
### skyer技术中台 技术底座 spring cloud微服务

#### 介绍

    SKYER技术中台 技术底座 spring cloud微服务-面对市场快速的变化和越来越繁琐的开发任务，我们需要技术底座来管理服务并解决已有的技术难点还要避免重复造轮子。
    系统支持通用的服务包括多租户SAAS模式、工作流、文件管理、消息应用、报表管理、分布式调度、通用导入以及告警管理等。
    集成服务包括服务注册、能力接口注册、客户端注册、接口多级授权、计量计费、执行\健康监控、服务编排等。
    可应用于落地企业各种内部管理系统、各种2B&2C外部创新应用，研发各种工具与平台等
    针对不同应用场景，支持应用不同的基础设施，配合以不同的中间件，搭建可灵活伸缩(服务可合可分)的架构

#### 软件架构


软件架构说明 
![img](https://github.com/K8S9/Rsocket-Springcloud/blob/main/28ee1fc18a8f467f880c931d2697a760.png)

#### 功能介绍
 
##### 注册中心	
    基于Nacos/Eureka的平台注册中心服务，包括服务注册发现，服务健康检查，服务监控，注册中心其他功能

##### 网关		
    网关服务-SpringCloud Gateway+API鉴权，并预留鉴权拓展接口，  可根据实际情况自定义鉴权规则

##### 身份认证	
    身份认证oauth服务是基于 Spring Security、  Spring OAuth2、JWT 实现的统一认证服务中心，登录基于 spring security 的标准登录流程。           
    客户端授权支持 oauth2.0 的四种授权模式：授权码模式、简化模式、密码模式、客户端模式，授权流程跟标准的 oauth2 流程一致。
    web端采用简化模式(implicit)登录系统。
    移动端可使用密码模式(password)登录系统 。
    并支持基于Spring Social 的三方账号登录方式，如微信/QQ、支付宝、微博等，并提供拓展模式，支持更多三方渠道。

##### 身份权限管理		
    权限管理服务，平台统一的权限体系架构，用于管理角色、菜单、子账户等
![img](https://github.com/K8S9/Rsocket-Springcloud/blob/main/%E6%9D%83%E9%99%90%E4%BD%93%E7%B3%BB-%E6%95%B0%E6%8D%AE%E6%9D%83%E9%99%90%EF%BC%9A%E9%92%88%E5%AF%B9%E8%A7%92%E8%89%B2%E4%B8%8E%E7%94%A8%E6%88%B7%E7%9A%84%E6%9D%83%E9%99%90%E5%BA%94%E7%94%A8%EF%BC%88%E4%B8%9A%E5%8A%A1%E4%BA%BA%E5%91%98%EF%BC%89.png)
![img](https://github.com/K8S9/Rsocket-Springcloud/blob/main/%E6%9D%83%E9%99%90%E4%BD%93%E7%B3%BB-%E8%AE%BF%E9%97%AE%E6%9D%83%E9%99%90%EF%BC%9A%E5%9F%BA%E4%BA%8ERBAC%E7%9A%84%E6%9D%83%E9%99%90%E4%BD%93%E7%B3%BB.png)
![img](https://github.com/K8S9/Rsocket-Springcloud/blob/main/%E6%9D%83%E9%99%90%E4%BD%93%E7%B3%BB-%E8%AE%BF%E9%97%AE%E6%9D%83%E9%99%90%EF%BC%9A%E5%A4%9A%E7%BA%A7%E7%AE%A1%E7%90%86%E5%91%98.png)

##### 平台基础管理		
    基础功能服务，主要包含系统基础设置，如：租户管理、配置管理等；开发管理，如：值集、个性化、编码规则、配置维护、数据源管理等；

##### 平台治理		
    管理服务，基础服务之一，把路由、限流、熔断等功能易用化，集中在管理服务来管控，提供自动化的路由刷新、权限刷新、swagger信息刷新服务，提供界面化的服务、配置、路由、限流、熔断管理功能以及Spring Boot Admin控制台。

##### 配置中心		
    配置中心服务-Config；配置服务作为配置中心，为微服务体系中的其他服务提供配置存储、配置推送的服务。Spring Cloud提供了默认配置中心的实现，包含svn、git等几种实现，config则是基于数据库的实现，可以管理大数据量的配置，并且有  更快捷的配置推送方式。

##### 接口文档
    用于对平台开发测试的API文档进行管理以及接口调试。

##### 报表平台		
    报表服务-定制化报表；通过配置数据集，执行SQL或者查询URL，获取数据以渲染平面报表、单据报表、图形报表的服务

##### 分布式调度		
    分布式调度服务-Quartz服务端负责任务调度，任务的执行由执行器来完成。该服务具体包含执行器管理、并发任务管理、日志管理以及并发请求等。

##### 文件管理		
    提供简单易用的文件存储功能，具备对接多种云对象存储服务的能力且易于拓展，同时支持服务器ftp协议文件上传，支持大文件断点续传、文件预览、word在线编辑、pdf水印等。

##### 分布式事务	
    采用SAGA模型的分布式事务管理服务，保证事务一致性处理。

##### 消息管理		
    支持短信、邮箱、企业微信、钉钉、电话语音、Webhook、站内消息发送，并能够灵活管理消息模板和对接云平台支持的微服务。

##### 工作流		
    基于Activiti的工作流引擎服务,支持灵活的配置，搭建健全的业务审批管理流程;数据维护审批;申请、订单审批费用申请与报销,各类业务单据等
![img](https://github.com/K8S9/Rsocket-Springcloud/blob/main/%E5%B7%A5%E4%BD%9C%E6%B5%81.png)
![img](https://github.com/K8S9/Rsocket-Springcloud/blob/main/%E5%B7%A5%E4%BD%9C%E6%B5%81DEMO.png)
##### 通用数据导入		
    通用导入服务，支持Excel、csv数据导入。支持自定义渲染Excel模板，自定义数据校验，自定义数据导入。  Excel读取永远不会内存溢出

##### 审计服务		
    提供监控审计功能。监控包括服务监控、日志监控、调用链路追踪等监控功能。审计包括数据审计和操作审计

##### 全文检索应用		
    用于客制化管理ES的搜索功能，对ES中的索引创建更新、数据自定义查询、源数据接口同步、同步日志记录等功能进行可视化的管理，  使搜索变的配置性强，查询变的更加简单

##### 规则引擎		
    为系统提供动态计算业务规则的功能，  通过图形化的界面配置来配置计算流程，  能够在页面中动态调整配置应用到服务中的计算

##### 告警平台		
    提供处理报表数据集、消息队列等数据来源，  并能通过多种预警规则配置，产生告警信息，通过短信、电话语音、邮件等模式进行发送提醒。适用于业务数据监控，如合同到期预警、定时库存预警等场景。

##### 计费管理		
    计费服务为系统提供资源计费的功能，业务系统在计费服务中配置不同的计费规则，  使用计费规则规范业务资源的消费；计费服务可通过业务资源消费量和计费规则对业务资源进行计费、账单生成、账单支付、账单结果回调等一系列操作；计费服务还提供账户、账户充值等功能，用以支撑账单功能

##### 集成平台	
    外部能力集成、内部能力开放等功能，支持Rest、SOAP等多种格式转换，并可对接口进行全面监控、权限控制、接口映射等管理
![img](https://github.com/K8S9/Rsocket-Springcloud/blob/main/%E8%BF%9E%E6%8E%A5%E6%9C%8D%E5%8A%A1.png)
#### 特性

##### 云原生

    基于分布部署和统一运管，以分布式云，以容器、微服务、DevOps等技术为基础建立技术产品体系

![img](https://github.com/eeveek/oms/blob/main/front-end/%E4%BA%91%E5%8E%9F%E7%94%9F.png)

##### 开发

    集成GitLab的代码统一管理能力、支持多种类型的制品库管理能力、集成CI/CD的自动化流水线、内建的代码扫描与质量分析，全流程跟进开发过程

![img](https://github.com/eeveek/oms/blob/main/front-end/%E5%BC%80%E5%8F%91.png)

##### 部署

    包括集群管理、环境管理、资源管理，支持集群与环境的统一管理和集中分配，支持自动化部署流水线与一键式的手工部署，高效灵活地支撑产品运维

![img](https://github.com/eeveek/oms/blob/main/front-end/%E9%83%A8%E7%BD%B2.png)

##### 测试

    包括测试用例管理、测试计划管理、测试执行管理、缺陷管理、 测试报告管理，支持手工测试并提供API测试、性能测试、流量 回归测试、UI测试等自动化测试能力，测试任务还可嵌入开发流 水线，持续测试有效保障产品质量

![img](https://github.com/eeveek/oms/blob/main/front-end/%E6%B5%8B%E8%AF%95.png)

##### 技术支持

    轻松支持springcloud和Istio两种微服务模式，可以轻松为已部署的服务创建带来负载均衡、端到端的身份验证、监视等功能

![img](https://github.com/K8S9/Rsocket-Springcloud/blob/main/%E6%8A%80%E6%9C%AF%E6%94%AF%E6%8C%81.png)

#### 联系方式

![img](https://github.com/eeveek/oms/blob/main/front-end/we.png)  ![img](https://github.com/eeveek/oms/blob/main/front-end/gzh.png)


#### 特技

1.  使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2.  Gitee 官方博客 [blog.gitee.com](https://blog.gitee.com)
3.  你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解 Gitee 上的优秀开源项目
4.  [GVP](https://gitee.com/gvp) 全称是 Gitee 最有价值开源项目，是综合评定出的优秀开源项目
5.  Gitee 官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6.  Gitee 封面人物是一档用来展示 Gitee 会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)
