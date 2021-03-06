# Cross - 美诺福业务管理系统

## **基本概念**
### **用户**

用户是一个特定的系统使用者（可以是人或设备、软件系统等），具有一个面向系统的统一身份，而与用户对应的是一个（或多个）用户账户则是系统对该用户的身份认证方式。每一个用户账号与一组基于特定子系统的业务角色相对应，一个业务角色体现了职能组织中的一组业务职责与权限。如果一个用户账号无任何业务角色担当，则该用户账号为“游客”身份。用户可以是外部用户，更重要的场景则是内部员工。系统基础安全管控提供用户账号（包括内部员工和外部用户）注册，当系统上线HR子系统后，由HR通过用户注册接口自动完成内部员工用户的注册。

将用户统一身份同内部员工相关联使系统可以对员工进行统一评估。

注册新的用户账号时，用户向系统提供以下信息：
* 姓名
* 用户名 - 必需且唯一，账号登录标识
* 密码 - 6位以上数字和字母组合，不能是纯数字
* 内部员工 - 缺省为“是”
* 手机
* 头像
* 邮箱

系统创建用户账号成功后，返回“用户账号统一身份识别码”（可以二维码等形式展现），用户保存该识别码发送给业务主管用于业务角色权限分配。用户账号注册成功后，用户即可以该账号登录。

如果用户是在已有账号下注册新的用户账号，则系统将已有账号同新建账号通过统一身份相互关联。

用户可以在已有账号下随时修改当前账号信息，包括姓名、密码、手机、邮箱、头像等。如果当前账号为游客（未分配任何业务角色），则用户可以注销当前账号。

### **用户账号统一身份识别码**
用户账号统一身份识别码唯一标识了一个特定用户的一个特定账号（因为一个用户可以拥有多个账号），所有的业务角色分配均通过用户账号统一身份识别码向一个用户账号分配业务角色权限。

### **系统管理员**

系统管理员用于分配各子系统主管权限（子系统其它业务角色均由该子系统业务主管指定），而并不涉及任何具体的业务操作。其中，缺省系统管理员为系统预设的系统管理员，用于系统实际启用后指定首位系统管理员，一旦有系统管理员被指定，该缺省系统管理员将自动失效，系统将保持至少一位系统管理员。

系统管理员可以为系统中的每一个业务子系统指定一个用户账户为该业务子系统首位业务主管，业务主管被指定后，即可分配其它业务角色，并开展业务工作。

### **业务操作日志**
系统通过业务操作日志自动记录各种业务操作，以便跟踪用户操作和业务状态。业务操作日志的主要内容包括：    
  
  * 日期 - 
  * 操作人
    * 用户 -
    * 账号 -
    * 角色 -
  * 操作 -
    * 子系统 -
    * 操作类型
    * 说明

系统规定了各种业务角色可以订阅的操作类型，用户可以根据需要按其账号的业务角色订阅某些重点关注的业务操作类型，订阅后，系统将实时推送这类业务操作日志。


## **维保技术服务业务概要需求**

**维保技术服务系统总体目标** 致力于为客户提供细致、稳定、及时的仪器设备维护、保障及维修服务，在业务不断成长的同时努力降低营运成本、保障安全、提高整体效率。

**维保业务设置** 是对系统中维保相关业务的周期、工时等参数的配置，以便系统灵活地按需产生各种维保计划、计算工时、评估维保工程师绩效等。其主要内容包括：

* 业务类型 - 维保业务类型，如：巡检、点检、维护、维修等
* 参数类型 - 周期、工时等
* 设置 - 参数设置值

维保业务设置可以在设备类型、设备、维保设备层面进行配置，上层配置为下层配置提供缺省值。

### **维修技术部经理**

**维修技术部经理**是维保技术服务系统的业务主管（或区域业务分管），系统管理员将指定一个用户账户为首位维修技术部经理，其主要业务职责包括：

* 指定其他维修技术部经理，或回收其他（不包括自己）维修技术部经理权限
* 维护所有维保技术服务站基础资料
* 指定或替换维保技术服务站站长，或回收站长权限
* 分配或回收专业组组长角色权限
* 掌握、分析各维保技术服务站运营状态，完成其各项管理职责

维修技术部经理可以创建新的维保技术服务站，创建时向系统提供所建服务站的基本信息，主要包括：

* 名称 - 必需，维保技术服务站名称，唯一
* 缩写 - 可选
* 站长 - 指定一名站长

维修技术部经理可以随时修改维保技术服务站名称、缩写等基本信息，替换新的站长，或回收站长权限。

维修技术部经理可以指定一个或多个专业组长，或回收专业组长的业务权限。

### **专业组**

专业组负责提供专业技术信息，包括仪器设备技术规格、维保标准、维修技术指导、技术培训等。专业组分为专业组长、专业工程师两种业务角色，专业组长除含盖专业工程师的职责外，还具有技术审核的职责。

为了便于设备管理，统一各种设备的厂商信息，专业组需负责向系统提供并维护所有设备所涉及的生产厂商信息，内容包括：

  * 名称 - 生产厂商名称
  * 简称 - 简短名称


系统可以按预设设备类型设定业务参数，如点巡检及维修保养周期和工时缺省值等等。专业组成员负责向系统提供并维护所有预设设备类型，主要内容包括：
  * 名称 - 设备类型名称
  * 参数设置
    * 巡检周期 - 每年巡检次数，缺省值为每周一次 
    * 巡检工时 - 每次巡检所占工时 
    * 点检周期 - 每年点检次数，缺省值为每月一次
    * 点检工时 - 每次点检所占工时
    * 维护周期 - 每年维护保养次数，缺省值为每年2次
    * 维护工时 - 每次维护所占工时
    * 维修周期 - 每年维修次数，缺省值为每年2次
    * 维修工时 - 每次维修所占工时
  

专业组成员负责向系统提供并维护所有仪器设备基本信息、检测标准、点巡检周期、以及相关技术资料，包括：

  * 编号 - 可选，任何便于标识的统一编码
  * 名称 - 
  * 型号 - 设备厂商所给定的型号编码
  * 厂商 - 生产厂商，缺省为美诺福
  * 类型 - 设备类型
  * 等级 -
  * 检测标准
    * 项目 - 检测项目或检测部位表述
    * 标准 - 检测指标及其标准值或范围
    * 说明
  * 参数设置
    * 巡检周期 - 每年巡检次数，缺省值为设备类型中所设定的巡检周期（每周一次） 
    * 巡检工时 - 每次巡检所占工时，缺省值为设备类型中所设定的巡检工时 
    * 点检周期 - 每年点检次数，缺省值为设备类型中所设定的点检周期（每月一次）
    * 点检工时 - 每次点检所占工时，缺省值为设备类型中所设定的点检工时
    * 维护周期 - 每年维护保养次数，缺省值为设备类型中所设定的维护周期（每年2次）
    * 维护工时 - 每次维护所占工时，缺省值为设备类型中所设定的维护工时
    * 维修周期 - 每年维修次数，缺省值为设备类型中所设定的维修周期（每年2次）
    * 维修工时 - 每次维修所占工时，缺省值为设备类型中所设定的维修工时
  * 技术资料
    * 标题
    * 文档 - 任何可以上载的文档、多媒体文件等
    * 提供者
  * 状态 - 待审核、正常、停用
  * 标签 -
  * 图片 -
  * 备注 -
  
专业工程师对任何设备类型、设备的创建、修改均会被系统自动推送给专业组长进行审核，专业组长必须及时审核，超时未审核系统将自动审核通过。

所有技术信息的创建和修改均可以通过系统业务操作日志予以记录和消息发布，订阅者（如专业组成员、站长等）可以及时了解到技术动态。


### **站长**
站长首先需对本站维保工程师进行指定（用户授权），虽然站长可以随时收回已有的维保工程师的授权，但如果维保工程师尚有计划中待执行的维保任务，或维保工程师已被安排在一个作业区负责该作业区维保设备的维保工作时，则无法收回授权。

一个维保技术服务站可以服务多个客户公司，每一个客户公司可以设置多个作业区，每个作业区均包含一组维保设备。当将一名维保工程师安排至一个作业区时，缺省情况下系统将自动设置由该维保工程师负责该作业区所有维保设备的维保工作。当然，站长亦可以根据需要特别设定任何负责维保设备的维保工程师。

为了方便管理维保设备、维保工程师以及安排维保计划，站长可以根据需要维护和管理一组客户公司及其作业区信息：

* 服务公司名称
* 作业区 - 所有作业区列表
  * 名称 - 作业区名称
  * 维保工程师

站长需根据公司与客户签订的维保服务协议维护和管理本站所负责维保的所有仪器设备。这些维保设备必需是由专业组在系统中先行定义的，站长需仔细核对这些设备的基本信息，然后向系统提供该维保设备的主要信息包括：

* 设备 - 由专业组维护的设备规格定义，包含设备名称、型号、类型、等级、制造商、维保标准等等
* 序列号 - 特定设备唯一标识
* 所属公司
* 作业区
* 图片 - 该设备实地图片
* 负责人 - 负责该设备维保的维保工程师，缺省值为作业区维保工程师
* 创建日期
* 维保起始日期 - 自该日起编制维保计划

系统将为站长产生巡检、点检、维护、维修计划：巡检每周一次，点检每月一次，每年两次维护，每年两次维修。系统自动完成以下工作：

* 按维保计划每周向每一位维保工程师发布一次维保任务列表
* 每日统计每一位维保工程师本周进度，供站长、维修技术部经理查阅
* 计算维保工时
* 。。。。

站长可以随时对尚未执行的维保计划进行修订，特殊情况下可手动添加/取消维保任务，或临时更换执行者等。
系统可以为站长列出本周所有维保任务、维保设备、维保人员及其执行状态，及时了解本站工作状态和进度。
系统可以为站长列出当前正在进行的维保任务及维保工程师。

### **维保工程师**

系统根据维保计划按周为每一位维保工程师推送一批维保任务，维保工程师需在规定期限内完成系统分配的所有维保任务。
维保工程师在执行维保任务时系统将为其呈现以下内容：
* 服务公司 -
* 作业区 -
* 维保类型 - 巡检、点检、维护、维修
* 维保设备
  * 编号 - 可选，任何便于标识的统一编码
  * 名称 - 
  * 型号 - 设备厂商所给定的型号编码
  * 厂商 - 生产厂商，缺省为美诺福
  * 类型 - 设备类型
  * 等级 -
* 序列号
* 图片

维保工程师在执行点检或巡检任务时，根据以上系统给出的设备信息先核对确认被检设备，确认无误后向系统确认本次检测开始。系统将记录开始时间，并更新该检测任务状态为“检测中”，然后为维保工程师列出各项检测标准。维保工程师按检测标准逐项进行检测并记录检测值；最后维保工程师需对设备状态进行评价给出检测结果，然后向系统确认完成检测；系统逐项记录检测项的检测值，最后记录本次检测完成时间，并更新该检测任务状态为“已完成”。



### **问题**
* 在巡检时如果某个检测部位未达检测标准，这时检测人员作什么操作？
* 点巡检记录审核是何含义？ 是否需要专门审核？有审核不通过的情况？
* 安装地点同作业区有何区别？区分作业区和安装地点有何作用？
* 多个甲方单位拥有同种设备的情况是否普遍？同种设备是否具有相同的巡检和点检标准？
* 除了点检周期，点检计划的产生依据还有哪些？


## **附录一**

* 厂商 - 维保仪器设备的生产厂商
  - 编号
  - 名称

* 客户
  - 编号
  - 名称
  - 作业区
    - 作业区名称
  
* 设备类型 - 维保仪器设备的特定分类
  
* 设备 - 维保服务所涉及的仪器设备的类型及其规格定义
  
  - 名称 - 
  - 型号 - 设备厂商所给定的型号编码
  - 厂商 - 生产厂商，缺省为美诺福
  - 类型 - 设备类型
  - 编号 - 可选，任何便于标识的统一编码
  - 标签 
  - 图片
  - 备注
  
* 维保设备 - 由客户指定的需进行维保的仪器设备
  - 所属公司（客户）
  - 设备
  - 设备序列号
  - 作业区
  - 安装地点
  - 状态 - 草稿/启用/停用
  - 负责人
  - 权重（重要性）
  - 标签 
  - 图片
  - 备注
  
* 设备检修标准

* 维保技术服务站
  - 名称 - 必需，维保技术服务站名称，唯一
  - 缩写 - 可选
  - 站长 - 
  - 服务公司 - 服务公司名称
  - Logo
  - 创建人
  - 创建日期
  - 更新日志
    - 操作人
    - 更新日期
    - 操作
  

* 巡检
  - 期间 - 巡检开始和完成时间
    - 开始时间
    - 完成时间
  - 设备 - 本次巡检的设备
  - 检测明细
    - 检测部位
    - 检测值
    - 是否通过检测
  - 检测人
  - 审核 ？

