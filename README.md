# Warden Protocol 自动化日常任务机器人

## 项目简介
本项目是一个基于 Python 的 Warden Protocol 自动化日常任务机器人，支持多账户批量自动化、任务调度、断点续跑、数据库持久化等特性，适用于 Web3 用户日常签到、AI对话、游戏等自动化场景。

## 注意
本项目暂不开源，若怕有毒就别用

## 前置条件
- 注册：https://app.nstproxy.com/register?i=EE0Ije
- 创建频道后保存你的通道ID和密码，放到config.yaml文件中对应地方

## 功能特性
- 支持多账户批量自动化（私钥批量导入）
- 自动完成 Warden Protocol 的 CHAT_INTERACTION、GAME_PLAY、LOGIN 等日常任务
- 任务完成后自动调度，定时再次执行
- 支持万IP代理池，自动切换出口IP
- 任务状态、token、账户信息等自动持久化到 SQLite 数据库
- 支持断点续跑，token 有效时自动复用
- 彩色日志输出，账户进度清晰可见
- 配置文件化，所有参数集中管理


## 快速开始
### 1. 配置参数
- 编辑 `config.yaml`，填写代理、推荐码、私钥文件等参数（见下表）。
- 将所有私钥（0x开头）写入 `private.txt`，每行一个。

### 2. 运行脚本
```bash
warden_auto.exe
```

## 多账户与数据持久化
- 支持在 `private.txt` 中批量导入私钥，每行一个。
- 脚本会自动为每个私钥独立调度、独立持久化、独立代理。
- 所有账户信息、token、任务状态、下次执行时间等自动存储在 `warden_accounts.db`（SQLite）中。
- 支持断点续跑和多账户独立调度。

## 常见问题与注意事项
- **私钥安全**：请妥善保管私钥文件，勿泄露。
- **配置必填**：所有 config.yaml 字段必须填写，否则启动时报错。
- **依赖安装**：如遇依赖问题，优先升级 pip 并重装 requirements.txt。
- **日志查看**：终端日志为彩色输出，便于快速定位问题。

## License
MIT 
