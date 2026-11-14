# miniblog-packages

Mini Blog 的发版验证包源（GitHub Releases）。

- `v1.0.0` / `v1.1.0`：demo 插件包（slug=demo），由 `tools/sign-package.php` 生成
  SHA-256 完整性清单 + HMAC-SHA256 签名（演示密钥 `gh-remote-update-verify-secret`）。
- 消费方式：`php tools/remote-update.php` —— 从本仓库 Releases 下载资产，
  落到隔离站点 `storage/updates/` 暂存区内（满足 `PackageVerifier::assertSource`
  的站点根目录边界），经 `lifecycle.install / upgrade / rollback` 实跑升级与回滚。
