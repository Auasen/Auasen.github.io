## 该平台于暑期小学期期间完成
志愿服务平台是一个用于为高校或其他机构提供志愿报名，志愿展示，志愿管理等功能的平台。该项目是一个前后端分离的支援管理系统。后端负责数据管理、业务逻辑处理和API接口提供，前端则负责用户界面展示和交互逻辑。这种架构模式有助于实现模块化开发，提高开发效率和系统可维护性。
<img width="1021" height="565" alt="Image" src="https://github.com/user-attachments/assets/24450ef8-f2dc-4f47-8446-3579ad1bc0cd" />
## **技术栈** 
**后端技术栈**
后端部分主要采用Java生态系统，具体技术栈如下：

- Spring Boot 3.2.3 : 作为核心后端框架，Spring Boot 提供了快速开发和部署的能力，简化了配置过程，使开发者能够专注于业务逻辑的实现。
- MySQL : 关系型数据库，用于存储博客文章、用户信息、评论等核心数据。其稳定性和可靠性使其成为数据持久化的常用选择。
- MyBatis-Plus 3.5.5 : 这是一个基于MyBatis的增强工具，极大地简化了数据库操作。它提供了强大的CRUD功能，减少了SQL语句的编写量，提高了开发效率。
- Spring Security : 安全框架，用于实现用户认证和授权功能，确保系统的安全性。它提供了灵活的配置选项，可以实现细粒度的权限控制。
- Lombok 1.18.30 : 一个Java库，通过注解自动生成样板代码（如getter、setter、构造函数等），从而使代码更加简洁和可读。
- Java 21 : 项目使用的Java版本，该版本带来了性能提升和新的语言特性。 

**前端技术栈**
前端部分主要采用Vue技术栈，具体如下：

- Vue 3.5.17 : 渐进式JavaScript框架，用于构建用户界面。其组合式API（Composition API）提供了更灵活的逻辑组织方式，增强了代码的复用性。
- Element Plus 2.10.2 : 一套基于Vue 3的桌面端UI组件库，提供了丰富的预构建组件，加速了前端界面的开发过程，并确保了界面的美观性和一致性。
- Vue Router 4.5.1 : Vue官方的路由管理器，用于实现单页应用（SPA）中的页面导航和路由管理。
- Vite 7.0.0 : 新一代前端构建工具，以其快速的开发服务器启动和热模块更新（HMR）能力，显著提升了前端开发效率。
- Axios 1.10.0 : 基于Promise的HTTP客户端，用于前端向后端发送HTTP请求，进行数据交互。
- xlsx 0.18.5 : 一个用于处理Excel文件的JavaScript库，可用于实现数据的导入导出功能。

## **平台展示**
首页
<img width="2549" height="1412" alt="Image" src="https://github.com/user-attachments/assets/61cf9833-40e9-483b-b8fc-fc523064f575" />
志愿风采：展示全校有记录的志愿时长考前的学生
<img width="2547" height="1350" alt="Image" src="https://github.com/user-attachments/assets/74874042-2a3d-4cda-b515-39e5218839c4" />
志愿时长：展示每个学院的学生时长
<img width="2553" height="1338" alt="Image" src="https://github.com/user-attachments/assets/a5802701-fbcc-4462-93f1-039cb0c6b777" />
志愿队伍：展示注册在案的志愿队伍
<img width="2559" height="1188" alt="Image" src="https://github.com/user-attachments/assets/0af9ecba-9f11-45f4-b7c0-88ed3633884d" />
志愿报名：进行志愿报名
<img width="2553" height="1193" alt="Image" src="https://github.com/user-attachments/assets/a7e07d18-f51e-4c07-8400-af497ab73b2c" />
志愿通知：查看报名详情
<img width="2556" height="1194" alt="Image" src="https://github.com/user-attachments/assets/5f971caf-667a-4300-8291-665ba1702a44" />
AI助手
<img width="897" height="684" alt="Image" src="https://github.com/user-attachments/assets/dae65e54-9f95-47b8-b96d-2dda7763f884" />

## **项目细节**
该项目的密码加密是在**后端**进行的，采用的是 **BCrypt 加密算法**。
具体来说：
- 在后端项目的`SecurityConfig.java` 文件中，配置了 `BCryptPasswordEncoder` 作为密码编码器。
- 在 `UserServiceImpl.java` 文件中，用户注册时通过 passwordEncoder.encode(password) 对密码进行加密存储，用户登录时则通过 passwordEncoder.matches(password, user.getPassword()) 来验证密码。
这意味着前端在用户输入密码后，会将明文密码发送到后端，由后端进行加密处理和存储，并在后续的认证过程中进行比对。
> [!NOTE]
> 经老师指点，这种在后端加密的方法并不是很安全，易被截获密码，导致账号安全问题，考虑将加密处理逻辑在前端执行。

# 值得学习的知识点
1. 前后端分离架构实践 : 深入理解前后端如何通过RESTful API进行通信，包括API设计原则、数据格式约定、跨域资源共享（CORS）处理以及认证机制的实现。
2. Spring Boot 3 的核心特性与生态 : 学习Spring Boot 3的新功能、配置方式以及如何集成Spring Data JPA、Spring AOP等其他Spring项目，以构建功能完善的企业级应用。
3. MyBatis-Plus 的高级用法 : 掌握MyBatis-Plus的条件构造器、代码生成器、分页插件等高级功能，以更高效地进行数据库操作和开发。
4. Vue 3 组合式API 的应用 : 深入理解Vue 3的组合式API，包括 ref 、 reactive 、 computed 、 watch 等，以及如何利用它们来组织可复用、可测试的组件逻辑。
5. Vite 的性能优势与配置 : 学习Vite的构建原理，掌握其开发服务器配置、插件系统以及生产环境打包优化策略，以实现更快的开发和部署。
6. Element Plus 组件库的定制与扩展 : 了解Element Plus的组件使用方法，并学习如何根据项目需求进行主题定制和组件扩展，以满足特定的UI/UX要求。
7. Spring Security 的安全机制 : 深入研究Spring Security的认证和授权流程，包括基于Token的认证（如JWT）、角色权限管理以及安全漏洞防范措施。