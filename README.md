# DouSql V3.0 - Burp Suite SQL注入检测插件

## 插件简介

基于Xia Sql 二次开发，感谢前辈铺路。
修复多个不足/bug，满足安全仔的日常渗透神器。

## 主要功能

### 核心检测功能
- **多种SQL注入检测**：支持报错注入、时间盲注、布尔盲注等多种检测方式
- **智能payload管理**：内置多种payload组，支持自定义payload配置
- **实时响应分析**：自动分析响应长度、时间、状态码等关键指标
- **报错信息识别**：可配置自定义报错关键字，精确识别SQL错误

### 高级配置选项
- **参数过滤系统**：支持白名单/黑名单模式，精确控制测试范围
- **URL黑名单过滤**：可配置黑名单URL，跳过不需要测试的路径
- **响应时间阈值**：可自定义时间盲注检测阈值
- **长度差异阈值**：可配置响应长度差异检测敏感度
- **HTTP方法过滤**：仅对GET/POST请求进行检测，提高效率

### 用户界面特性
- **双面板设计**：左侧显示扫描结果，右侧显示参数测试详情
- **实时状态更新**：支持报错标记(err)、时间超时标记(time)等状态显示
- **配置持久化**：所有配置自动保存，重启后自动恢复
- **跨平台兼容**：支持Windows、macOS、Linux等多种操作系统

### 工具集成
- **多工具支持**：支持从Scanner、Proxy、Repeater、Intruder发送请求
- **右键菜单集成**：可通过右键菜单快速发送请求到插件
- **监控模式**：支持实时监控Proxy和Repeater的流量

## 配置文件说明

插件配置文件统一存储在 `xia_sql_config/` 目录下：

- `xia_SQL_diy_payload.ini` - 默认payload配置
- `xia_SQL_payload_[组名].ini` - 自定义payload组配置
- `xia_SQL_diy_error.ini` - 自定义报错关键字
- `xia_SQL_response_time_threshold.ini` - 响应时间阈值配置
- `xia_SQL_length_diff_threshold.ini` - 长度差异阈值配置
- `xia_SQL_blacklist_urls.ini` - 黑名单URL配置
- `xia_SQL_whitelist.ini` - 白名单参数配置
- `xia_SQL_blacklist.ini` - 黑名单参数配置
- `xia_SQL_param_filter_mode.ini` - 参数过滤模式配置

## 使用方法

1. 将插件jar文件加载到Burp Suite
2. 在Extensions标签页中找到"xia SQL"插件
3. 配置相关检测参数和阈值
4. 通过右键菜单或监控模式发送请求进行检测
5. 查看扫描结果和参数测试详情

## 系统要求

- Burp Suite Professional 2024.6+
- Java 11+
- 支持Windows、macOS、Linux操作系统

## 开发环境

- Java版本：Java 11
- Burp Suite版本：2024.8.2
- 构建工具：Maven 3.x
- API框架：Montoya API (Burp Suite官方扩展API)

## 更新记录

### V3.0.0 (2025-12-25)
- 基于Montoya API重构，提升稳定性和兼容性
- 新增payload分组管理功能，支持多种测试场景
- 优化用户界面布局，改进左右分割面板设计
- 新增参数过滤系统，支持白名单/黑名单模式
- 新增黑名单URL过滤功能，支持通配符匹配
- 新增自定义报错信息检测功能
- 新增响应时间阈值和长度差异阈值配置
- 优化时间盲注检测逻辑，支持全payload类型时间检测
- 新增配置文件统一管理，所有配置持久化保存
- 修复跨平台兼容性问题，确保Windows/macOS下界面正常显示
- 新增HTTP方法过滤，仅检测GET/POST请求
- 优化错误检测优先级，报错信息优先于其他变化标记
- 新增状态栏时间超时标记，完善检测结果展示
- 修复多线程并发问题，提升插件稳定性



## 免责声明

本工具仅供安全测试和教育目的使用，使用者应遵守相关法律法规，不得用于非法用途。开发者不承担因误用本工具造成的任何责任。
