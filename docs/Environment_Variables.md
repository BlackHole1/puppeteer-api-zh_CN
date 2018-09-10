[📚 查看原文](//github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#environment-variables)

** 环境变量 **

Puppeteer 寻找某些环境变量来帮助其操作。 如果 puppeteer 在环境中没有找到它们，这些变量的小写变体将从 [npm 配置](https://docs.npmjs.com/cli/config) 中使用。

- `HTTP_PROXY`, `HTTPS_PROXY`, `NO_PROXY` - 定义用于下载和运行 Chromium 的 HTTP 代理设置。
- `PUPPETEER_SKIP_CHROMIUM_DOWNLOAD` - 请勿在安装步骤中下载绑定的 Chromium。
- `PUPPETEER_DOWNLOAD_HOST` - 覆盖用于下载 Chromium 的 URL 的主机部分。
- `PUPPETEER_CHROMIUM_REVISION` - 在安装步骤中指定一个你喜欢 puppeteer 使用的特定版本的 Chromium。

> **NOTE** PUPPETEER_* env variables are not accounted for in the [`puppeteer-core`](https://www.npmjs.com/package/puppeteer-core) package.