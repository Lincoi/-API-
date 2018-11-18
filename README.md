# -API-
阿里云API平台使用学习笔记
==================================
##一、使用说明：

  ECS API云服务器的调用：
    -（推荐）不同编程语言的云服务器 ECS SDK
    -阿里云 CLI
    -阿里云 API Explorer
    -API URL 请求
  
  实例相关接口Instance
      通过一些可以对实例进行操作
    
  启动模块相关接口Template
      在实例的基础上，对实例进行相关创建启动删除查询等操作
    
  磁盘相关接口Disk
      实例所需存储数据的磁盘
      
  镜像相关接口Image
      磁盘、自动快照策略、快照链
      
  网络相关接口
      为实例分配公网IP、转化实例的网路类型、将实例连接到VPC，使能实例和VPC中的云资源私网互通
     
  安全组相关接口SecurityGroup
      新建安全组、安全组出入方向规则的增删、将实例加入\移出指定安全组等操作
  
  部署集相关接口
  
  SSH密钥对相关接口
      对SSH密钥对的一些相关操作、对一或多台Linux实例绑定/接绑密钥对、查询删除等操作
      
  弹性网卡相关接口
  运维与监控相关接口 
  标签相关接口
  云助手相关接口
  地域相关接口
  
##基于 API URL 发起 HTTP/HTTPS GET 请求 （SDK免去此环节，免除手动签名验证环节）
  ###例：
    https://ecs.aliyuncs.com/?Action=CreateSnapshot
    &DiskId=1033-60053321
    &<公共请求参数>
  
      -https 指定了请求通信协议。
      -ecs.aliyuncs.com 指定了ECS的服务接入地址（Endpoint）。
      -Action=CreateSnapshot 指定了要调用的API，DiskId=1033-60053321 是  规定的参数。
      -<公共请求参数> 是系统规定的公共参数。
      通信协议
      接入地址
      ECS API 的服务接入地址
   
  ###签名机制
    步骤1.构造规范化请求字符串
    步骤2.构造签名字符串
    示例1.参数拼接法
    示例2.编程语言法
    
    对于每一次HTTP或者HTTPS协议请求，我们会根据访问中的签名信息验证访问请求者身份。具体由使用AccessKeyID和AccessKeySecret对称加密验证实现。
    AccessKey：相当于用户密码，用于调用API，而用户密码用于登陆ECS控制台
    AccessKeyID:访问者身份，AccessKeySecret是加密签名字符串和服务器端验证签名字符串的密钥，必须严格保密谨防泄露。
    
    1）步骤1.构造规范化请求字符串
        1.排序参数：排序规则以首字母顺序排序，排序参数包括  和接口自定义参数，不包括公共请求参数中的 Signature 参数
        2.编码参数：一些编码规则
        
    2）步骤2.构造签名字符串
         1.构造待签名字符串 StringToSign
            规则如下:StringToSign=                 
                       HTTPMethod + "&" + //HTTPMethod：发送请求的 HTTP 方法，例如 GET。
                       percentEncode("/") + "&" + //percentEncode("/")：字符（/）UTF-8 编码得到的值，即 %2F。
                       percentEncode(CanonicalizedQueryString) //您的规范化请求字符串。
    3）示例1.参数拼接法
          
    4）示例 2. 编程语言法

    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
  
  
  
  
  
