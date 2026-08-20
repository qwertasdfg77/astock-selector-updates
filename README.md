# AStockSelector 更新源

这个仓库只作为 AStockSelector Android App 的更新服务器使用，不是源码仓库。

App 内“检测程序更新”会读取：

- `latest.json`
- `app-release.apk`：由源码仓库 Release 流程生成并使用正式证书签名。

`latest.json` 会指向当前可下载安装的 APK，并包含：

- `versionCode`
- `versionName`
- `apkUrl`
- `apkSha256`
- `apkSize`
- `releaseNotes`

源码仓库在这里：

- <https://github.com/qwertasdfg77/AStockSelector>

发布流程说明：

- 正常发布从源码仓库推送 `v*` tag 开始。
- GitHub Actions 会构建 APK、生成 GitHub Release，并自动更新本仓库的 APK 与 `latest.json`。
- 当前分支只保留正式签名的 `app-release.apk`，不提供 debug APK。
- 不建议手工修改本仓库文件，除非自动发布流程失败。
