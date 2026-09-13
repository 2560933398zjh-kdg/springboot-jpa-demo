# boot-demo — Spring Boot 学习演示项目

基于 **Spring Boot + Spring Data JPA + MySQL** 的学生信息管理演示项目，用于学习 Spring Boot Web、JPA 数据访问与分层架构（Controller / Service / DAO）。

## 项目简介

- 定义学生实体 `Student`（id / name / email / age），对应数据库 `student` 表
- 使用 Spring Data JPA（`JpaRepository`）完成基础数据访问
- 提供 `/hello` 测试接口与标准 Spring Boot 工程结构（含 Maven Wrapper）

## 技术栈

- Java 17 + Spring Boot 4.0.5
- Spring Data JPA + MySQL（mysql-connector-j）
- Maven Wrapper（mvnw）

## 目录结构

```
boot-demo/
├── pom.xml                     # Maven 配置
├── mvnw / mvnw.cmd             # Maven Wrapper
├── HELP.md                     # Spring Initializr 生成说明
└── src/
    ├── main/
    │   ├── java/com/tutorial/boot_demo/
    │   │   ├── BootDemoApplication.java          # 启动类
    │   │   ├── TestController.java               # 测试接口（/hello）
    │   │   ├── dao/
    │   │   │   ├── Student.java                  # 学生实体（JPA）
    │   │   │   └── StudentRepository.java        # JPA 仓库接口
    │   │   └── service/
    │   │       ├── StudentService.java           # 业务接口
    │   │       └── StudentServiceImpl.java       # 业务实现
    │   └── resources/application.properties      # 应用配置
    └── test/java/com/tutorial/boot_demo/         # 单元测试
```

## 运行方式

```bash
# 使用 Maven Wrapper 启动（需本地 MySQL 并配置连接）
./mvnw spring-boot:run
```

## 备注

- 当前 `application.properties` 仅配置了应用名，数据库连接（MySQL 地址、账号密码）需自行补充。
- `StudentServiceImpl` 为空的骨架实现，CRUD 业务逻辑待完善，属于教学起点项目。
