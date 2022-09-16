├─cn.xuelianyong.ddd.template <br/>
│    │<br/>
│    ├─ apis   API接口层<br/>
│    │    ├─model     视图模型,数据模型定义 vo/dto（大多数情況是一样的）<br/>
│    │    ├─assembler    装配器，实现模型转换eg. apiModel&#x3c;=> domainModel<br/>
│    │    └─controller   控制器，对外提供（Restful）接口<br/>
│    │
│    ├─application   应用层<br/>
│    │    ├─service  应用服务，非核心服务<br/>
│    │    ├─task     任务定义，协调领域模型<br/>
│    │    └─***      others<br/>
│    │
│    ├─domain   领域层<br/>
│    │    ├─common       公共代码抽取，限于领域层有效<br/>
│    │    ├─events       领域事件<br/>
│    │    ├─model        领域模型<br/>
│    │    │    ├─dict    领域划分的模块，可理解为子域划分<br/>
│    │    │    │    ├─DictVo.java       领域值对象<br/>
│    │    │    │    ├─DictEntity.java   领域实体，充血的领域模型，如本身的CRUD操作在此处<br/>
│    │    │    │    ├─DictAgg.java      领域聚合，通常表现为实体的聚合，需要有聚合根<br/>
│    │    │    │    └─DictService.java  领域服务，不能归与上述模型，如分页条件查询等可写在此处<br/>
│    │    │    ├─xxx<br/>
│    │    │    │    ├─xxxEntity.java<br/>
│    │    │    │    ├─bbbAgg.java<br/>
│    │    │    │    └─cccAgg.java<br/>
│    │    ├─service      领域服务类，一些不能归属某个具体领域模型的行为<br/>
│    │    └─factory      工厂类，负责复杂领域对象创建，封装细节<br/>
│    │<br/>
│    ├─infrastructure  基础设施层<br/>
│    │    ├─persistent   持久化机制<br/>
│    │    │    ├─po           持久化对象<br/>
│    │    │    └─repository   仓储类，持久化接口&实现，可与ORM映射框架结合<br/>
│    │    ├─general      通用技术支持，向其他层输出通用服务<br/>
│    │    │    ├─config       配置类<br/>
│    │    │    ├─toolkit      工具类<br/>
│    │    │    └─common       基础公共模块等<br/>
│    │<br/>
│    └─resources<br/>
│        ├─statics  静态资源<br/>
│        ├─template 系统页面<br/>
│        └─application.yml   全局配置文件<br/>