📦 项目根目录
│  build.gradle                   # 全局Gradle构建配置
│  settings.gradle                # 子模块注册文件
├── 📂 gradle/wrapper             # Gradle版本控制
│       gradle-wrapper.properties 
├── 📂 common                     # [公共模块] 管理公共组件和依赖
│   │  build.gradle
│   └── com/nblg/message
│       ├── 📂 common             # 全局常量/工具类
│       └── 📂 module             # 公共实体类和Openfeign的Client
│           ├── 📂 auth           # 认证DTO/VO
│           ├── 📂 innerMessage   # 内部消息模型
│           ├── 📂 message        # 主业务模型
│           └── 📂 system         # 系统公共类，如统一返回实体类，统一错误码
├── 📂 gateway                    # [入口模块] API网关
│   │  build.gradle
│   │  Dockerfile
│   └── com/nblg/message
│       ├── 📂 common             # 网关过滤器
│       └── 📂 gateway
│           │  GateWayApplication.java
│           ├── 📂 config         # 路由配置
│           └── 📂 filter         # 过滤器链
├── 📂 auth                       # [核心模块] 认证服务
│   │  build.gradle               # 模块依赖配置
│   │  Dockerfile                 # 容器镜像构建
│   └── com/nblg/message
│       │  AuthApplication.java   # 启动类
│       ├── 📂 auth               # 认证业务代码
│       └── 📂 common             # 通用组件
│
└── 📂 message                    # [主模块] 业务实现
    │  build.gradle               # 模块依赖配置
    │  Dockerfile                 # 容器镜像构建
    ├── 📂 libs                   # 本地jar依赖
    └── com/nblg/message
        │  MessageApplication.java # 启动类
        ├── 📂 message            # 核心业务
        ├── 📂 innerMessage       # 内部消息服务
        └── 📂 common             # 通用组件
