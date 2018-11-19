# Puppeteer API <!-- GEN:version -->Tip-Of-Tree<!-- GEN:stop-->

<!-- GEN:empty-if-release -->
> Next Release: **Nov 29, 2018**
<!-- GEN:stop -->
- API Translations: [中文|Chinese](https://zhaoqize.github.io/puppeteer-api-zh_CN/#/)
- Releases per Chromium Version:
  * Chromium 72.0.3582.0 - [Puppeteer v1.10.0](https://github.com/GoogleChrome/puppeteer/blob/v1.10.0/docs/api.md)
  * Chromium 71.0.3563.0 - [Puppeteer v1.9.0](https://github.com/GoogleChrome/puppeteer/blob/v1.9.0/docs/api.md)
  * Chromium 70.0.3508.0 - [Puppeteer v1.7.0](https://github.com/GoogleChrome/puppeteer/blob/v1.7.0/docs/api.md)
  * Chromium 69.0.3494.0 - [Puppeteer v1.6.2](https://github.com/GoogleChrome/puppeteer/blob/v1.6.2/docs/api.md)
  * Chromium 68.0.3419.0 - [Puppeteer v1.4.0](https://github.com/GoogleChrome/puppeteer/blob/v1.4.0/docs/api.md)
  * Chromium 67.0.3392.0 - [Puppeteer v1.3.0](https://github.com/GoogleChrome/puppeteer/blob/v1.3.0/docs/api.md)
  * [All releases](https://github.com/GoogleChrome/puppeteer/releases)


##### Table of Contents

<!-- GEN:toc -->
- [Overview](#overview)
- [puppeteer vs puppeteer-core](#puppeteer-vs-puppeteer-core)
- [Environment Variables](#environment-variables)
- [Error handling](#error-handling)
- [Working with Chrome Extensions](#working-with-chrome-extensions)
- [class: Puppeteer](#class-puppeteer)
  * [puppeteer.connect(options)](#puppeteerconnectoptions)
  * [puppeteer.createBrowserFetcher([options])](#puppeteercreatebrowserfetcheroptions)
  * [puppeteer.defaultArgs([options])](#puppeteerdefaultargsoptions)
  * [puppeteer.executablePath()](#puppeteerexecutablepath)
  * [puppeteer.launch([options])](#puppeteerlaunchoptions)
- [class: BrowserFetcher](#class-browserfetcher)
  * [browserFetcher.canDownload(revision)](#browserfetchercandownloadrevision)
  * [browserFetcher.download(revision[, progressCallback])](#browserfetcherdownloadrevision-progresscallback)
  * [browserFetcher.localRevisions()](#browserfetcherlocalrevisions)
  * [browserFetcher.platform()](#browserfetcherplatform)
  * [browserFetcher.remove(revision)](#browserfetcherremoverevision)
  * [browserFetcher.revisionInfo(revision)](#browserfetcherrevisioninforevision)
- [class: Browser](#class-browser)
  * [event: 'disconnected'](#event-disconnected)
  * [event: 'targetchanged'](#event-targetchanged)
  * [event: 'targetcreated'](#event-targetcreated)
  * [event: 'targetdestroyed'](#event-targetdestroyed)
  * [browser.browserContexts()](#browserbrowsercontexts)
  * [browser.close()](#browserclose)
  * [browser.createIncognitoBrowserContext()](#browsercreateincognitobrowsercontext)
  * [browser.defaultBrowserContext()](#browserdefaultbrowsercontext)
  * [browser.disconnect()](#browserdisconnect)
  * [browser.newPage()](#browsernewpage)
  * [browser.pages()](#browserpages)
  * [browser.process()](#browserprocess)
  * [browser.target()](#browsertarget)
  * [browser.targets()](#browsertargets)
  * [browser.userAgent()](#browseruseragent)
  * [browser.version()](#browserversion)
  * [browser.waitForTarget(predicate[, options])](#browserwaitfortargetpredicate-options)
  * [browser.wsEndpoint()](#browserwsendpoint)
- [class: BrowserContext](#class-browsercontext)
  * [event: 'targetchanged'](#event-targetchanged-1)
  * [event: 'targetcreated'](#event-targetcreated-1)
  * [event: 'targetdestroyed'](#event-targetdestroyed-1)
  * [browserContext.browser()](#browsercontextbrowser)
  * [browserContext.clearPermissionOverrides()](#browsercontextclearpermissionoverrides)
  * [browserContext.close()](#browsercontextclose)
  * [browserContext.isIncognito()](#browsercontextisincognito)
  * [browserContext.newPage()](#browsercontextnewpage)
  * [browserContext.overridePermissions(origin, permissions)](#browsercontextoverridepermissionsorigin-permissions)
  * [browserContext.pages()](#browsercontextpages)
  * [browserContext.targets()](#browsercontexttargets)
  * [browserContext.waitForTarget(predicate[, options])](#browsercontextwaitfortargetpredicate-options)
- [class: Page](#class-page)
  * [event: 'close'](#event-close)
  * [event: 'console'](#event-console)
  * [event: 'dialog'](#event-dialog)
  * [event: 'domcontentloaded'](#event-domcontentloaded)
  * [event: 'error'](#event-error)
  * [event: 'frameattached'](#event-frameattached)
  * [event: 'framedetached'](#event-framedetached)
  * [event: 'framenavigated'](#event-framenavigated)
  * [event: 'load'](#event-load)
  * [event: 'metrics'](#event-metrics)
  * [event: 'pageerror'](#event-pageerror)
  * [event: 'request'](#event-request)
  * [event: 'requestfailed'](#event-requestfailed)
  * [event: 'requestfinished'](#event-requestfinished)
  * [event: 'response'](#event-response)
  * [event: 'workercreated'](#event-workercreated)
  * [event: 'workerdestroyed'](#event-workerdestroyed)
  * [page.$(selector)](#pageselector)
  * [page.$$(selector)](#pageselector-1)
  * [page.$$eval(selector, pageFunction[, ...args])](#pageevalselector-pagefunction-args)
  * [page.$eval(selector, pageFunction[, ...args])](#pageevalselector-pagefunction-args-1)
  * [page.$x(expression)](#pagexexpression)
  * [page.accessibility](#pageaccessibility)
  * [page.addScriptTag(options)](#pageaddscripttagoptions)
  * [page.addStyleTag(options)](#pageaddstyletagoptions)
  * [page.authenticate(credentials)](#pageauthenticatecredentials)
  * [page.bringToFront()](#pagebringtofront)
  * [page.browser()](#pagebrowser)
  * [page.click(selector[, options])](#pageclickselector-options)
  * [page.close(options)](#pagecloseoptions)
  * [page.content()](#pagecontent)
  * [page.cookies(...urls)](#pagecookiesurls)
  * [page.coverage](#pagecoverage)
  * [page.deleteCookie(...cookies)](#pagedeletecookiecookies)
  * [page.emulate(options)](#pageemulateoptions)
  * [page.emulateMedia(mediaType)](#pageemulatemediamediatype)
  * [page.evaluate(pageFunction, ...args)](#pageevaluatepagefunction-args)
  * [page.evaluateHandle(pageFunction, ...args)](#pageevaluatehandlepagefunction-args)
  * [page.evaluateOnNewDocument(pageFunction, ...args)](#pageevaluateonnewdocumentpagefunction-args)
  * [page.exposeFunction(name, puppeteerFunction)](#pageexposefunctionname-puppeteerfunction)
  * [page.focus(selector)](#pagefocusselector)
  * [page.frames()](#pageframes)
  * [page.goBack(options)](#pagegobackoptions)
  * [page.goForward(options)](#pagegoforwardoptions)
  * [page.goto(url, options)](#pagegotourl-options)
  * [page.hover(selector)](#pagehoverselector)
  * [page.isClosed()](#pageisclosed)
  * [page.keyboard](#pagekeyboard)
  * [page.mainFrame()](#pagemainframe)
  * [page.metrics()](#pagemetrics)
  * [page.mouse](#pagemouse)
  * [page.pdf(options)](#pagepdfoptions)
  * [page.queryObjects(prototypeHandle)](#pagequeryobjectsprototypehandle)
  * [page.reload(options)](#pagereloadoptions)
  * [page.screenshot([options])](#pagescreenshotoptions)
  * [page.select(selector, ...values)](#pageselectselector-values)
  * [page.setBypassCSP(enabled)](#pagesetbypasscspenabled)
  * [page.setCacheEnabled(enabled)](#pagesetcacheenabledenabled)
  * [page.setContent(html)](#pagesetcontenthtml)
  * [page.setCookie(...cookies)](#pagesetcookiecookies)
  * [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout)
  * [page.setExtraHTTPHeaders(headers)](#pagesetextrahttpheadersheaders)
  * [page.setGeolocation(options)](#pagesetgeolocationoptions)
  * [page.setJavaScriptEnabled(enabled)](#pagesetjavascriptenabledenabled)
  * [page.setOfflineMode(enabled)](#pagesetofflinemodeenabled)
  * [page.setRequestInterception(value)](#pagesetrequestinterceptionvalue)
  * [page.setUserAgent(userAgent)](#pagesetuseragentuseragent)
  * [page.setViewport(viewport)](#pagesetviewportviewport)
  * [page.tap(selector)](#pagetapselector)
  * [page.target()](#pagetarget)
  * [page.title()](#pagetitle)
  * [page.touchscreen](#pagetouchscreen)
  * [page.tracing](#pagetracing)
  * [page.type(selector, text[, options])](#pagetypeselector-text-options)
  * [page.url()](#pageurl)
  * [page.viewport()](#pageviewport)
  * [page.waitFor(selectorOrFunctionOrTimeout[, options[, ...args]])](#pagewaitforselectororfunctionortimeout-options-args)
  * [page.waitForFunction(pageFunction[, options[, ...args]])](#pagewaitforfunctionpagefunction-options-args)
  * [page.waitForNavigation(options)](#pagewaitfornavigationoptions)
  * [page.waitForRequest(urlOrPredicate, options)](#pagewaitforrequesturlorpredicate-options)
  * [page.waitForResponse(urlOrPredicate, options)](#pagewaitforresponseurlorpredicate-options)
  * [page.waitForSelector(selector[, options])](#pagewaitforselectorselector-options)
  * [page.waitForXPath(xpath[, options])](#pagewaitforxpathxpath-options)
  * [page.workers()](#pageworkers)
- [class: Worker](#class-worker)
  * [worker.evaluate(pageFunction, ...args)](#workerevaluatepagefunction-args)
  * [worker.evaluateHandle(pageFunction, ...args)](#workerevaluatehandlepagefunction-args)
  * [worker.executionContext()](#workerexecutioncontext)
  * [worker.url()](#workerurl)
- [class: Accessibility](#class-accessibility)
  * [accessibility.snapshot([options])](#accessibilitysnapshotoptions)
- [class: Keyboard](#class-keyboard)
  * [keyboard.down(key[, options])](#keyboarddownkey-options)
  * [keyboard.press(key[, options])](#keyboardpresskey-options)
  * [keyboard.sendCharacter(char)](#keyboardsendcharacterchar)
  * [keyboard.type(text, options)](#keyboardtypetext-options)
  * [keyboard.up(key)](#keyboardupkey)
- [class: Mouse](#class-mouse)
  * [mouse.click(x, y, [options])](#mouseclickx-y-options)
  * [mouse.down([options])](#mousedownoptions)
  * [mouse.move(x, y, [options])](#mousemovex-y-options)
  * [mouse.up([options])](#mouseupoptions)
- [class: Touchscreen](#class-touchscreen)
  * [touchscreen.tap(x, y)](#touchscreentapx-y)
- [class: Tracing](#class-tracing)
  * [tracing.start(options)](#tracingstartoptions)
  * [tracing.stop()](#tracingstop)
- [class: Dialog](#class-dialog)
  * [dialog.accept([promptText])](#dialogacceptprompttext)
  * [dialog.defaultValue()](#dialogdefaultvalue)
  * [dialog.dismiss()](#dialogdismiss)
  * [dialog.message()](#dialogmessage)
  * [dialog.type()](#dialogtype)
- [class: ConsoleMessage](#class-consolemessage)
  * [consoleMessage.args()](#consolemessageargs)
  * [consoleMessage.text()](#consolemessagetext)
  * [consoleMessage.type()](#consolemessagetype)
- [class: Frame](#class-frame)
  * [frame.$(selector)](#frameselector)
  * [frame.$$(selector)](#frameselector-1)
  * [frame.$$eval(selector, pageFunction[, ...args])](#frameevalselector-pagefunction-args)
  * [frame.$eval(selector, pageFunction[, ...args])](#frameevalselector-pagefunction-args-1)
  * [frame.$x(expression)](#framexexpression)
  * [frame.addScriptTag(options)](#frameaddscripttagoptions)
  * [frame.addStyleTag(options)](#frameaddstyletagoptions)
  * [frame.childFrames()](#framechildframes)
  * [frame.click(selector[, options])](#frameclickselector-options)
  * [frame.content()](#framecontent)
  * [frame.evaluate(pageFunction, ...args)](#frameevaluatepagefunction-args)
  * [frame.evaluateHandle(pageFunction, ...args)](#frameevaluatehandlepagefunction-args)
  * [frame.executionContext()](#frameexecutioncontext)
  * [frame.focus(selector)](#framefocusselector)
  * [frame.goto(url, options)](#framegotourl-options)
  * [frame.hover(selector)](#framehoverselector)
  * [frame.isDetached()](#frameisdetached)
  * [frame.name()](#framename)
  * [frame.parentFrame()](#frameparentframe)
  * [frame.select(selector, ...values)](#frameselectselector-values)
  * [frame.setContent(html)](#framesetcontenthtml)
  * [frame.tap(selector)](#frametapselector)
  * [frame.title()](#frametitle)
  * [frame.type(selector, text[, options])](#frametypeselector-text-options)
  * [frame.url()](#frameurl)
  * [frame.waitFor(selectorOrFunctionOrTimeout[, options[, ...args]])](#framewaitforselectororfunctionortimeout-options-args)
  * [frame.waitForFunction(pageFunction[, options[, ...args]])](#framewaitforfunctionpagefunction-options-args)
  * [frame.waitForNavigation(options)](#framewaitfornavigationoptions)
  * [frame.waitForSelector(selector[, options])](#framewaitforselectorselector-options)
  * [frame.waitForXPath(xpath[, options])](#framewaitforxpathxpath-options)
- [class: ExecutionContext](#class-executioncontext)
  * [executionContext.evaluate(pageFunction, ...args)](#executioncontextevaluatepagefunction-args)
  * [executionContext.evaluateHandle(pageFunction, ...args)](#executioncontextevaluatehandlepagefunction-args)
  * [executionContext.frame()](#executioncontextframe)
  * [executionContext.queryObjects(prototypeHandle)](#executioncontextqueryobjectsprototypehandle)
- [class: JSHandle](#class-jshandle)
  * [jsHandle.asElement()](#jshandleaselement)
  * [jsHandle.dispose()](#jshandledispose)
  * [jsHandle.executionContext()](#jshandleexecutioncontext)
  * [jsHandle.getProperties()](#jshandlegetproperties)
  * [jsHandle.getProperty(propertyName)](#jshandlegetpropertypropertyname)
  * [jsHandle.jsonValue()](#jshandlejsonvalue)
- [class: ElementHandle](#class-elementhandle)
  * [elementHandle.$(selector)](#elementhandleselector)
  * [elementHandle.$$(selector)](#elementhandleselector-1)
  * [elementHandle.$$eval(selector, pageFunction, ...args)](#elementhandleevalselector-pagefunction-args)
  * [elementHandle.$eval(selector, pageFunction, ...args)](#elementhandleevalselector-pagefunction-args-1)
  * [elementHandle.$x(expression)](#elementhandlexexpression)
  * [elementHandle.asElement()](#elementhandleaselement)
  * [elementHandle.boundingBox()](#elementhandleboundingbox)
  * [elementHandle.boxModel()](#elementhandleboxmodel)
  * [elementHandle.click([options])](#elementhandleclickoptions)
  * [elementHandle.contentFrame()](#elementhandlecontentframe)
  * [elementHandle.dispose()](#elementhandledispose)
  * [elementHandle.executionContext()](#elementhandleexecutioncontext)
  * [elementHandle.focus()](#elementhandlefocus)
  * [elementHandle.getProperties()](#elementhandlegetproperties)
  * [elementHandle.getProperty(propertyName)](#elementhandlegetpropertypropertyname)
  * [elementHandle.hover()](#elementhandlehover)
  * [elementHandle.isIntersectingViewport()](#elementhandleisintersectingviewport)
  * [elementHandle.jsonValue()](#elementhandlejsonvalue)
  * [elementHandle.press(key[, options])](#elementhandlepresskey-options)
  * [elementHandle.screenshot([options])](#elementhandlescreenshotoptions)
  * [elementHandle.tap()](#elementhandletap)
  * [elementHandle.toString()](#elementhandletostring)
  * [elementHandle.type(text[, options])](#elementhandletypetext-options)
  * [elementHandle.uploadFile(...filePaths)](#elementhandleuploadfilefilepaths)
- [class: Request](#class-request)
  * [request.abort([errorCode])](#requestaborterrorcode)
  * [request.continue([overrides])](#requestcontinueoverrides)
  * [request.failure()](#requestfailure)
  * [request.frame()](#requestframe)
  * [request.headers()](#requestheaders)
  * [request.isNavigationRequest()](#requestisnavigationrequest)
  * [request.method()](#requestmethod)
  * [request.postData()](#requestpostdata)
  * [request.redirectChain()](#requestredirectchain)
  * [request.resourceType()](#requestresourcetype)
  * [request.respond(response)](#requestrespondresponse)
  * [request.response()](#requestresponse)
  * [request.url()](#requesturl)
- [class: Response](#class-response)
  * [response.buffer()](#responsebuffer)
  * [response.frame()](#responseframe)
  * [response.fromCache()](#responsefromcache)
  * [response.fromServiceWorker()](#responsefromserviceworker)
  * [response.headers()](#responseheaders)
  * [response.json()](#responsejson)
  * [response.ok()](#responseok)
  * [response.remoteAddress()](#responseremoteaddress)
  * [response.request()](#responserequest)
  * [response.securityDetails()](#responsesecuritydetails)
  * [response.status()](#responsestatus)
  * [response.statusText()](#responsestatustext)
  * [response.text()](#responsetext)
  * [response.url()](#responseurl)
- [class: SecurityDetails](#class-securitydetails)
  * [securityDetails.issuer()](#securitydetailsissuer)
  * [securityDetails.protocol()](#securitydetailsprotocol)
  * [securityDetails.subjectName()](#securitydetailssubjectname)
  * [securityDetails.validFrom()](#securitydetailsvalidfrom)
  * [securityDetails.validTo()](#securitydetailsvalidto)
- [class: Target](#class-target)
  * [target.browser()](#targetbrowser)
  * [target.browserContext()](#targetbrowsercontext)
  * [target.createCDPSession()](#targetcreatecdpsession)
  * [target.opener()](#targetopener)
  * [target.page()](#targetpage)
  * [target.type()](#targettype)
  * [target.url()](#targeturl)
- [class: CDPSession](#class-cdpsession)
  * [cdpSession.detach()](#cdpsessiondetach)
  * [cdpSession.send(method[, params])](#cdpsessionsendmethod-params)
- [class: Coverage](#class-coverage)
  * [coverage.startCSSCoverage(options)](#coveragestartcsscoverageoptions)
  * [coverage.startJSCoverage(options)](#coveragestartjscoverageoptions)
  * [coverage.stopCSSCoverage()](#coveragestopcsscoverage)
  * [coverage.stopJSCoverage()](#coveragestopjscoverage)
- [class: TimeoutError](#class-timeouterror)
<!-- GEN:stop -->

### Overview

Puppeteer 是一个 Node 库，它提供了一个高级 API 来通过 DevTools 协议控制 Chromium 或 Chrome。

Puppeteer API 是分层次的，反映了浏览器结构。 

> 注意：在下面的图表中，浅色框体内容目前不在 Puppeteer 中体现。

![puppeteer 概述](https://user-images.githubusercontent.com/746130/40333229-5df5480c-5d0c-11e8-83cb-c3e371de7374.png)

- [`Puppeteer`](#class-puppeteer) 使用 [DevTools 协议](https://chromedevtools.github.io/devtools-protocol/) 与浏览器进行通信。
- [`Browser`](#class-browser) 实例可以拥有浏览器上下文。
- [`BrowserContext`](#class-browsercontext) 实例定义了一个浏览会话并可拥有多个页面。
- [`Page`](#class-page) 至少有一个框架：主框架。 可能还有其他框架由 [iframe](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) 或 [框架标签](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame) 创建。
- [`frame`](#class-frame) 至少有一个执行上下文 - 默认的执行上下文 - 框架的 JavaScript 被执行。 一个框架可能有额外的与 [扩展](https://developer.chrome.com/extensions) 关联的执行上下文。
- [`Worker`](#class-worker) 具有单一执行上下文，并且便于与 [WebWorkers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API) 进行交互。

(图例资源: [链接](https://docs.google.com/drawings/d/1Q_AM6KYs9kbyLZF-Lpp5mtpAWth73Cq8IKCsWYgi8MM/edit?usp=sharing))

### puppeteer vs puppeteer-core

[📚 查看原文](//github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#puppeteer-vs-puppeteer-core)

自 v1.7.0 以来的每个版本我们都发布了两个包:
- [puppeteer](https://www.npmjs.com/package/puppeteer)
- [puppeteer-core](https://www.npmjs.com/package/puppeteer-core)

`puppeteer` 是浏览器自动化的 *产品*。安装后，它会下载一个版本的 Chromium，然后使用`puppeteer-core` 驱动工作。作为最终用户产品，`puppeteer` 支持一堆方便的 `PUPPETEER_*` env 变量来调整行为。

`puppeteer-core` 是一个 *库* 来帮助驱动任何支持 DevTools 协议的东西。`puppeteer-core` 在安装时不会下载 Chromium。作为一个库，`puppeteer-core` 是完全是通过其编程接口驱动的并忽略所有`PUPPETEER_*` env 变量。

总结一下，`puppeteer-core` 与 `puppeteer` 不同的地方：
- `puppeteer-core` 在安装时不会自动下载 Chromium。
- `puppeteer-core`忽略所有的 `PUPPETEER_*` env 变量.

在大多数情况下，你可以使用 `puppeteer` 包。

然而, 如果是下面这些情况那你需要使用 `puppeteer-core`:
- 你正在构建 DevTools 协议顶部的另一个最终用户产品或库。例如，可以使用 `puppeteer-core` 构建 PDF 生成器并编写下载 [`headless_shell`](https://chromium.googlesource.com/chromium/src/+/lkgr/headless/README.md) 的自定义`install.js`脚本而不是 Chromium 来节省磁盘空间。
- 你正在打包 Puppeteer 用在 Chrome 扩展应用或浏览器中以使用 DevTools 协议，因为下载额外的 Chromium 二进制文件不是必须的。

当使用 `puppeteer-core` 时，使用下面这行代替原来的使用方式：

```js
const puppeteer = require('puppeteer-core');
```


### Environment Variables

[📚 查看原文](//github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#environment-variables)

Puppeteer 寻找某些环境变量来帮助其操作。 如果 puppeteer 在环境中没有找到它们，这些变量的小写变体将从 [npm 配置](https://docs.npmjs.com/cli/config) 中使用。

- `HTTP_PROXY`, `HTTPS_PROXY`, `NO_PROXY` - 定义用于下载和运行 Chromium 的 HTTP 代理设置。
- `PUPPETEER_SKIP_CHROMIUM_DOWNLOAD` - 请勿在安装步骤中下载绑定的 Chromium。
- `PUPPETEER_DOWNLOAD_HOST` - 覆盖用于下载 Chromium 的 URL 的主机部分。
- `PUPPETEER_CHROMIUM_REVISION` - 在安装步骤中指定一个你喜欢 puppeteer 使用的特定版本的 Chromium。
- `PUPPETEER_EXECUTABLE_PATH` - 指定一个 Chrome 或者 Chromium 的可执行路径，会被用于 `puppeteer.launch`。具体关于可执行路径参数的意义，可参考[`puppeteer.launch([options])`](#puppeteerlaunchoptions)。

> **NOTE** 在使用 [`puppeteer-core`](https://www.npmjs.com/package/puppeteer-core) 时，上述环境变量中以 PUPPETEER_* 开头的会被忽略.

### Error handling

[📚 查看原文](//github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#error-handling)

如果 Puppeteer 方法无法执行一个请求，就会抛出一个错误。例如，[page.waitForSelector(selector[, options])](#pagewaitforselectorselector-options) 选择器如果在给定的时间范围内无法匹配节点，就会失败。

对于某些类型的错误，Puppeteer 使用特定的错误类处理。这些类可以通过 `require('puppeteer/Errors')` 获得。

支持的类列表：
- [`TimeoutError`](#class-timeouterror)

一个处理超时错误的例子：
```js
const {TimeoutError} = require('puppeteer/Errors');

// ...

try {
  await page.waitForSelector('.foo');
} catch (e) {
  if (e instanceof TimeoutError) {
    // 如果超时，做一些处理。
  }
}
```


### Working with Chrome Extensions

[📚 查看原文](//github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#working-with-chrome-extensions)

Puppeteer 可以用来测试 Chrome 扩展

> **注意** Chrome / Chromium 扩展当前只能在非无头模式下使用。

下面的代码用来处理扩展的 [background page](https://developer.chrome.com/extensions/background_pages)，该扩展的代码在 `./my-extension`:

```js
const puppeteer = require('puppeteer');

(async () => {
  const pathToExtension = require('path').join(__dirname, 'my-extension');
  const browser = puppeteer.launch({
    headless: false,
    args: [
      `--disable-extensions-except=${pathToExtension}`,
      `--load-extension=${pathToExtension}`
    ]
  });
  const targets = await browser.targets();
  const backgroundPageTarget = targets.find(target => target.type() === 'background_page');
  const backgroundPage = await backgroundPageTarget.page();
  // 像处理任何其他页面一样测试背景页面。
  await browser.close();
})();
```

> **注意** 目前还无法测试扩展弹出窗口或内容脚本。

### class: Puppeteer

Puppeteer 模块提供了一种启动 Chromium 实例的方法。
下面就是使用 Puppeteer 进行自动化的一个典型示例：
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.goto('https://www.google.com');
  // 其他操作...
  await browser.close();
});
```

#### puppeteer.connect(options)
- `options` <[Object]>
  - `browserWSEndpoint` <[string]> 一个 [浏览器 websocket 端点链接](#browserwsendpoint)。
  - `ignoreHTTPSErrors` <[boolean]> 是否在导航期间忽略 HTTPS 错误. 默认是 `false`。
  - `defaultViewport` <?[Object]> 为每个页面设置一个默认视口大小。默认是 800x600。如果为 `null` 的话就禁用视图口。
    - `width` <[number]> 页面宽度像素。
    - `height` <[number]> 页面高度像素。
    - `deviceScaleFactor` <[number]> 设置设备的缩放（可以认为是 dpr）。默认是 `1`。
    - `isMobile` <[boolean]> 是否在页面中设置了 `meta viewport` 标签。默认是 `false`。
    - `hasTouch`<[boolean]> 指定viewport是否支持触摸事件。默认是 `false`。
    - `isLandscape` <[boolean]> 指定视口是否处于横向模式。默认是 `false`。
  - `slowMo` <[number]> 将 Puppeteer 操作减少指定的毫秒数。这样你就可以看清发生了什么，这很有用。
- returns: <[Promise]<[Browser]>>

此方法将 Puppeteer 添加到现有的 Chromium 实例。

#### puppeteer.createBrowserFetcher([options])
- `options` <[Object]>
  - `host` <[string]> 要使用的下载主机. 默认是 `https://storage.googleapis.com`.
  - `path` <[string]> 下载文件夹的路径. 默认是 `<root>/.local-chromium`, `<root>` 是 puppeteer 的包根目录。
  - `platform` <[string]> 可能的值有: `mac`, `win32`, `win64`, `linux`. 默认是当前平台。
- returns: <[BrowserFetcher]>

#### puppeteer.defaultArgs([options])
- `options` <[Object]>  设置浏览器可选项。有一下字段：
  - `headless` <[boolean]> 是否在 [无头模式]((https://developers.google.com/web/updates/2017/04/headless-chrome) 下运行浏览器。默认是 `true` 除非  `devtools` 选项是 `true`。
  - `args` <[Array]<[string]>> 传递给浏览器实例的其他参数。可以 [在这](http://peter.sh/experiments/chromium-command-line-switches/) 找到 Chromium 标志列表。
  - `userDataDir` <[string]> [用户数据目录](https://chromium.googlesource.com/chromium/src/+/master/docs/user_data_dir.md) 的路径。
  - `devtools` <[boolean]> 是否为每个选项卡自动打开 DevTools 面板。如果这个选项是 `true` 的话, `headless` 选项将被设置为 `false`。
- returns: <[Array]<[string]>>

Chromium 启动时将使用的默认参数。

#### puppeteer.executablePath()
- returns: <[string]> Puppeteer 希望找到绑定的 Chromium 的路径。 如果使用 [`PUPPETEER_SKIP_CHROMIUM_DOWNLOAD`](#environment-variables) 跳过下载，则 Chromium 可能不存在。

#### puppeteer.launch([options])
- `options` <[Object]>  在浏览器上设置的一组可配置选项。 有以下字段：
  - `ignoreHTTPSErrors` <[boolean]> 是否在导航期间忽略 HTTPS 错误. 默认是 `false`。
  - `headless` <[boolean]> 是否以 [无头模式](https://developers.google.com/web/updates/2017/04/headless-chrome) 运行浏览器。默认是 `true`，除非 `devtools` 选项是 `true`。
  - `executablePath` <[string]> 可运行 Chromium 或 Chrome 可执行文件的路径，而不是绑定的的 Chromium。如果 `executablePath` 是一个相对路径，那么他相对于 [当前工作路径](https://nodejs.org/api/process.html#process_process_cwd) 解析。
  - `slowMo` <[number]> 将 Puppeteer 操作减少指定的毫秒数。这样你就可以看清发生了什么，这很有用。
  - `defaultViewport` <?[Object]> 为每个页面设置一个默认视口大小。默认是 800x600。如果为 `null` 的话就禁用视图口。
    - `width` <[number]> 页面宽度像素。
    - `height` <[number]> 页面高度像素。
    - `deviceScaleFactor` <[number]> 设置设备的缩放（可以认为是 dpr）。默认是 `1`。
    - `isMobile` <[boolean]> 是否在页面中设置了 `meta viewport` 标签。默认是 `false`。
    - `hasTouch`<[boolean]> 指定viewport是否支持触摸事件。默认是 `false`。
    - `isLandscape` <[boolean]> 指定视口是否处于横向模式。默认是 `false`。
  - `args` <[Array]<[string]>> 传递给浏览器实例的其他参数。 这些参数可以参考 [这里](http://peter.sh/experiments/chromium-command-line-switches/)。
  - `ignoreDefaultArgs` <([boolean]|<[Array]<[string]>>)> 如果是 `true`，那就不要使用 [`puppeteer.defaultArgs()`](#puppeteerdefaultargs-options)。 如果给出了数组，则过滤掉给定的默认参数。这个选项请谨慎使用。默认为 `false`。
  - `handleSIGINT` <[boolean]> Ctrl-C 关闭浏览器进程。默认是 `true`。
  - `handleSIGTERM` <[boolean]> 关闭 SIGTERM 上的浏览器进程。默认是 `true`。
  - `handleSIGHUP` <[boolean]> 关闭 SIGHUP 上的浏览器进程。默认是 `true`.
  - `timeout` <[number]> 等待浏览器实例启动的最长时间（以毫秒为单位）。默认是 `30000` (30 秒). 通过 `0` 来禁用超时。
  - `dumpio` <[boolean]> 是否将浏览器进程标准输出和标准错误输入到 `process.stdout` 和 `process.stderr` 中。默认是 `false`。
  - `userDataDir` <[string]> [用户数据目录](https://chromium.googlesource.com/chromium/src/+/master/docs/user_data_dir.md) 路径。
  - `env` <[Object]> 指定浏览器可见的环境变量。默认是 `process.env`。
  - `devtools` <[boolean]> 是否为每个选项卡自动打开DevTools面板。如果这个选项是 `true`，`headless` 选项将会设置成 `false`。
  - `pipe` <[boolean]> 通过管道而不是WebSocket连接到浏览器。默认是 `false`。
- returns: <[Promise]<[Browser]>> 浏览器实例支持 Promise。

这个方法结合了下面3个步骤：
1、使用 `puppeteer.defaultArgs()` 作为一组默认值来启动 Chromium。
2、启动浏览器并根据 `executablePath` ，`handleSIGINT`，`dumpio` 和其他选项开始管理它的进程。
3、创建一个 [Browser] 类的实例，并根据 `defaultViewport`，`slowMo` 和 `ignoreHTTPSErrors` 初始化它。

`ignoreDefaultArgs` 选项可用于自定义（1）步骤的行为。 例如，要从参数中过滤掉 `--mute-audio`：
```js
const browser = await puppeteer.launch({
  ignoreDefaultArgs: ['--mute-audio']
});
```

> **NOTE** Puppeteer 也可以用来控制 Chrome 浏览器， 但它与绑定的 Chromium 版本在一起使用效果最好。不能保证它可以与任何其他版本一起使用。谨慎地使用 `executablePath` 选项。
>
> 如果 Google Chrome（而不是Chromium）是首选，一个 [Chrome Canary](https://www.google.com/chrome/browser/canary.html) 或 [Dev Channel](https://www.chromium.org/getting-involved/dev-channel) 版本是建议的。
>
> 在上面的 [puppeteer.launch([options])](#puppeteerlaunchoptions) 中，任何提及的 Chromium 同样也适用于 Chrome。
>
> 参考 [这篇文章](https://www.howtogeek.com/202825/what%E2%80%99s-the-difference-between-chromium-and-chrome/) 了解 Chromium and Chrome 的不同。 [`本文`](https://chromium.googlesource.com/chromium/src/+/lkcr/docs/chromium_browser_vs_google_chrome.md) 介绍了 Linux 用户的一些差异。

### class: BrowserFetcher

BrowserFetcher 可以用来下载和管理不同版本的 Chromium。

BrowserFetcher 操作一个修订版本字符串，修订版本字符串指定了一个 Chromium 的确定版本，例如 `"533271"`。修订版本字符串可以从 [omahaproxy.appspot.com](http://omahaproxy.appspot.com/) 获取。

见下面这个例子，告诉你如何使用 BrowserFetcher 下载一个指定版本的 Chromium：

```js
const browserFetcher = puppeteer.createBrowserFetcher();
const revisionInfo = await browserFetcher.download('533271');
const browser = await puppeteer.launch({executablePath: revisionInfo.executablePath})
```

> **注意** BrowserFetcher 不适用于与共享下载目录的其他实例同时运行。

#### browserFetcher.canDownload(revision)
- `revision` <[string]> 修订版本号, 检查其可用性
- returns: <[Promise]<[boolean]>> 返回 `true` 如果该修订版本可以从主机下载

该方法将会发起一个 HEAD 请求来检查该修订版本是否有效。

#### browserFetcher.download(revision[, progressCallback])
- `revision` <[string]> 下载的修订版本
  - `progressCallback` <[function]([number], [number])> 一个函数, 调用时将会传入两个参数：
  - `downloadedBytes` <[number]> 多少字节已经被下载
  - `totalBytes` <number> 下载全部的字节数(译者注: 也就是需要下载的文件大小)
- returns: <[Promise]<Object>> Resolves with revision information when the revision is downloaded and extracted
  - `revision` <[string]> 该修订版本被创建时的信息
  - `folderPath` <[string]> 解压该修订版本的路径
  - `executablePath` <[string]> 该修订版本的可执行文件的路径
  - `url` <[string]> URL 该修订版本的下载路径
  - `local` <[boolean]> 该修订版本是否是在本地的磁盘上是可用的

该方法将会发起一个 GET 请求来从主机下载该修订版本。

#### browserFetcher.localRevisions()
- returns: <[Promise]<[Array]<[string]>>> 一个列表, 包含所有的在本地磁盘可用的修订版本

#### browserFetcher.platform()
- returns: <[string]> 返回 `mac`， `linux`， `win32` 或 `win64` 之一。

#### browserFetcher.remove(revision)
- `revision` <[string]> 想要移除的修订版本，如果指定的修订版本还没有被下载，该方法将抛出一个错误
- returns: <[Promise]> Resolves when the revision has been removed.

#### browserFetcher.revisionInfo(revision)
- `revision` <[string]> 想要获取信息的修订版本
- returns: <[Object]>
  - `revision` <[string]> 该修订版本被创建时的信息
  - `folderPath` <[string]> 解压该修订版本的路径
  - `executablePath` <[string]> 该修订版本的可执行文件的路径
  - `url` <[string]> URL 该修订版本的下载路径
  - `local` <[boolean]> 该修订版本是否是在本地的磁盘上是可用的

### class: Browser

* extends: [`EventEmitter`](https://nodejs.org/api/events.html#events_class_eventemitter)

A Browser is created when Puppeteer connects to a Chromium instance, either through [`puppeteer.launch`](#puppeteerlaunchoptions) or [`puppeteer.connect`](#puppeteerconnectoptions).

An example of using a [Browser] to create a [Page]:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.goto('https://example.com');
  await browser.close();
});
```

An example of disconnecting from and reconnecting to a [Browser]:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  // Store the endpoint to be able to reconnect to Chromium
  const browserWSEndpoint = browser.wsEndpoint();
  // Disconnect puppeteer from Chromium
  browser.disconnect();

  // Use the endpoint to reestablish a connection
  const browser2 = await puppeteer.connect({browserWSEndpoint});
  // Close Chromium
  await browser2.close();
});
```
#### event: 'disconnected'
Emitted when Puppeteer gets disconnected from the Chromium instance. This might happen because of one of the following:
- Chromium is closed or crashed
- The [`browser.disconnect`](#browserdisconnect) method was called

#### event: 'targetchanged'
- <[Target]>

Emitted when the url of a target changes.

> **NOTE** This includes target changes in incognito browser contexts.


#### event: 'targetcreated'
- <[Target]>

Emitted when a target is created, for example when a new page is opened by [`window.open`](https://developer.mozilla.org/en-US/docs/Web/API/Window/open) or [`browser.newPage`](#browsernewpage).

> **NOTE** This includes target creations in incognito browser contexts.

#### event: 'targetdestroyed'
- <[Target]>

Emitted when a target is destroyed, for example when a page is closed.

> **NOTE** This includes target destructions in incognito browser contexts.

#### browser.browserContexts()
- returns: <[Array]<[BrowserContext]>>

Returns an array of all open browser contexts. In a newly created browser, this will return
a single instance of [BrowserContext].

#### browser.close()
- returns: <[Promise]>

Closes Chromium and all of its pages (if any were opened). The [Browser] object itself is considered to be disposed and cannot be used anymore.

#### browser.createIncognitoBrowserContext()
- returns: <[Promise]<[BrowserContext]>>

Creates a new incognito browser context. This won't share cookies/cache with other browser contexts.

```js
const browser = await puppeteer.launch();
// Create a new incognito browser context.
const context = await browser.createIncognitoBrowserContext();
// Create a new page in a pristine context.
const page = await context.newPage();
// Do stuff
await page.goto('https://example.com');
```

#### browser.defaultBrowserContext()
- returns: <[BrowserContext]>

Returns the default browser context. The default browser context can not be closed.

#### browser.disconnect()

Disconnects Puppeteer from the browser, but leaves the Chromium process running. After calling `disconnect`, the [Browser] object is considered disposed and cannot be used anymore.

#### browser.newPage()
- returns: <[Promise]<[Page]>>

Promise which resolves to a new [Page] object. The [Page] is created in a default browser context.

#### browser.pages()
- returns: <[Promise]<[Array]<[Page]>>> Promise which resolves to an array of all open pages. Non visible pages, such as `"background_page"`, will not be listed here. You can find them using [target.page()](#targetpage).

An array of all pages inside the Browser. In case of multiple browser contexts,
the method will return an array with all the pages in all browser contexts.

#### browser.process()
- returns: <?[ChildProcess]> Spawned browser process. Returns `null` if the browser instance was created with [`puppeteer.connect`](#puppeteerconnectoptions) method.

#### browser.target()
- returns: <[Target]>

A target associated with the browser.

#### browser.targets()
- returns: <[Array]<[Target]>>

An array of all active targets inside the Browser. In case of multiple browser contexts,
the method will return an array with all the targets in all browser contexts.

#### browser.userAgent()
- returns: <[Promise]<[string]>> Promise which resolves to the browser's original user agent.

> **NOTE** Pages can override browser user agent with [page.setUserAgent](#pagesetuseragentuseragent)

#### browser.version()
- returns: <[Promise]<[string]>> For headless Chromium, this is similar to `HeadlessChrome/61.0.3153.0`. For non-headless, this is similar to `Chrome/61.0.3153.0`.

> **NOTE** the format of browser.version() might change with future releases of Chromium.

#### browser.waitForTarget(predicate[, options])
- `predicate` <[function]\([Target]\):[boolean]> A function to be run for every target
- `options` <[Object]>
  - `timeout` <[number]> Maximum wait time in milliseconds. Pass `0` to disable the timeout. Defaults to 30 seconds.
- returns: <[Promise]<[Target]>> Promise which resolves to the first target found that matches the `predicate` function.

This searches for a target in all browser contexts.

An example of finding a target for a page opened via `window.open`:
```js
await page.evaluate(() => window.open('https://www.example.com/'));
const newWindowTarget = await browser.waitForTarget(target => target.url() === 'https://www.example.com/');
```

#### browser.wsEndpoint()
- returns: <[string]> Browser websocket url.

Browser websocket endpoint which can be used as an argument to
[puppeteer.connect](#puppeteerconnectoptions). The format is `ws://${host}:${port}/devtools/browser/<id>`

You can find the `webSocketDebuggerUrl` from `http://${host}:${port}/json/version`. Learn more about the [devtools protocol](https://chromedevtools.github.io/devtools-protocol) and the [browser endpoint](https://chromedevtools.github.io/devtools-protocol/#how-do-i-access-the-browser-target).

### class: BrowserContext

* extends: [`EventEmitter`](https://nodejs.org/api/events.html#events_class_eventemitter)

BrowserContexts provide a way to operate multiple independent browser sessions. When a browser is launched, it has
a single BrowserContext used by default. The method `browser.newPage()` creates a page in the default browser context.

If a page opens another page, e.g. with a `window.open` call, the popup will belong to the parent page's browser
context.

Puppeteer allows creation of "incognito" browser contexts with `browser.createIncognitoBrowserContext()` method.
"Incognito" browser contexts don't write any browsing data to disk.

```js
// Create a new incognito browser context
const context = await browser.createIncognitoBrowserContext();
// Create a new page inside context.
const page = await context.newPage();
// ... do stuff with page ...
await page.goto('https://example.com');
// Dispose context once it's no longer needed.
await context.close();
```

#### event: 'targetchanged'
- <[Target]>

Emitted when the url of a target inside the browser context changes.

#### event: 'targetcreated'
- <[Target]>

Emitted when a new target is created inside the browser context, for example when a new page is opened by [`window.open`](https://developer.mozilla.org/en-US/docs/Web/API/Window/open) or [`browserContext.newPage`](#browsercontextnewpage).

#### event: 'targetdestroyed'
- <[Target]>

Emitted when a target inside the browser context is destroyed, for example when a page is closed.

#### browserContext.browser()
- returns: <[Browser]>

The browser this browser context belongs to.

#### browserContext.clearPermissionOverrides()
- returns: <[Promise]>

Clears all permission overrides for the browser context.

```js
const context = browser.defaultBrowserContext();
context.overridePermissions('https://example.com', ['clipboard-read']);
// do stuff ..
context.clearPermissionOverrides();
```

#### browserContext.close()
- returns: <[Promise]>

Closes the browser context. All the targets that belong to the browser context
will be closed.

> **NOTE** only incognito browser contexts can be closed.

#### browserContext.isIncognito()
- returns: <[boolean]>

Returns whether BrowserContext is incognito.
The default browser context is the only non-incognito browser context.

> **NOTE** the default browser context cannot be closed.

#### browserContext.newPage()
- returns: <[Promise]<[Page]>>

Creates a new page in the browser context.


#### browserContext.overridePermissions(origin, permissions)
- `origin` <[string]> The [origin] to grant permissions to, e.g. "https://example.com".
- `permissions` <[Array]<[string]>> An array of permissions to grant. All permissions that are not listed here will be automatically denied. Permissions can be one of the following values:
    - `'geolocation'`
    - `'midi'`
    - `'midi-sysex'` (system-exclusive midi)
    - `'notifications'`
    - `'push'`
    - `'camera'`
    - `'microphone'`
    - `'background-sync'`
    - `'ambient-light-sensor'`
    - `'accelerometer'`
    - `'gyroscope'`
    - `'magnetometer'`
    - `'accessibility-events'`
    - `'clipboard-read'`
    - `'clipboard-write'`
    - `'payment-handler'`
- returns: <[Promise]>


```js
const context = browser.defaultBrowserContext();
await context.overridePermissions('https://html5demos.com', ['geolocation']);
```


#### browserContext.pages()
- returns: <[Promise]<[Array]<[Page]>>> Promise which resolves to an array of all open pages. Non visible pages, such as `"background_page"`, will not be listed here. You can find them using [target.page()](#targetpage).

An array of all pages inside the browser context.

#### browserContext.targets()
- returns: <[Array]<[Target]>>

An array of all active targets inside the browser context.

#### browserContext.waitForTarget(predicate[, options])
- `predicate` <[function]\([Target]\):[boolean]> A function to be run for every target
- `options` <[Object]>
  - `timeout` <[number]> Maximum wait time in milliseconds. Pass `0` to disable the timeout. Defaults to 30 seconds.
- returns: <[Promise]<[Target]>> Promise which resolves to the first target found that matches the `predicate` function.

This searches for a target in this specific browser context.

An example of finding a target for a page opened via `window.open`:
```js
await page.evaluate(() => window.open('https://www.example.com/'));
const newWindowTarget = await browserContext.waitForTarget(target => target.url() === 'https://www.example.com/');
```

### class: Page

* extends: [`EventEmitter`](https://nodejs.org/api/events.html#events_class_eventemitter)

Page provides methods to interact with a single tab or [extension background page](https://developer.chrome.com/extensions/background_pages) in Chromium. One [Browser] instance might have multiple [Page] instances.

This example creates a page, navigates it to a URL, and then saves a screenshot:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.goto('https://example.com');
  await page.screenshot({path: 'screenshot.png'});
  await browser.close();
});
```

The Page class emits various events (described below) which can be handled using any of Node's native [`EventEmitter`](https://nodejs.org/api/events.html#events_class_eventemitter) methods, such as `on`, `once` or `removeListener`.

This example logs a message for a single page `load` event:
```js
page.once('load', () => console.log('Page loaded!'));
```

To unsubscribe from events use the `removeListener` method:

```js
function logRequest(interceptedRequest) {
  console.log('A request was made:', interceptedRequest.url());
}
page.on('request', logRequest);
// Sometime later...
page.removeListener('request', logRequest);
```

#### event: 'close'

Emitted when the page closes.

#### event: 'console'
- <[ConsoleMessage]>

Emitted when JavaScript within the page calls one of console API methods, e.g. `console.log` or `console.dir`. Also emitted if the page throws an error or a warning.

The arguments passed into `console.log` appear as arguments on the event handler.

An example of handling `console` event:
```js
page.on('console', msg => {
  for (let i = 0; i < msg.args().length; ++i)
    console.log(`${i}: ${msg.args()[i]}`);
});
page.evaluate(() => console.log('hello', 5, {foo: 'bar'}));
```

#### event: 'dialog'
- <[Dialog]>

Emitted when a JavaScript dialog appears, such as `alert`, `prompt`, `confirm` or `beforeunload`. Puppeteer can respond to the dialog via [Dialog]'s [accept](#dialogacceptprompttext) or [dismiss](#dialogdismiss) methods.

#### event: 'domcontentloaded'

Emitted when the JavaScript [`DOMContentLoaded`](https://developer.mozilla.org/en-US/docs/Web/Events/DOMContentLoaded) event is dispatched.

#### event: 'error'
- <[Error]>

Emitted when the page crashes.

> **NOTE** `error` event has a special meaning in Node, see [error events](https://nodejs.org/api/events.html#events_error_events) for details.

#### event: 'frameattached'
- <[Frame]>

Emitted when a frame is attached.

#### event: 'framedetached'
- <[Frame]>

Emitted when a frame is detached.

#### event: 'framenavigated'
- <[Frame]>

Emitted when a frame is navigated to a new url.

#### event: 'load'

Emitted when the JavaScript [`load`](https://developer.mozilla.org/en-US/docs/Web/Events/load) event is dispatched.

#### event: 'metrics'
- <[Object]>
  - `title` <[string]> The title passed to `console.timeStamp`.
  - `metrics` <[Object]> Object containing metrics as key/value pairs. The values
    of metrics are of <[number]> type.

Emitted when the JavaScript code makes a call to `console.timeStamp`. For the list
of metrics see `page.metrics`.

#### event: 'pageerror'
- <[Error]> The exception message

Emitted when an uncaught exception happens within the page.

#### event: 'request'
- <[Request]>

Emitted when a page issues a request. The [request] object is read-only.
In order to intercept and mutate requests, see `page.setRequestInterception`.

#### event: 'requestfailed'
- <[Request]>

Emitted when a request fails, for example by timing out.

#### event: 'requestfinished'
- <[Request]>

Emitted when a request finishes successfully.

#### event: 'response'
- <[Response]>

Emitted when a [response] is received.

#### event: 'workercreated'
- <[Worker]>

Emitted when a dedicated [WebWorker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API) is spawned by the page.

#### event: 'workerdestroyed'
- <[Worker]>

Emitted when a dedicated [WebWorker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API) is terminated.

#### page.$(selector)
- `selector` <[string]> A [selector] to query page for
- returns: <[Promise]<?[ElementHandle]>>

The method runs `document.querySelector` within the page. If no element matches the selector, the return value resolves to `null`.

Shortcut for [page.mainFrame().$(selector)](#frameselector).

#### page.$$(selector)
- `selector` <[string]> A [selector] to query page for
- returns: <[Promise]<[Array]<[ElementHandle]>>>

The method runs `document.querySelectorAll` within the page. If no elements match the selector, the return value resolves to `[]`.

Shortcut for [page.mainFrame().$$(selector)](#frameselector-1).

#### page.$$eval(selector, pageFunction[, ...args])
- `selector` <[string]> A [selector] to query page for
- `pageFunction` <[function]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

This method runs `Array.from(document.querySelectorAll(selector))` within the page and passes it as the first argument to `pageFunction`.

If `pageFunction` returns a [Promise], then `page.$$eval` would wait for the promise to resolve and return its value.

Examples:
```js
const divsCounts = await page.$$eval('div', divs => divs.length);
```

#### page.$eval(selector, pageFunction[, ...args])
- `selector` <[string]> A [selector] to query page for
- `pageFunction` <[function]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

This method runs `document.querySelector` within the page and passes it as the first argument to `pageFunction`. If there's no element matching `selector`, the method throws an error.

If `pageFunction` returns a [Promise], then `page.$eval` would wait for the promise to resolve and return its value.

Examples:
```js
const searchValue = await page.$eval('#search', el => el.value);
const preloadHref = await page.$eval('link[rel=preload]', el => el.href);
const html = await page.$eval('.main-container', e => e.outerHTML);
```

Shortcut for [page.mainFrame().$eval(selector, pageFunction)](#frameevalselector-pagefunction-args).

#### page.$x(expression)
- `expression` <[string]> Expression to [evaluate](https://developer.mozilla.org/en-US/docs/Web/API/Document/evaluate).
- returns: <[Promise]<[Array]<[ElementHandle]>>>

The method evaluates the XPath expression.

Shortcut for [page.mainFrame().$x(expression)](#framexexpression)

#### page.accessibility
- returns: <[Accessibility]>

#### page.addScriptTag(options)
- `options` <[Object]>
  - `url` <[string]> URL of a script to be added.
  - `path` <[string]> Path to the JavaScript file to be injected into frame. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd).
  - `content` <[string]> Raw JavaScript content to be injected into frame.
  - `type` <[string]> Script type. Use 'module' in order to load a Javascript ES6 module. See [script](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) for more details.
- returns: <[Promise]<[ElementHandle]>> which resolves to the added tag when the script's onload fires or when the script content was injected into frame.

Adds a `<script>` tag into the page with the desired url or content.

Shortcut for [page.mainFrame().addScriptTag(options)](#frameaddscripttagoptions).

#### page.addStyleTag(options)
- `options` <[Object]>
  - `url` <[string]> URL of the `<link>` tag.
  - `path` <[string]> Path to the CSS file to be injected into frame. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd).
  - `content` <[string]> Raw CSS content to be injected into frame.
- returns: <[Promise]<[ElementHandle]>> which resolves to the added tag when the stylesheet's onload fires or when the CSS content was injected into frame.

Adds a `<link rel="stylesheet">` tag into the page with the desired url or a `<style type="text/css">` tag with the content.

Shortcut for [page.mainFrame().addStyleTag(options)](#frameaddstyletagoptions).

#### page.authenticate(credentials)
- `credentials` <?[Object]>
  - `username` <[string]>
  - `password` <[string]>
- returns: <[Promise]>

Provide credentials for [HTTP authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication).

To disable authentication, pass `null`.

#### page.bringToFront()

- returns: <[Promise]>

Brings page to front (activates tab).

#### page.browser()

- returns: <[Browser]>

Get the browser the page belongs to.

#### page.click(selector[, options])
- `selector` <[string]> A [selector] to search for element to click. If there are multiple elements satisfying the selector, the first will be clicked.
- `options` <[Object]>
  - `button` <[string]> `left`, `right`, or `middle`, defaults to `left`.
  - `clickCount` <[number]> defaults to 1. See [UIEvent.detail].
  - `delay` <[number]> Time to wait between `mousedown` and `mouseup` in milliseconds. Defaults to 0.
- returns: <[Promise]> Promise which resolves when the element matching `selector` is successfully clicked. The Promise will be rejected if there is no element matching `selector`.

This method fetches an element with `selector`, scrolls it into view if needed, and then uses [page.mouse](#pagemouse) to click in the center of the element.
If there's no element matching `selector`, the method throws an error.

Bear in mind that if `click()` triggers a navigation event and there's a separate `page.waitForNavigation()` promise to be resolved, you may end up with a race condition that yields unexpected results. The correct pattern for click and wait for navigation is the following:

```javascript
const [response] = await Promise.all([
  page.waitForNavigation(waitOptions),
  page.click(selector, clickOptions),
]);
```

Shortcut for [page.mainFrame().click(selector[, options])](#frameclickselector-options).

#### page.close(options)
- `options` <[Object]>
  - `runBeforeUnload` <[boolean]> Defaults to `false`. Whether to run the
    [before unload](https://developer.mozilla.org/en-US/docs/Web/Events/beforeunload)
    page handlers.
- returns: <[Promise]>

By default, `page.close()` **does not** run beforeunload handlers.

> **NOTE** if `runBeforeUnload` is passed as true, a `beforeunload` dialog might be summoned
> and should be handled manually via page's ['dialog'](#event-dialog) event.

#### page.content()
- returns: <[Promise]<[string]>>

Gets the full HTML contents of the page, including the doctype.

#### page.cookies(...urls)
- `...urls` <...[string]>
- returns: <[Promise]<[Array]<[Object]>>>
  - `name` <[string]>
  - `value` <[string]>
  - `domain` <[string]>
  - `path` <[string]>
  - `expires` <[number]> Unix time in seconds.
  - `size` <[number]>
  - `httpOnly` <[boolean]>
  - `secure` <[boolean]>
  - `session` <[boolean]>
  - `sameSite` <"Strict"|"Lax">

If no URLs are specified, this method returns cookies for the current page URL.
If URLs are specified, only cookies for those URLs are returned.

#### page.coverage

- returns: <[Coverage]>

#### page.deleteCookie(...cookies)
- `...cookies` <...[Object]>
  - `name` <[string]> **required**
  - `url` <[string]>
  - `domain` <[string]>
  - `path` <[string]>
- returns: <[Promise]>

#### page.emulate(options)
- `options` <[Object]>
  - `viewport` <[Object]>
    - `width` <[number]> page width in pixels.
    - `height` <[number]> page height in pixels.
    - `deviceScaleFactor` <[number]> Specify device scale factor (can be thought of as dpr). Defaults to `1`.
    - `isMobile` <[boolean]> Whether the `meta viewport` tag is taken into account. Defaults to `false`.
    - `hasTouch`<[boolean]> Specifies if viewport supports touch events. Defaults to `false`
    - `isLandscape` <[boolean]> Specifies if viewport is in landscape mode. Defaults to `false`.
  - `userAgent` <[string]>
- returns: <[Promise]>

Emulates given device metrics and user agent. This method is a shortcut for calling two methods:
- [page.setUserAgent(userAgent)](#pagesetuseragentuseragent)
- [page.setViewport(viewport)](#pagesetviewportviewport)

To aid emulation, puppeteer provides a list of device descriptors which can be obtained via the `require('puppeteer/DeviceDescriptors')` command.
Below is an example of emulating an iPhone 6 in puppeteer:
```js
const puppeteer = require('puppeteer');
const devices = require('puppeteer/DeviceDescriptors');
const iPhone = devices['iPhone 6'];

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.emulate(iPhone);
  await page.goto('https://www.google.com');
  // other actions...
  await browser.close();
});
```

List of all available devices is available in the source code: [DeviceDescriptors.js](https://github.com/GoogleChrome/puppeteer/blob/master/DeviceDescriptors.js).

#### page.emulateMedia(mediaType)
- `mediaType` <?[string]> Changes the CSS media type of the page. The only allowed values are `'screen'`, `'print'` and `null`. Passing `null` disables media emulation.
- returns: <[Promise]>

#### page.evaluate(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in the page context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

If the function passed to the `page.evaluate` returns a [Promise], then `page.evaluate` would wait for the promise to resolve and return its value.

If the function passed to the `page.evaluate` returns a non-[Serializable] value, then `page.evaluate` resolves to `undefined`.

Passing arguments to `pageFunction`:
```js
const result = await page.evaluate(x => {
  return Promise.resolve(8 * x);
}, 7);
console.log(result); // prints "56"
```

A string can also be passed in instead of a function:
```js
console.log(await page.evaluate('1 + 2')); // prints "3"
const x = 10;
console.log(await page.evaluate(`1 + ${x}`)); // prints "11"
```

[ElementHandle] instances can be passed as arguments to the `page.evaluate`:
```js
const bodyHandle = await page.$('body');
const html = await page.evaluate(body => body.innerHTML, bodyHandle);
await bodyHandle.dispose();
```

Shortcut for [page.mainFrame().evaluate(pageFunction, ...args)](#frameevaluatepagefunction-args).

#### page.evaluateHandle(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in the page context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves to the return value of `pageFunction` as in-page object (JSHandle)

The only difference between `page.evaluate` and `page.evaluateHandle` is that `page.evaluateHandle` returns in-page object (JSHandle).

If the function passed to the `page.evaluateHandle` returns a [Promise], then `page.evaluateHandle` would wait for the promise to resolve and return its value.

A string can also be passed in instead of a function:
```js
const aHandle = await page.evaluateHandle('document'); // Handle for the 'document'
```

[JSHandle] instances can be passed as arguments to the `page.evaluateHandle`:
```js
const aHandle = await page.evaluateHandle(() => document.body);
const resultHandle = await page.evaluateHandle(body => body.innerHTML, aHandle);
console.log(await resultHandle.jsonValue());
await resultHandle.dispose();
```

Shortcut for [page.mainFrame().executionContext().evaluateHandle(pageFunction, ...args)](#executioncontextevaluatehandlepagefunction-args).

#### page.evaluateOnNewDocument(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in browser context
- `...args` <...[Serializable]> Arguments to pass to `pageFunction`
- returns: <[Promise]>

Adds a function which would be invoked in one of the following scenarios:
- whenever the page is navigated
- whenever the child frame is attached or navigated. In this case, the function is invoked in the context of the newly attached frame

The function is invoked after the document was created but before any of its scripts were run. This is useful to amend  the JavaScript environment, e.g. to seed `Math.random`.

An example of overriding the navigator.languages property before the page loads:

```js
// preload.js

// overwrite the `languages` property to use a custom getter
Object.defineProperty(navigator, "languages", {
  get: function() {
    return ["en-US", "en", "bn"];
  }
});

// In your puppeteer script, assuming the preload.js file is in same folder of our script
const preloadFile = fs.readFileSync('./preload.js', 'utf8');
await page.evaluateOnNewDocument(preloadFile);
```

#### page.exposeFunction(name, puppeteerFunction)
- `name` <[string]> Name of the function on the window object
- `puppeteerFunction` <[function]> Callback function which will be called in Puppeteer's context.
- returns: <[Promise]>

The method adds a function called `name` on the page's `window` object.
When called, the function executes `puppeteerFunction` in node.js and returns a [Promise] which resolves to the return value of `puppeteerFunction`.

If the `puppeteerFunction` returns a [Promise], it will be awaited.

> **NOTE** Functions installed via `page.exposeFunction` survive navigations.

An example of adding an `md5` function into the page:
```js
const puppeteer = require('puppeteer');
const crypto = require('crypto');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  page.on('console', msg => console.log(msg.text()));
  await page.exposeFunction('md5', text =>
    crypto.createHash('md5').update(text).digest('hex')
  );
  await page.evaluate(async () => {
    // use window.md5 to compute hashes
    const myString = 'PUPPETEER';
    const myHash = await window.md5(myString);
    console.log(`md5 of ${myString} is ${myHash}`);
  });
  await browser.close();
});
```

An example of adding a `window.readfile` function into the page:

```js
const puppeteer = require('puppeteer');
const fs = require('fs');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  page.on('console', msg => console.log(msg.text()));
  await page.exposeFunction('readfile', async filePath => {
    return new Promise((resolve, reject) => {
      fs.readFile(filePath, 'utf8', (err, text) => {
        if (err)
          reject(err);
        else
          resolve(text);
      });
    });
  });
  await page.evaluate(async () => {
    // use window.readfile to read contents of a file
    const content = await window.readfile('/etc/hosts');
    console.log(content);
  });
  await browser.close();
});

```

#### page.focus(selector)
- `selector` <[string]> A [selector] of an element to focus. If there are multiple elements satisfying the selector, the first will be focused.
- returns: <[Promise]> Promise which resolves when the element matching `selector` is successfully focused. The promise will be rejected if there is no element matching `selector`.

This method fetches an element with `selector` and focuses it.
If there's no element matching `selector`, the method throws an error.

Shortcut for [page.mainFrame().focus(selector)](#framefocusselector).

#### page.frames()
- returns: <[Array]<[Frame]>> An array of all frames attached to the page.

#### page.goBack(options)
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
- returns: <[Promise]<?[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect. If
can not go back, resolves to `null`.

Navigate to the previous page in history.

#### page.goForward(options)
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
- returns: <[Promise]<?[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect. If
can not go forward, resolves to `null`.

Navigate to the next page in history.

#### page.goto(url, options)
- `url` <[string]> URL to navigate page to. The url should include scheme, e.g. `https://`.
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
  - `referer` <[string]> Referer header value. If provided it will take preference over the referer header value set by [page.setExtraHTTPHeaders()](#pagesetextrahttpheadersheaders).
- returns: <[Promise]<?[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect.

The `page.goto` will throw an error if:
- there's an SSL error (e.g. in case of self-signed certificates).
- target URL is invalid.
- the `timeout` is exceeded during navigation.
- the main resource failed to load.

> **NOTE** `page.goto` either throw or return a main resource response. The only exceptions are navigation to `about:blank` or navigation to the same URL with a different hash, which would succeed and return `null`.

> **NOTE** Headless mode doesn't support navigation to a PDF document. See the [upstream issue](https://bugs.chromium.org/p/chromium/issues/detail?id=761295).

Shortcut for [page.mainFrame().goto(url, options)](#framegotourl-options)

#### page.hover(selector)
- `selector` <[string]> A [selector] to search for element to hover. If there are multiple elements satisfying the selector, the first will be hovered.
- returns: <[Promise]> Promise which resolves when the element matching `selector` is successfully hovered. Promise gets rejected if there's no element matching `selector`.

This method fetches an element with `selector`, scrolls it into view if needed, and then uses [page.mouse](#pagemouse) to hover over the center of the element.
If there's no element matching `selector`, the method throws an error.

Shortcut for [page.mainFrame().hover(selector)](#framehoverselector).

#### page.isClosed()

- returns: <[boolean]>

Indicates that the page has been closed.

#### page.keyboard

- returns: <[Keyboard]>

#### page.mainFrame()
- returns: <[Frame]> returns page's main frame.

Page is guaranteed to have a main frame which persists during navigations.

#### page.metrics()
- returns: <[Promise]<[Object]>> Object containing metrics as key/value pairs.
  - `Timestamp` <[number]> The timestamp when the metrics sample was taken.
  - `Documents` <[number]> Number of documents in the page.
  - `Frames` <[number]> Number of frames in the page.
  - `JSEventListeners` <[number]> Number of events in the page.
  - `Nodes` <[number]> Number of DOM nodes in the page.
  - `LayoutCount` <[number]> Total number of full or partial page layout.
  - `RecalcStyleCount` <[number]> Total number of page style recalculations.
  - `LayoutDuration` <[number]> Combined durations of all page layouts.
  - `RecalcStyleDuration` <[number]> Combined duration of all page style recalculations.
  - `ScriptDuration` <[number]> Combined duration of JavaScript execution.
  - `TaskDuration` <[number]> Combined duration of all tasks performed by the browser.
  - `JSHeapUsedSize` <[number]> Used JavaScript heap size.
  - `JSHeapTotalSize` <[number]> Total JavaScript heap size.

> **NOTE** All timestamps are in monotonic time: monotonically increasing time in seconds since an arbitrary point in the past.

#### page.mouse

- returns: <[Mouse]>

#### page.pdf(options)
- `options` <[Object]> Options object which might have the following properties:
  - `path` <[string]> The file path to save the PDF to. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd). If no path is provided, the PDF won't be saved to the disk.
  - `scale` <[number]> Scale of the webpage rendering. Defaults to `1`. Scale amount must be between 0.1 and 2.
  - `displayHeaderFooter` <[boolean]> Display header and footer. Defaults to `false`.
  - `headerTemplate` <[string]> HTML template for the print header. Should be valid HTML markup with following classes used to inject printing values into them:
    - `date` formatted print date
    - `title` document title
    - `url` document location
    - `pageNumber` current page number
    - `totalPages` total pages in the document
  - `footerTemplate` <[string]> HTML template for the print footer. Should use the same format as the `headerTemplate`.
  - `printBackground` <[boolean]> Print background graphics. Defaults to `false`.
  - `landscape` <[boolean]> Paper orientation. Defaults to `false`.
  - `pageRanges` <[string]> Paper ranges to print, e.g., '1-5, 8, 11-13'. Defaults to the empty string, which means print all pages.
  - `format` <[string]> Paper format. If set, takes priority over `width` or `height` options. Defaults to 'Letter'.
  - `width` <[string]|[number]> Paper width, accepts values labeled with units.
  - `height` <[string]|[number]> Paper height, accepts values labeled with units.
  - `margin` <[Object]> Paper margins, defaults to none.
    - `top` <[string]|[number]> Top margin, accepts values labeled with units.
    - `right` <[string]|[number]> Right margin, accepts values labeled with units.
    - `bottom` <[string]|[number]> Bottom margin, accepts values labeled with units.
    - `left` <[string]|[number]> Left margin, accepts values labeled with units.
  - `preferCSSPageSize` <[boolean]> Give any CSS `@page` size declared in the page priority over what is declared in `width` and `height` or `format` options. Defaults to `false`, which will scale the content to fit the paper size.
- returns: <[Promise]<[Buffer]>> Promise which resolves with PDF buffer.

> **NOTE** Generating a pdf is currently only supported in Chrome headless.

`page.pdf()` generates a pdf of the page with `print` css media. To generate a pdf with `screen` media, call [page.emulateMedia('screen')](#pageemulatemediamediatype) before calling `page.pdf()`:

> **NOTE** By default, `page.pdf()` generates a pdf with modified colors for printing. Use the [`-webkit-print-color-adjust`](https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-print-color-adjust) property to force rendering of exact colors.

```js
// Generates a PDF with 'screen' media type.
await page.emulateMedia('screen');
await page.pdf({path: 'page.pdf'});
```

The `width`, `height`, and `margin` options accept values labeled with units. Unlabeled values are treated as pixels.

A few examples:
- `page.pdf({width: 100})` - prints with width set to 100 pixels
- `page.pdf({width: '100px'})` - prints with width set to 100 pixels
- `page.pdf({width: '10cm'})` - prints with width set to 10 centimeters.

All possible units are:
- `px` - pixel
- `in` - inch
- `cm` - centimeter
- `mm` - millimeter

The `format` options are:
- `Letter`: 8.5in x 11in
- `Legal`: 8.5in x 14in
- `Tabloid`: 11in x 17in
- `Ledger`: 17in x 11in
- `A0`: 33.1in x 46.8in
- `A1`: 23.4in x 33.1in
- `A2`: 16.5in x 23.4in
- `A3`: 11.7in x 16.5in
- `A4`: 8.27in x 11.7in
- `A5`: 5.83in x 8.27in
- `A6`: 4.13in x 5.83in

> **NOTE** `headerTemplate` and `footerTemplate` markup have the following limitations:
> 1. Script tags inside templates are not evaluated.
> 2. Page styles are not visible inside templates.

#### page.queryObjects(prototypeHandle)
- `prototypeHandle` <[JSHandle]> A handle to the object prototype.
- returns: <[Promise]<[JSHandle]>> Promise which resolves to a handle to an array of objects with this prototype.

The method iterates the JavaScript heap and finds all the objects with the given prototype.

```js
// Create a Map object
await page.evaluate(() => window.map = new Map());
// Get a handle to the Map object prototype
const mapPrototype = await page.evaluateHandle(() => Map.prototype);
// Query all map instances into an array
const mapInstances = await page.queryObjects(mapPrototype);
// Count amount of map objects in heap
const count = await page.evaluate(maps => maps.length, mapInstances);
await mapInstances.dispose();
await mapPrototype.dispose();
```

Shortcut for [page.mainFrame().executionContext().queryObjects(prototypeHandle)](#executioncontextqueryobjectsprototypehandle).

#### page.reload(options)
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
- returns: <[Promise]<[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect.

#### page.screenshot([options])
- `options` <[Object]> Options object which might have the following properties:
  - `path` <[string]> The file path to save the image to. The screenshot type will be inferred from file extension. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd). If no path is provided, the image won't be saved to the disk.
  - `type` <[string]> Specify screenshot type, can be either `jpeg` or `png`. Defaults to 'png'.
  - `quality` <[number]> The quality of the image, between 0-100. Not applicable to `png` images.
  - `fullPage` <[boolean]> When true, takes a screenshot of the full scrollable page. Defaults to `false`.
  - `clip` <[Object]> An object which specifies clipping region of the page. Should have the following fields:
    - `x` <[number]> x-coordinate of top-left corner of clip area
    - `y` <[number]> y-coordinate of top-left corner of clip area
    - `width` <[number]> width of clipping area
    - `height` <[number]> height of clipping area
  - `omitBackground` <[boolean]> Hides default white background and allows capturing screenshots with transparency. Defaults to `false`.
  - `encoding` <[string]> The encoding of the image, can be either `base64` or `binary`. Defaults to `binary`.
- returns: <[Promise]<[string]|[Buffer]>> Promise which resolves to buffer or a base64 string (depending on the value of `encoding`) with captured screenshot.

> **NOTE** Screenshots take at least 1/6 second on OS X. See https://crbug.com/741689 for discussion.

#### page.select(selector, ...values)
- `selector` <[string]> A [selector] to query page for
- `...values` <...[string]> Values of options to select. If the `<select>` has the `multiple` attribute, all values are considered, otherwise only the first one is taken into account.
- returns: <[Promise]<[Array]<[string]>>> Returns an array of option values that have been successfully selected.

Triggers a `change` and `input` event once all the provided options have been selected.
If there's no `<select>` element matching `selector`, the method throws an error.

```js
page.select('select#colors', 'blue'); // single selection
page.select('select#colors', 'red', 'green', 'blue'); // multiple selections
```

Shortcut for [page.mainFrame().select()](#frameselectselector-values)

#### page.setBypassCSP(enabled)
- `enabled` <[boolean]> sets bypassing of page's Content-Security-Policy.
- returns: <[Promise]>

Toggles bypassing page's Content-Security-Policy.

> **NOTE** CSP bypassing happens at the moment of CSP initialization rather then evaluation. Usually this means
that `page.setBypassCSP` should be called before navigating to the domain.

#### page.setCacheEnabled(enabled)
- `enabled` <[boolean]> sets the `enabled` state of the cache.
- returns: <[Promise]>

Toggles ignoring cache for each request based on the enabled state. By default, caching is enabled.

#### page.setContent(html)
- `html` <[string]> HTML markup to assign to the page.
- returns: <[Promise]>

#### page.setCookie(...cookies)
- `...cookies` <...[Object]>
  - `name` <[string]> **required**
  - `value` <[string]> **required**
  - `url` <[string]>
  - `domain` <[string]>
  - `path` <[string]>
  - `expires` <[number]> Unix time in seconds.
  - `httpOnly` <[boolean]>
  - `secure` <[boolean]>
  - `sameSite` <"Strict"|"Lax">
- returns: <[Promise]>

```js
await page.setCookie(cookieObject1, cookieObject2);
```

#### page.setDefaultNavigationTimeout(timeout)
- `timeout` <[number]> Maximum navigation time in milliseconds

This setting will change the default maximum navigation time of 30 seconds for the following methods:
- [page.goto(url, options)](#pagegotourl-options)
- [page.goBack(options)](#pagegobackoptions)
- [page.goForward(options)](#pagegoforwardoptions)
- [page.reload(options)](#pagereloadoptions)
- [page.waitForNavigation(options)](#pagewaitfornavigationoptions)

#### page.setExtraHTTPHeaders(headers)
- `headers` <[Object]> An object containing additional HTTP headers to be sent with every request. All header values must be strings.
- returns: <[Promise]>

The extra HTTP headers will be sent with every request the page initiates.

> **NOTE** page.setExtraHTTPHeaders does not guarantee the order of headers in the outgoing requests.

#### page.setGeolocation(options)
- `options` <[Object]>
  - `latitude` <[number]> Latitude between -90 and 90.
  - `longitude` <[number]> Longitude between -180 and 180.
  - `accuracy` <[number]> Optional non-negative accuracy value.
- returns: <[Promise]>

Sets the page's geolocation.

```js
await page.setGeolocation({latitude: 59.95, longitude: 30.31667});
```

> **NOTE** Consider using [browserContext.overridePermissions](#browsercontextoverridepermissionsorigin-permissions) to grant permissions for the page to read its geolocation.

#### page.setJavaScriptEnabled(enabled)
- `enabled` <[boolean]> Whether or not to enable JavaScript on the page.
- returns: <[Promise]>

> **NOTE** changing this value won't affect scripts that have already been run. It will take full effect on the next [navigation](#pagegotourl-options).

#### page.setOfflineMode(enabled)
- `enabled` <[boolean]> When `true`, enables offline mode for the page.
- returns: <[Promise]>

#### page.setRequestInterception(value)
- `value` <[boolean]> Whether to enable request interception.
- returns: <[Promise]>

Activating request interception enables `request.abort`, `request.continue` and
`request.respond` methods.  This provides the capability to modify network requests that are made by a page.

Once request interception is enabled, every request will stall unless it's continued, responded or aborted.
An example of a naïve request interceptor that aborts all image requests:

```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.setRequestInterception(true);
  page.on('request', interceptedRequest => {
    if (interceptedRequest.url().endsWith('.png') || interceptedRequest.url().endsWith('.jpg'))
      interceptedRequest.abort();
    else
      interceptedRequest.continue();
  });
  await page.goto('https://example.com');
  await browser.close();
});
```

> **NOTE** Enabling request interception disables page caching.

#### page.setUserAgent(userAgent)
- `userAgent` <[string]> Specific user agent to use in this page
- returns: <[Promise]> Promise which resolves when the user agent is set.

#### page.setViewport(viewport)
- `viewport` <[Object]>
  - `width` <[number]> page width in pixels.
  - `height` <[number]> page height in pixels.
  - `deviceScaleFactor` <[number]> Specify device scale factor (can be thought of as dpr). Defaults to `1`.
  - `isMobile` <[boolean]> Whether the `meta viewport` tag is taken into account. Defaults to `false`.
  - `hasTouch`<[boolean]> Specifies if viewport supports touch events. Defaults to `false`
  - `isLandscape` <[boolean]> Specifies if viewport is in landscape mode. Defaults to `false`.
- returns: <[Promise]>

> **NOTE** in certain cases, setting viewport will reload the page in order to set the `isMobile` or `hasTouch` properties.

In the case of multiple pages in a single browser, each page can have its own viewport size.

#### page.tap(selector)
- `selector` <[string]> A [selector] to search for element to tap. If there are multiple elements satisfying the selector, the first will be tapped.
- returns: <[Promise]>

This method fetches an element with `selector`, scrolls it into view if needed, and then uses [page.touchscreen](#pagetouchscreen) to tap in the center of the element.
If there's no element matching `selector`, the method throws an error.

Shortcut for [page.mainFrame().tap(selector)](#frametapselector).

#### page.target()
- returns: <[Target]> a target this page was created from.

#### page.title()
- returns: <[Promise]<[string]>> Returns page's title.

Shortcut for [page.mainFrame().title()](#frametitle).

#### page.touchscreen
- returns: <[Touchscreen]>

#### page.tracing
- returns: <[Tracing]>

#### page.type(selector, text[, options])
- `selector` <[string]> A [selector] of an element to type into. If there are multiple elements satisfying the selector, the first will be used.
- `text` <[string]> A text to type into a focused element.
- `options` <[Object]>
  - `delay` <[number]> Time to wait between key presses in milliseconds. Defaults to 0.
- returns: <[Promise]>

Sends a `keydown`, `keypress`/`input`, and `keyup` event for each character in the text.

To press a special key, like `Control` or `ArrowDown`, use [`keyboard.press`](#keyboardpresskey-options).

```js
page.type('#mytextarea', 'Hello'); // Types instantly
page.type('#mytextarea', 'World', {delay: 100}); // Types slower, like a user
```

Shortcut for [page.mainFrame().type(selector, text[, options])](#frametypeselector-text-options).

#### page.url()
- returns: <[string]>

This is a shortcut for [page.mainFrame().url()](#frameurl)

#### page.viewport()
- returns: <?[Object]>
  - `width` <[number]> page width in pixels.
  - `height` <[number]> page height in pixels.
  - `deviceScaleFactor` <[number]> Specify device scale factor (can be though of as dpr). Defaults to `1`.
  - `isMobile` <[boolean]> Whether the `meta viewport` tag is taken into account. Defaults to `false`.
  - `hasTouch`<[boolean]> Specifies if viewport supports touch events. Defaults to `false`
  - `isLandscape` <[boolean]> Specifies if viewport is in landscape mode. Defaults to `false`.

#### page.waitFor(selectorOrFunctionOrTimeout[, options[, ...args]])
- `selectorOrFunctionOrTimeout` <[string]|[number]|[function]> A [selector], predicate or timeout to wait for
- `options` <[Object]> Optional waiting parameters
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to  `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves to a JSHandle of the success value

This method behaves differently with respect to the type of the first parameter:
- if `selectorOrFunctionOrTimeout` is a `string`, then the first argument is treated as a [selector] or [xpath], depending on whether or not it starts with '//', and the method is a shortcut for
  [page.waitForSelector](#pagewaitforselectorselector-options) or [page.waitForXPath](#pagewaitforxpathxpath-options)
- if `selectorOrFunctionOrTimeout` is a `function`, then the first argument is treated as a predicate to wait for and the method is a shortcut for [page.waitForFunction()](#pagewaitforfunctionpagefunction-options-args).
- if `selectorOrFunctionOrTimeout` is a `number`, then the first argument is treated as a timeout in milliseconds and the method returns a promise which resolves after the timeout
- otherwise, an exception is thrown

```js
// wait for selector
await page.waitFor('.foo');
// wait for 1 second
await page.waitFor(1000);
// wait for predicate
await page.waitFor(() => !!document.querySelector('.foo'));
```

To pass arguments from node.js to the predicate of `page.waitFor` function:

```js
const selector = '.foo';
await page.waitFor(selector => !!document.querySelector(selector), {}, selector);
```

Shortcut for [page.mainFrame().waitFor(selectorOrFunctionOrTimeout[, options[, ...args]])](#framewaitforselectororfunctionortimeout-options-args).

#### page.waitForFunction(pageFunction[, options[, ...args]])
- `pageFunction` <[function]|[string]> Function to be evaluated in browser context
- `options` <[Object]> Optional waiting parameters
  - `polling` <[string]|[number]> An interval at which the `pageFunction` is executed, defaults to `raf`. If `polling` is a number, then it is treated as an interval in milliseconds at which the function would be executed. If `polling` is a string, then it can be one of the following values:
    - `raf` - to constantly execute `pageFunction` in `requestAnimationFrame` callback. This is the tightest polling mode which is suitable to observe styling changes.
    - `mutation` - to execute `pageFunction` on every DOM mutation.
  - `timeout` <[number]> maximum time to wait for in milliseconds. Defaults to `30000` (30 seconds). Pass `0` to disable timeout.
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to  `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves when the `pageFunction` returns a truthy value. It resolves to a JSHandle of the truthy value.

The `waitForFunction` can be used to observe viewport size change:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  const watchDog = page.waitForFunction('window.innerWidth < 100');
  await page.setViewport({width: 50, height: 50});
  await watchDog;
  await browser.close();
});
```

To pass arguments from node.js to the predicate of `page.waitForFunction` function:

```js
const selector = '.foo';
await page.waitForFunction(selector => !!document.querySelector(selector), {}, selector);
```

Shortcut for [page.mainFrame().waitForFunction(pageFunction[, options[, ...args]])](#framewaitforfunctionpagefunction-options-args).

#### page.waitForNavigation(options)
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
- returns: <[Promise]<?[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect. In case of navigation to a different anchor or navigation due to History API usage, the navigation will resolve with `null`.

This resolves when the page navigates to a new URL or reloads. It is useful for when you run code
which will indirectly cause the page to navigate. Consider this example:

```js
const [response] = await Promise.all([
  page.waitForNavigation(), // The promise resolves after navigation has finished
  page.click('a.my-link'), // Clicking the link will indirectly cause a navigation
]);
```

**NOTE** Usage of the [History API](https://developer.mozilla.org/en-US/docs/Web/API/History_API) to change the URL is considered a navigation.

Shortcut for [page.mainFrame().waitForNavigation(options)](#framewaitfornavigationoptions).

#### page.waitForRequest(urlOrPredicate, options)
- `urlOrPredicate` <[string]|[Function]> A URL or predicate to wait for.
- `options` <[Object]> Optional waiting parameters
  - `timeout` <[number]> Maximum wait time in milliseconds, defaults to 30 seconds, pass `0` to disable the timeout.
- returns: <[Promise]<[Request]>> Promise which resolves to the matched request.

```js
const firstRequest = await page.waitForRequest('http://example.com/resource');
const finalRequest = await page.waitForRequest(request => request.url() === 'http://example.com' && request.method() === 'GET');
return firstRequest.url();
```

#### page.waitForResponse(urlOrPredicate, options)
- `urlOrPredicate` <[string]|[Function]> A URL or predicate to wait for.
- `options` <[Object]> Optional waiting parameters
  - `timeout` <[number]> Maximum wait time in milliseconds, defaults to 30 seconds, pass `0` to disable the timeout.
- returns: <[Promise]<[Response]>> Promise which resolves to the matched response.

```js
const firstResponse = await page.waitForResponse('https://example.com/resource');
const finalResponse = await page.waitForResponse(response => response.url() === 'https://example.com' && response.status() === 200);
return finalResponse.ok();
```

#### page.waitForSelector(selector[, options])
- `selector` <[string]> A [selector] of an element to wait for
- `options` <[Object]> Optional waiting parameters
  - `visible` <[boolean]> wait for element to be present in DOM and to be visible, i.e. to not have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `hidden` <[boolean]> wait for element to not be found in the DOM or to be hidden, i.e. have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `timeout` <[number]> maximum time to wait for in milliseconds. Defaults to `30000` (30 seconds). Pass `0` to disable timeout.
- returns: <[Promise]<[ElementHandle]>> Promise which resolves when element specified by selector string is added to DOM.

Wait for the `selector` to appear in page. If at the moment of calling
the method the `selector` already exists, the method will return
immediately. If the selector doesn't appear after the `timeout` milliseconds of waiting, the function will throw.

This method works across navigations:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  let currentURL;
  page
    .waitForSelector('img')
    .then(() => console.log('First URL with image: ' + currentURL));
  for (currentURL of ['https://example.com', 'https://google.com', 'https://bbc.com'])
    await page.goto(currentURL);
  await browser.close();
});
```
Shortcut for [page.mainFrame().waitForSelector(selector[, options])](#framewaitforselectorselector-options).

#### page.waitForXPath(xpath[, options])
- `xpath` <[string]> A [xpath] of an element to wait for
- `options` <[Object]> Optional waiting parameters
  - `visible` <[boolean]> wait for element to be present in DOM and to be visible, i.e. to not have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `hidden` <[boolean]> wait for element to not be found in the DOM or to be hidden, i.e. have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `timeout` <[number]> maximum time to wait for in milliseconds. Defaults to `30000` (30 seconds). Pass `0` to disable timeout.
- returns: <[Promise]<[ElementHandle]>> Promise which resolves when element specified by xpath string is added to DOM.

Wait for the `xpath` to appear in page. If at the moment of calling
the method the `xpath` already exists, the method will return
immediately. If the xpath doesn't appear after the `timeout` milliseconds of waiting, the function will throw.

This method works across navigations:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  let currentURL;
  page
    .waitForXPath('//img')
    .then(() => console.log('First URL with image: ' + currentURL));
  for (currentURL of ['https://example.com', 'https://google.com', 'https://bbc.com'])
    await page.goto(currentURL);
  await browser.close();
});
```
Shortcut for [page.mainFrame().waitForXPath(xpath[, options])](#framewaitforxpathxpath-options).

#### page.workers()
- returns: <[Array]<[Worker]>>
This method returns all of the dedicated [WebWorkers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API) associated with the page.

> **NOTE** This does not contain ServiceWorkers

### class: Worker

The Worker class represents a [WebWorker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API).
The events `workercreated` and `workerdestroyed` are emitted on the page object to signal the worker lifecycle.

```js
page.on('workercreated', worker => console.log('Worker created: ' + worker.url()));
page.on('workerdestroyed', worker => console.log('Worker destroyed: ' + worker.url()));

console.log('Current workers:');
for (const worker of page.workers())
  console.log('  ' + worker.url());
```

#### worker.evaluate(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in the worker context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

If the function passed to the `worker.evaluate` returns a [Promise], then `worker.evaluate` would wait for the promise to resolve and return its value.

If the function passed to the `worker.evaluate` returns a non-[Serializable] value, then `worker.evaluate` resolves to `undefined`.

Shortcut for [(await worker.executionContext()).evaluate(pageFunction, ...args)](#executioncontextevaluatepagefunction-args).

#### worker.evaluateHandle(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in the page context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves to the return value of `pageFunction` as in-page object (JSHandle)

The only difference between `worker.evaluate` and `worker.evaluateHandle` is that `worker.evaluateHandle` returns in-page object (JSHandle).

If the function passed to the `worker.evaluateHandle` returns a [Promise], then `worker.evaluateHandle` would wait for the promise to resolve and return its value.

Shortcut for [(await worker.executionContext()).evaluateHandle(pageFunction, ...args)](#executioncontextevaluatehandlepagefunction-args).

#### worker.executionContext()
- returns: <[Promise]<[ExecutionContext]>>

#### worker.url()
- returns: <[string]>

### class: Accessibility

The Accessibility class provides methods for inspecting Chromium's accessibility tree. The accessibility tree is used by assistive technology such as [screen readers](https://en.wikipedia.org/wiki/Screen_reader).

Accessibility is a very platform-specific thing. On different platforms, there are different screen readers that might have wildly different output.

Blink - Chrome's rendering engine - has a concept of "accessibility tree", which is than translated into different platform-specific APIs. Accessibility namespace gives users
access to the Blink Accessibility Tree.

Most of the accessibility tree gets filtered out when converting from Blink AX Tree to Platform-specific AX-Tree or by screen readers themselves. By default, Puppeteer tries to approximate this filtering, exposing only the "interesting" nodes of the tree.



#### accessibility.snapshot([options])
- `options` <[Object]>
  - `interestingOnly` <[boolean]> Prune uninteresting nodes from the tree. Defaults to `true`.
- returns: <[Promise]<[Object]>> Returns an [AXNode] object with the following properties:
  - `role` <[string]> The [role](https://www.w3.org/TR/wai-aria/#usage_intro).
  - `name` <[string]> A human readable name for the node.
  - `value` <[string]|[number]> The current value of the node.
  - `description` <[string]> An additional human readable description of the node.
  - `keyshortcuts` <[string]> Keyboard shortcuts associated with this node.
  - `roledescription` <[string]> A human readable alternative to the role.
  - `valuetext` <[string]> A description of the current value.
  - `disabled` <[boolean]> Whether the node is disabled.
  - `expanded` <[boolean]> Whether the node is expanded or collapsed.
  - `focused` <[boolean]> Whether the node is focused.
  - `modal` <[boolean]> Whether the node is [modal](https://en.wikipedia.org/wiki/Modal_window).
  - `multiline` <[boolean]> Whether the node text input supports multiline.
  - `multiselectable` <[boolean]> Whether more than one child can be selected.
  - `readonly` <[boolean]> Whether the node is read only.
  - `required` <[boolean]> Whether the node is required.
  - `selected` <[boolean]> Whether the node is selected in its parent node.
  - `checked` <[boolean]|"mixed"> Whether the checkbox is checked, or "mixed".
  - `pressed` <[boolean]|"mixed"> Whether the toggle button is checked, or "mixed".
  - `level` <[number]> The level of a heading.
  - `valuemin` <[number]> The minimum value in a node.
  - `valuemax` <[number]> The maximum value in a node.
  - `autocomplete` <[string]> What kind of autocomplete is supported by a control.
  - `haspopup` <[string]> What kind of popup is currently being shown for a node.
  - `invalid` <[string]> Whether and in what way this node's value is invalid.
  - `orientation` <[string]> Whether the node is oriented horizontally or vertically.
  - `children` <[Array]<[Object]>> Child [AXNode]s of this node, if any.

Captures the current state of the accessibility tree. The returned object represents the root accessible node of the page.

> **NOTE** The Chromium accessibility tree contains nodes that go unused on most platforms and by
most screen readers. Puppeteer will discard them as well for an easier to process tree,
unless `interestingOnly` is set to `false`.

An example of dumping the entire accessibility tree:
```js
const snapshot = await page.accessibility.snapshot();
console.log(snapshot);
```

An example of logging the focused node's name:
```js
const snapshot = await page.accessibility.snapshot();
const node = findFocusedNode(snapshot);
console.log(node && node.name);

function findFocusedNode(node) {
  if (node.focused)
    return node;
  for (const child of node.children || []) {
    const foundNode = findFocusedNode(child);
    return foundNode;
  }
  return null;
}
```

### class: Keyboard

Keyboard provides an api for managing a virtual keyboard. The high level api is [`keyboard.type`](#keyboardtypetext-options), which takes raw characters and generates proper keydown, keypress/input, and keyup events on your page.

For finer control, you can use [`keyboard.down`](#keyboarddownkey-options), [`keyboard.up`](#keyboardupkey), and [`keyboard.sendCharacter`](#keyboardsendcharacterchar) to manually fire events as if they were generated from a real keyboard.

An example of holding down `Shift` in order to select and delete some text:
```js
await page.keyboard.type('Hello World!');
await page.keyboard.press('ArrowLeft');

await page.keyboard.down('Shift');
for (let i = 0; i < ' World'.length; i++)
  await page.keyboard.press('ArrowLeft');
await page.keyboard.up('Shift');

await page.keyboard.press('Backspace');
// Result text will end up saying 'Hello!'
```

An example of pressing `A`
```js
await page.keyboard.down('Shift');
await page.keyboard.press('KeyA');
await page.keyboard.up('Shift');
```

> **NOTE** On MacOS, keyboard shortcuts like `⌘ A` -> Select All do not work. See [#1313](https://github.com/GoogleChrome/puppeteer/issues/1313)

#### keyboard.down(key[, options])
- `key` <[string]> Name of key to press, such as `ArrowLeft`. See [USKeyboardLayout] for a list of all key names.
- `options` <[Object]>
  - `text` <[string]> If specified, generates an input event with this text.
- returns: <[Promise]>

Dispatches a `keydown` event.

If `key` is a single character and no modifier keys besides `Shift` are being held down, a `keypress`/`input` event will also generated. The `text` option can be specified to force an input event to be generated.

If `key` is a modifier key, `Shift`, `Meta`, `Control`, or `Alt`, subsequent key presses will be sent with that modifier active. To release the modifier key, use [`keyboard.up`](#keyboardupkey).

After the key is pressed once, subsequent calls to [`keyboard.down`](#keyboarddownkey-options) will have [repeat](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/repeat) set to true. To release the key, use [`keyboard.up`](#keyboardupkey).

> **NOTE** Modifier keys DO influence `keyboard.down`. Holding down `Shift` will type the text in upper case.

#### keyboard.press(key[, options])
- `key` <[string]> Name of key to press, such as `ArrowLeft`. See [USKeyboardLayout] for a list of all key names.
- `options` <[Object]>
  - `text` <[string]> If specified, generates an input event with this text.
  - `delay` <[number]> Time to wait between `keydown` and `keyup` in milliseconds. Defaults to 0.
- returns: <[Promise]>

If `key` is a single character and no modifier keys besides `Shift` are being held down, a `keypress`/`input` event will also generated. The `text` option can be specified to force an input event to be generated.

> **NOTE** Modifier keys DO effect `keyboard.press`. Holding down `Shift` will type the text in upper case.

Shortcut for [`keyboard.down`](#keyboarddownkey-options) and [`keyboard.up`](#keyboardupkey).

#### keyboard.sendCharacter(char)
- `char` <[string]> Character to send into the page.
- returns: <[Promise]>

Dispatches a `keypress` and `input` event. This does not send a `keydown` or `keyup` event.

```js
page.keyboard.sendCharacter('嗨');
```

> **NOTE** Modifier keys DO NOT effect `keyboard.sendCharacter`. Holding down `Shift` will not type the text in upper case.

#### keyboard.type(text, options)
- `text` <[string]> A text to type into a focused element.
- `options` <[Object]>
  - `delay` <[number]> Time to wait between key presses in milliseconds. Defaults to 0.
- returns: <[Promise]>

Sends a `keydown`, `keypress`/`input`, and `keyup` event for each character in the text.

To press a special key, like `Control` or `ArrowDown`, use [`keyboard.press`](#keyboardpresskey-options).

```js
page.keyboard.type('Hello'); // Types instantly
page.keyboard.type('World', {delay: 100}); // Types slower, like a user
```

> **NOTE** Modifier keys DO NOT effect `keyboard.type`. Holding down `Shift` will not type the text in upper case.

#### keyboard.up(key)
- `key` <[string]> Name of key to release, such as `ArrowLeft`. See [USKeyboardLayout] for a list of all key names.
- returns: <[Promise]>

Dispatches a `keyup` event.

### class: Mouse

The Mouse class operates in main-frame CSS pixels relative to the top-left corner of the viewport.

Every `page` object has its own Mouse, accessible with [`page.mouse`](#pagemouse).

```js
// Using ‘page.mouse’ to trace a 100x100 square.
await page.mouse.move(0, 0);
await page.mouse.down();
await page.mouse.move(0, 100);
await page.mouse.move(100, 100);
await page.mouse.move(100, 0);
await page.mouse.move(0, 0);
await page.mouse.up();
```

#### mouse.click(x, y, [options])
- `x` <[number]>
- `y` <[number]>
- `options` <[Object]>
  - `button` <[string]> `left`, `right`, or `middle`, defaults to `left`.
  - `clickCount` <[number]> defaults to 1. See [UIEvent.detail].
  - `delay` <[number]> Time to wait between `mousedown` and `mouseup` in milliseconds. Defaults to 0.
- returns: <[Promise]>

Shortcut for [`mouse.move`](#mousemovex-y-options), [`mouse.down`](#mousedownoptions) and [`mouse.up`](#mouseupoptions).

#### mouse.down([options])
- `options` <[Object]>
  - `button` <[string]> `left`, `right`, or `middle`, defaults to `left`.
  - `clickCount` <[number]> defaults to 1. See [UIEvent.detail].
- returns: <[Promise]>

Dispatches a `mousedown` event.

#### mouse.move(x, y, [options])
- `x` <[number]>
- `y` <[number]>
- `options` <[Object]>
  - `steps` <[number]> defaults to 1. Sends intermediate `mousemove` events.
- returns: <[Promise]>

Dispatches a `mousemove` event.

#### mouse.up([options])
- `options` <[Object]>
  - `button` <[string]> `left`, `right`, or `middle`, defaults to `left`.
  - `clickCount` <[number]> defaults to 1. See [UIEvent.detail].
- returns: <[Promise]>

Dispatches a `mouseup` event.

### class: Touchscreen

#### touchscreen.tap(x, y)
- `x` <[number]>
- `y` <[number]>
- returns: <[Promise]>

Dispatches a `touchstart` and `touchend` event.

### class: Tracing

You can use [`tracing.start`](#tracingstartoptions) and [`tracing.stop`](#tracingstop) to create a trace file which can be opened in Chrome DevTools or [timeline viewer](https://chromedevtools.github.io/timeline-viewer/).

```js
await page.tracing.start({path: 'trace.json'});
await page.goto('https://www.google.com');
await page.tracing.stop();
```

#### tracing.start(options)
- `options` <[Object]>
  - `path` <[string]> A path to write the trace file to.
  - `screenshots` <[boolean]> captures screenshots in the trace.
  - `categories` <[Array]<[string]>> specify custom categories to use instead of default.
- returns: <[Promise]>

Only one trace can be active at a time per browser.

#### tracing.stop()
- returns: <[Promise]<[Buffer]>> Promise which resolves to buffer with trace data.

### class: Dialog

[Dialog] objects are dispatched by page via the ['dialog'](#event-dialog) event.

An example of using `Dialog` class:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  page.on('dialog', async dialog => {
    console.log(dialog.message());
    await dialog.dismiss();
    await browser.close();
  });
  page.evaluate(() => alert('1'));
});
```

#### dialog.accept([promptText])
- `promptText` <[string]> A text to enter in prompt. Does not cause any effects if the dialog's `type` is not prompt.
- returns: <[Promise]> Promise which resolves when the dialog has been accepted.

#### dialog.defaultValue()
- returns: <[string]> If dialog is prompt, returns default prompt value. Otherwise, returns empty string.

#### dialog.dismiss()
- returns: <[Promise]> Promise which resolves when the dialog has been dismissed.

#### dialog.message()
- returns: <[string]> A message displayed in the dialog.

#### dialog.type()
- returns: <[string]> Dialog's type, can be one of `alert`, `beforeunload`, `confirm` or `prompt`.

### class: ConsoleMessage

[ConsoleMessage] objects are dispatched by page via the ['console'](#event-console) event.

#### consoleMessage.args()
- returns: <[Array]<[JSHandle]>>

#### consoleMessage.text()
- returns: <[string]>

#### consoleMessage.type()
- returns: <[string]>

One of the following values: `'log'`, `'debug'`, `'info'`, `'error'`, `'warning'`, `'dir'`, `'dirxml'`, `'table'`, `'trace'`, `'clear'`, `'startGroup'`, `'startGroupCollapsed'`, `'endGroup'`, `'assert'`, `'profile'`, `'profileEnd'`, `'count'`, `'timeEnd'`.

### class: Frame

At every point of time, page exposes its current frame tree via the [page.mainFrame()](#pagemainframe) and [frame.childFrames()](#framechildframes) methods.

[Frame] object's lifecycle is controlled by three events, dispatched on the page object:
- ['frameattached'](#event-frameattached) - fired when the frame gets attached to the page. A Frame can be attached to the page only once.
- ['framenavigated'](#event-framenavigated) - fired when the frame commits navigation to a different URL.
- ['framedetached'](#event-framedetached) - fired when the frame gets detached from the page.  A Frame can be detached from the page only once.

An example of dumping frame tree:

```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.goto('https://www.google.com/chrome/browser/canary.html');
  dumpFrameTree(page.mainFrame(), '');
  await browser.close();

  function dumpFrameTree(frame, indent) {
    console.log(indent + frame.url());
    for (let child of frame.childFrames())
      dumpFrameTree(child, indent + '  ');
  }
});
```

An example of getting text from an iframe element:

```js
  const frame = page.frames().find(frame => frame.name() === 'myframe');
  const text = await frame.$eval('.selector', element => element.textContent);
  console.log(text);
```

#### frame.$(selector)
- `selector` <[string]> A [selector] to query frame for
- returns: <[Promise]<?[ElementHandle]>> Promise which resolves to ElementHandle pointing to the frame element.

The method queries frame for the selector. If there's no such element within the frame, the method will resolve to `null`.

#### frame.$$(selector)
- `selector` <[string]> A [selector] to query frame for
- returns: <[Promise]<[Array]<[ElementHandle]>>> Promise which resolves to ElementHandles pointing to the frame elements.

The method runs `document.querySelectorAll` within the frame. If no elements match the selector, the return value resolves to `[]`.

#### frame.$$eval(selector, pageFunction[, ...args])
- `selector` <[string]> A [selector] to query frame for
- `pageFunction` <[function]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

This method runs `Array.from(document.querySelectorAll(selector))` within the frame and passes it as the first argument to `pageFunction`.

If `pageFunction` returns a [Promise], then `frame.$$eval` would wait for the promise to resolve and return its value.

Examples:
```js
const divsCounts = await frame.$$eval('div', divs => divs.length);
```

#### frame.$eval(selector, pageFunction[, ...args])
- `selector` <[string]> A [selector] to query frame for
- `pageFunction` <[function]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

This method runs `document.querySelector` within the frame and passes it as the first argument to `pageFunction`. If there's no element matching `selector`, the method throws an error.

If `pageFunction` returns a [Promise], then `frame.$eval` would wait for the promise to resolve and return its value.

Examples:
```js
const searchValue = await frame.$eval('#search', el => el.value);
const preloadHref = await frame.$eval('link[rel=preload]', el => el.href);
const html = await frame.$eval('.main-container', e => e.outerHTML);
```

#### frame.$x(expression)
- `expression` <[string]> Expression to [evaluate](https://developer.mozilla.org/en-US/docs/Web/API/Document/evaluate).
- returns: <[Promise]<[Array]<[ElementHandle]>>>

The method evaluates the XPath expression.

#### frame.addScriptTag(options)
- `options` <[Object]>
  - `url` <[string]> URL of a script to be added.
  - `path` <[string]> Path to the JavaScript file to be injected into frame. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd).
  - `content` <[string]> Raw JavaScript content to be injected into frame.
  - `type` <[string]> Script type. Use 'module' in order to load a Javascript ES6 module. See [script](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) for more details.
- returns: <[Promise]<[ElementHandle]>> which resolves to the added tag when the script's onload fires or when the script content was injected into frame.

Adds a `<script>` tag into the page with the desired url or content.

#### frame.addStyleTag(options)
- `options` <[Object]>
  - `url` <[string]> URL of the `<link>` tag.
  - `path` <[string]> Path to the CSS file to be injected into frame. If `path` is a relative path, then it is resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd).
  - `content` <[string]> Raw CSS content to be injected into frame.
- returns: <[Promise]<[ElementHandle]>> which resolves to the added tag when the stylesheet's onload fires or when the CSS content was injected into frame.

Adds a `<link rel="stylesheet">` tag into the page with the desired url or a `<style type="text/css">` tag with the content.

#### frame.childFrames()
- returns: <[Array]<[Frame]>>

#### frame.click(selector[, options])
- `selector` <[string]> A [selector] to search for element to click. If there are multiple elements satisfying the selector, the first will be clicked.
- `options` <[Object]>
  - `button` <[string]> `left`, `right`, or `middle`, defaults to `left`.
  - `clickCount` <[number]> defaults to 1. See [UIEvent.detail].
  - `delay` <[number]> Time to wait between `mousedown` and `mouseup` in milliseconds. Defaults to 0.
- returns: <[Promise]> Promise which resolves when the element matching `selector` is successfully clicked. The Promise will be rejected if there is no element matching `selector`.

This method fetches an element with `selector`, scrolls it into view if needed, and then uses [page.mouse](#pagemouse) to click in the center of the element.
If there's no element matching `selector`, the method throws an error.

Bear in mind that if `click()` triggers a navigation event and there's a separate `page.waitForNavigation()` promise to be resolved, you may end up with a race condition that yields unexpected results. The correct pattern for click and wait for navigation is the following:

```javascript
const [response] = await Promise.all([
  page.waitForNavigation(waitOptions),
  frame.click(selector, clickOptions),
]);
```

#### frame.content()
- returns: <[Promise]<[string]>>

Gets the full HTML contents of the frame, including the doctype.

#### frame.evaluate(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to  `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

If the function passed to the `frame.evaluate` returns a [Promise], then `frame.evaluate` would wait for the promise to resolve and return its value.

If the function passed to the `frame.evaluate` returns a non-[Serializable] value, then `frame.evaluate` resolves to `undefined`.

```js
const result = await frame.evaluate(() => {
  return Promise.resolve(8 * 7);
});
console.log(result); // prints "56"
```

A string can also be passed in instead of a function.

```js
console.log(await frame.evaluate('1 + 2')); // prints "3"
```

[ElementHandle] instances can be passed as arguments to the `frame.evaluate`:
```js
const bodyHandle = await frame.$('body');
const html = await frame.evaluate(body => body.innerHTML, bodyHandle);
await bodyHandle.dispose();
```

#### frame.evaluateHandle(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in the page context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves to the return value of `pageFunction` as in-page object (JSHandle)

The only difference between `frame.evaluate` and `frame.evaluateHandle` is that `frame.evaluateHandle` returns in-page object (JSHandle).

If the function, passed to the `frame.evaluateHandle`, returns a [Promise], then `frame.evaluateHandle` would wait for the promise to resolve and return its value.

```js
const aWindowHandle = await frame.evaluateHandle(() => Promise.resolve(window));
aWindowHandle; // Handle for the window object.
```

A string can also be passed in instead of a function.

```js
const aHandle = await frame.evaluateHandle('document'); // Handle for the 'document'.
```

[JSHandle] instances can be passed as arguments to the `frame.evaluateHandle`:
```js
const aHandle = await frame.evaluateHandle(() => document.body);
const resultHandle = await frame.evaluateHandle(body => body.innerHTML, aHandle);
console.log(await resultHandle.jsonValue());
await resultHandle.dispose();
```


#### frame.executionContext()
- returns: <[Promise]<[ExecutionContext]>>

Returns promise that resolves to the frame's default execution context.

#### frame.focus(selector)
- `selector` <[string]> A [selector] of an element to focus. If there are multiple elements satisfying the selector, the first will be focused.
- returns: <[Promise]> Promise which resolves when the element matching `selector` is successfully focused. The promise will be rejected if there is no element matching `selector`.

This method fetches an element with `selector` and focuses it.
If there's no element matching `selector`, the method throws an error.

#### frame.goto(url, options)
- `url` <[string]> URL to navigate frame to. The url should include scheme, e.g. `https://`.
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
  - `referer` <[string]> Referer header value. If provided it will take preference over the referer header value set by [page.setExtraHTTPHeaders()](#pagesetextrahttpheadersheaders).
- returns: <[Promise]<?[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect.

The `frame.goto` will throw an error if:
- there's an SSL error (e.g. in case of self-signed certificates).
- target URL is invalid.
- the `timeout` is exceeded during navigation.
- the main resource failed to load.

> **NOTE** `frame.goto` either throw or return a main resource response. The only exceptions are navigation to `about:blank` or navigation to the same URL with a different hash, which would succeed and return `null`.

> **NOTE** Headless mode doesn't support navigation to a PDF document. See the [upstream issue](https://bugs.chromium.org/p/chromium/issues/detail?id=761295).


#### frame.hover(selector)
- `selector` <[string]> A [selector] to search for element to hover. If there are multiple elements satisfying the selector, the first will be hovered.
- returns: <[Promise]> Promise which resolves when the element matching `selector` is successfully hovered. Promise gets rejected if there's no element matching `selector`.

This method fetches an element with `selector`, scrolls it into view if needed, and then uses [page.mouse](#pagemouse) to hover over the center of the element.
If there's no element matching `selector`, the method throws an error.

#### frame.isDetached()
- returns: <[boolean]>

Returns `true` if the frame has been detached, or `false` otherwise.

#### frame.name()
- returns: <[string]>

Returns frame's name attribute as specified in the tag.

If the name is empty, returns the id attribute instead.

> **NOTE** This value is calculated once when the frame is created, and will not update if the attribute is changed later.

#### frame.parentFrame()
- returns: <?[Frame]> Returns parent frame, if any. Detached frames and main frames return `null`.

#### frame.select(selector, ...values)
- `selector` <[string]> A [selector] to query frame for
- `...values` <...[string]> Values of options to select. If the `<select>` has the `multiple` attribute, all values are considered, otherwise only the first one is taken into account.
- returns: <[Promise]<[Array]<[string]>>> Returns an array of option values that have been successfully selected.

Triggers a `change` and `input` event once all the provided options have been selected.
If there's no `<select>` element matching `selector`, the method throws an error.

```js
frame.select('select#colors', 'blue'); // single selection
frame.select('select#colors', 'red', 'green', 'blue'); // multiple selections
```

#### frame.setContent(html)
- `html` <[string]> HTML markup to assign to the page.
- returns: <[Promise]>

#### frame.tap(selector)
- `selector` <[string]> A [selector] to search for element to tap. If there are multiple elements satisfying the selector, the first will be tapped.
- returns: <[Promise]>

This method fetches an element with `selector`, scrolls it into view if needed, and then uses [page.touchscreen](#pagetouchscreen) to tap in the center of the element.
If there's no element matching `selector`, the method throws an error.

#### frame.title()
- returns: <[Promise]<[string]>> Returns page's title.

#### frame.type(selector, text[, options])
- `selector` <[string]> A [selector] of an element to type into. If there are multiple elements satisfying the selector, the first will be used.
- `text` <[string]> A text to type into a focused element.
- `options` <[Object]>
  - `delay` <[number]> Time to wait between key presses in milliseconds. Defaults to 0.
- returns: <[Promise]>

Sends a `keydown`, `keypress`/`input`, and `keyup` event for each character in the text.

To press a special key, like `Control` or `ArrowDown`, use [`keyboard.press`](#keyboardpresskey-options).

```js
frame.type('#mytextarea', 'Hello'); // Types instantly
frame.type('#mytextarea', 'World', {delay: 100}); // Types slower, like a user
```

#### frame.url()
- returns: <[string]>

Returns frame's url.

#### frame.waitFor(selectorOrFunctionOrTimeout[, options[, ...args]])
- `selectorOrFunctionOrTimeout` <[string]|[number]|[function]> A [selector], predicate or timeout to wait for
- `options` <[Object]> Optional waiting parameters
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to  `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves to a JSHandle of the success value

This method behaves differently with respect to the type of the first parameter:
- if `selectorOrFunctionOrTimeout` is a `string`, then the first argument is treated as a [selector] or [xpath], depending on whether or not it starts with '//', and the method is a shortcut for
  [frame.waitForSelector](#framewaitforselectorselector-options) or [frame.waitForXPath](#framewaitforxpathxpath-options)
- if `selectorOrFunctionOrTimeout` is a `function`, then the first argument is treated as a predicate to wait for and the method is a shortcut for [frame.waitForFunction()](#framewaitforfunctionpagefunction-options-args).
- if `selectorOrFunctionOrTimeout` is a `number`, then the first argument is treated as a timeout in milliseconds and the method returns a promise which resolves after the timeout
- otherwise, an exception is thrown

```js
// wait for selector
await page.waitFor('.foo');
// wait for 1 second
await page.waitFor(1000);
// wait for predicate
await page.waitFor(() => !!document.querySelector('.foo'));
```

To pass arguments from node.js to the predicate of `page.waitFor` function:

```js
const selector = '.foo';
await page.waitFor(selector => !!document.querySelector(selector), {}, selector);
```

#### frame.waitForFunction(pageFunction[, options[, ...args]])
- `pageFunction` <[function]|[string]> Function to be evaluated in browser context
- `options` <[Object]> Optional waiting parameters
  - `polling` <[string]|[number]> An interval at which the `pageFunction` is executed, defaults to `raf`. If `polling` is a number, then it is treated as an interval in milliseconds at which the function would be executed. If `polling` is a string, then it can be one of the following values:
    - `raf` - to constantly execute `pageFunction` in `requestAnimationFrame` callback. This is the tightest polling mode which is suitable to observe styling changes.
    - `mutation` - to execute `pageFunction` on every DOM mutation.
  - `timeout` <[number]> maximum time to wait for in milliseconds. Defaults to `30000` (30 seconds). Pass `0` to disable timeout.
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to  `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves when the `pageFunction` returns a truthy value. It resolves to a JSHandle of the truthy value.

The `waitForFunction` can be used to observe viewport size change:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  const watchDog = page.mainFrame().waitForFunction('window.innerWidth < 100');
  page.setViewport({width: 50, height: 50});
  await watchDog;
  await browser.close();
});
```

To pass arguments from node.js to the predicate of `page.waitForFunction` function:

```js
const selector = '.foo';
await page.waitForFunction(selector => !!document.querySelector(selector), {}, selector);
```

#### frame.waitForNavigation(options)
- `options` <[Object]> Navigation parameters which might have the following properties:
  - `timeout` <[number]> Maximum navigation time in milliseconds, defaults to 30 seconds, pass `0` to disable timeout. The default value can be changed by using the [page.setDefaultNavigationTimeout(timeout)](#pagesetdefaultnavigationtimeouttimeout) method.
  - `waitUntil` <[string]|[Array]<[string]>> When to consider navigation succeeded, defaults to `load`. Given an array of event strings, navigation is considered to be successful after all events have been fired. Events can be either:
    - `load` - consider navigation to be finished when the `load` event is fired.
    - `domcontentloaded` - consider navigation to be finished when the `DOMContentLoaded` event is fired.
    - `networkidle0` - consider navigation to be finished when there are no more than 0 network connections for at least `500` ms.
    - `networkidle2` - consider navigation to be finished when there are no more than 2 network connections for at least `500` ms.
- returns: <[Promise]<?[Response]>> Promise which resolves to the main resource response. In case of multiple redirects, the navigation will resolve with the response of the last redirect. In case of navigation to a different anchor or navigation due to History API usage, the navigation will resolve with `null`.

This resolves when the frame navigates to a new URL. It is useful for when you run code
which will indirectly cause the frame to navigate. Consider this example:

```js
const [response] = await Promise.all([
  frame.waitForNavigation(), // The navigation promise resolves after navigation has finished
  frame.click('a.my-link'), // Clicking the link will indirectly cause a navigation
]);
```

**NOTE** Usage of the [History API](https://developer.mozilla.org/en-US/docs/Web/API/History_API) to change the URL is considered a navigation.


#### frame.waitForSelector(selector[, options])
- `selector` <[string]> A [selector] of an element to wait for
- `options` <[Object]> Optional waiting parameters
  - `visible` <[boolean]> wait for element to be present in DOM and to be visible, i.e. to not have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `hidden` <[boolean]> wait for element to not be found in the DOM or to be hidden, i.e. have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `timeout` <[number]> maximum time to wait for in milliseconds. Defaults to `30000` (30 seconds). Pass `0` to disable timeout.
- returns: <[Promise]<[ElementHandle]>> Promise which resolves when element specified by selector string is added to DOM.

Wait for the `selector` to appear in page. If at the moment of calling
the method the `selector` already exists, the method will return
immediately. If the selector doesn't appear after the `timeout` milliseconds of waiting, the function will throw.

This method works across navigations:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  let currentURL;
  page.mainFrame()
    .waitForSelector('img')
    .then(() => console.log('First URL with image: ' + currentURL));
  for (currentURL of ['https://example.com', 'https://google.com', 'https://bbc.com'])
    await page.goto(currentURL);
  await browser.close();
});
```

#### frame.waitForXPath(xpath[, options])
- `xpath` <[string]> A [xpath] of an element to wait for
- `options` <[Object]> Optional waiting parameters
  - `visible` <[boolean]> wait for element to be present in DOM and to be visible, i.e. to not have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `hidden` <[boolean]> wait for element to not be found in the DOM or to be hidden, i.e. have `display: none` or `visibility: hidden` CSS properties. Defaults to `false`.
  - `timeout` <[number]> maximum time to wait for in milliseconds. Defaults to `30000` (30 seconds). Pass `0` to disable timeout.
- returns: <[Promise]<[ElementHandle]>> Promise which resolves when element specified by xpath string is added to DOM.

Wait for the `xpath` to appear in page. If at the moment of calling
the method the `xpath` already exists, the method will return
immediately. If the xpath doesn't appear after the `timeout` milliseconds of waiting, the function will throw.

This method works across navigations:
```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  let currentURL;
  page.mainFrame()
    .waitForXPath('//img')
    .then(() => console.log('First URL with image: ' + currentURL));
  for (currentURL of ['https://example.com', 'https://google.com', 'https://bbc.com'])
    await page.goto(currentURL);
  await browser.close();
});
```

### class: ExecutionContext

The class represents a context for JavaScript execution. A [Page] might have many execution contexts:
- each [frame](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) has "default" execution context that is
  always created after frame is attached to DOM. This context is returned by the [`frame.executionContext()`](#frameexecutioncontext) method.
- [Extensions](https://developer.chrome.com/extensions)'s content scripts create additional execution contexts.

Besides pages, execution contexts can be found in [workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API).

#### executionContext.evaluate(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in `executionContext`
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

If the function passed to the `executionContext.evaluate` returns a [Promise], then `executionContext.evaluate` would wait for the promise to resolve and return its value.

```js
const executionContext = await page.mainFrame().executionContext();
const result = await executionContext.evaluate(() => Promise.resolve(8 * 7));
console.log(result); // prints "56"
```

A string can also be passed in instead of a function.

```js
console.log(await executionContext.evaluate('1 + 2')); // prints "3"
```

[JSHandle] instances can be passed as arguments to the `executionContext.evaluate`:
```js
const oneHandle = await executionContext.evaluateHandle(() => 1);
const twoHandle = await executionContext.evaluateHandle(() => 2);
const result = await executionContext.evaluate((a, b) => a + b, oneHandle, twoHandle);
await oneHandle.dispose();
await twoHandle.dispose();
console.log(result); // prints '3'.
```

#### executionContext.evaluateHandle(pageFunction, ...args)
- `pageFunction` <[function]|[string]> Function to be evaluated in the `executionContext`
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[JSHandle]>> Promise which resolves to the return value of `pageFunction` as in-page object (JSHandle)

The only difference between `executionContext.evaluate` and `executionContext.evaluateHandle` is that `executionContext.evaluateHandle` returns in-page object (JSHandle).

If the function passed to the `executionContext.evaluateHandle` returns a [Promise], then `executionContext.evaluateHandle` would wait for the promise to resolve and return its value.

```js
const context = await page.mainFrame().executionContext();
const aHandle = await context.evaluateHandle(() => Promise.resolve(self));
aHandle; // Handle for the global object.
```

A string can also be passed in instead of a function.

```js
const aHandle = await context.evaluateHandle('1 + 2'); // Handle for the '3' object.
```

[JSHandle] instances can be passed as arguments to the `executionContext.evaluateHandle`:
```js
const aHandle = await context.evaluateHandle(() => document.body);
const resultHandle = await context.evaluateHandle(body => body.innerHTML, aHandle);
console.log(await resultHandle.jsonValue()); // prints body's innerHTML
await aHandle.dispose();
await resultHandle.dispose();
```

#### executionContext.frame()
- returns: <?[Frame]> Frame associated with this execution context.

> **NOTE** Not every execution context is associated with a frame. For example, workers and extensions have execution contexts that are not associated with frames.


#### executionContext.queryObjects(prototypeHandle)
- `prototypeHandle` <[JSHandle]> A handle to the object prototype.
- returns: <[Promise]<[JSHandle]>> A handle to an array of objects with this prototype

The method iterates the JavaScript heap and finds all the objects with the given prototype.

```js
// Create a Map object
await page.evaluate(() => window.map = new Map());
// Get a handle to the Map object prototype
const mapPrototype = await page.evaluateHandle(() => Map.prototype);
// Query all map instances into an array
const mapInstances = await page.queryObjects(mapPrototype);
// Count amount of map objects in heap
const count = await page.evaluate(maps => maps.length, mapInstances);
await mapInstances.dispose();
await mapPrototype.dispose();
```

### class: JSHandle

JSHandle represents an in-page JavaScript object. JSHandles can be created with the [page.evaluateHandle](#pageevaluatehandlepagefunction-args) method.

```js
const windowHandle = await page.evaluateHandle(() => window);
// ...
```

JSHandle prevents the referenced JavaScript object being garbage collected unless the handle is [disposed](#jshandledispose). JSHandles are auto-disposed when their origin frame gets navigated or the parent context gets destroyed.

JSHandle instances can be used as arguments in [`page.$eval()`](#pageevalselector-pagefunction-args), [`page.evaluate()`](#pageevaluatepagefunction-args) and [`page.evaluateHandle`](#pageevaluatehandlepagefunction-args) methods.

#### jsHandle.asElement()
- returns: <?[ElementHandle]>

Returns either `null` or the object handle itself, if the object handle is an instance of [ElementHandle].

#### jsHandle.dispose()
- returns: <[Promise]> Promise which resolves when the object handle is successfully disposed.

The `jsHandle.dispose` method stops referencing the element handle.

#### jsHandle.executionContext()
- returns: <[ExecutionContext]>

Returns execution context the handle belongs to.

#### jsHandle.getProperties()
- returns: <[Promise]<[Map]<[string], [JSHandle]>>>

The method returns a map with property names as keys and JSHandle instances for the property values.

```js
const handle = await page.evaluateHandle(() => ({window, document}));
const properties = await handle.getProperties();
const windowHandle = properties.get('window');
const documentHandle = properties.get('document');
await handle.dispose();
```

#### jsHandle.getProperty(propertyName)
- `propertyName` <[string]> property to get
- returns: <[Promise]<[JSHandle]>>

Fetches a single property from the referenced object.

#### jsHandle.jsonValue()
- returns: <[Promise]<[Object]>>

Returns a JSON representation of the object. If the object has a
[`toJSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify#toJSON()_behavior)
function, it **will not be called**.

> **NOTE** The method will return an empty JSON object if the referenced object is not stringifiable. It will throw an error if the object has circular references.

### class: ElementHandle

> **NOTE** Class [ElementHandle] extends [JSHandle].

ElementHandle represents an in-page DOM element. ElementHandles can be created with the [page.$](#pageselector) method.

```js
const puppeteer = require('puppeteer');

puppeteer.launch().then(async browser => {
  const page = await browser.newPage();
  await page.goto('https://google.com');
  const inputElement = await page.$('input[type=submit]');
  await inputElement.click();
  // ...
});
```

ElementHandle prevents DOM element from garbage collection unless the handle is [disposed](#elementhandledispose). ElementHandles are auto-disposed when their origin frame gets navigated.

ElementHandle instances can be used as arguments in [`page.$eval()`](#pageevalselector-pagefunction-args) and [`page.evaluate()`](#pageevaluatepagefunction-args) methods.

#### elementHandle.$(selector)
- `selector` <[string]> A [selector] to query element for
- returns: <[Promise]<?[ElementHandle]>>

The method runs `element.querySelector` within the page. If no element matches the selector, the return value resolves to `null`.

#### elementHandle.$$(selector)
- `selector` <[string]> A [selector] to query element for
- returns: <[Promise]<[Array]<[ElementHandle]>>>

The method runs `element.querySelectorAll` within the page. If no elements match the selector, the return value resolves to `[]`.

#### elementHandle.$$eval(selector, pageFunction, ...args)
- `selector` <[string]> A [selector] to query page for
- `pageFunction` <[function]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

This method runs `document.querySelectorAll` within the element and passes it as the first argument to `pageFunction`. If there's no element matching `selector`, the method throws an error.

If `pageFunction` returns a [Promise], then `frame.$$eval` would wait for the promise to resolve and return its value.

Examples:
```html
<div class="feed">
  <div class="tweet">Hello!</div>
  <div class="tweet">Hi!</div>
</div>
```
```js
const feedHandle = await page.$('.feed');
expect(await feedHandle.$$eval('.tweet', nodes => nodes.map(n => n.innerText))).toEqual(['Hello!', 'Hi!']);
```

#### elementHandle.$eval(selector, pageFunction, ...args)
- `selector` <[string]> A [selector] to query page for
- `pageFunction` <[function]> Function to be evaluated in browser context
- `...args` <...[Serializable]|[JSHandle]> Arguments to pass to `pageFunction`
- returns: <[Promise]<[Serializable]>> Promise which resolves to the return value of `pageFunction`

This method runs `document.querySelector` within the element and passes it as the first argument to `pageFunction`. If there's no element matching `selector`, the method throws an error.

If `pageFunction` returns a [Promise], then `frame.$eval` would wait for the promise to resolve and return its value.

Examples:
```js
const tweetHandle = await page.$('.tweet');
expect(await tweetHandle.$eval('.like', node => node.innerText)).toBe('100');
expect(await tweetHandle.$eval('.retweets', node => node.innerText)).toBe('10');
```

#### elementHandle.$x(expression)
- `expression` <[string]> Expression to [evaluate](https://developer.mozilla.org/en-US/docs/Web/API/Document/evaluate).
- returns: <[Promise]<[Array]<[ElementHandle]>>>

The method evaluates the XPath expression relative to the elementHandle. If there are no such elements, the method will resolve to an empty array.

#### elementHandle.asElement()
- returns: <[ElementHandle]>

#### elementHandle.boundingBox()
- returns: <[Promise]<?[Object]>>
  - x <[number]> the x coordinate of the element in pixels.
  - y <[number]> the y coordinate of the element in pixels.
  - width <[number]> the width of the element in pixels.
  - height <[number]> the height of the element in pixels.

This method returns the bounding box of the element (relative to the main frame), or `null` if the element is not visible.

#### elementHandle.boxModel()
- returns: <[Promise]<?[Object]>>
  - content <[Array]<[Object]>> Content box.
    - x <[number]>
    - y <[number]>
  - padding <[Array]<[Object]>> Padding box.
    - x <[number]>
    - y <[number]>
  - border <[Array]<[Object]>> Border box.
    - x <[number]>
    - y <[number]>
  - margin <[Array]<[Object]>> Margin box.
    - x <[number]>
    - y <[number]>
  - width <[number]> Element's width.
  - height <[number]> Element's height.

This method returns boxes of the element, or `null` if the element is not visible. Boxes are represented as an array of points; each Point is an object `{x, y}`. Box points are sorted clock-wise.

#### elementHandle.click([options])
- `options` <[Object]>
  - `button` <[string]> `left`, `right`, or `middle`, defaults to `left`.
  - `clickCount` <[number]> defaults to 1. See [UIEvent.detail].
  - `delay` <[number]> Time to wait between `mousedown` and `mouseup` in milliseconds. Defaults to 0.
- returns: <[Promise]> Promise which resolves when the element is successfully clicked. Promise gets rejected if the element is detached from DOM.

This method scrolls element into view if needed, and then uses [page.mouse](#pagemouse) to click in the center of the element.
If the element is detached from DOM, the method throws an error.

#### elementHandle.contentFrame()
- returns: <[Promise]<?[Frame]>> Resolves to the content frame for element handles referencing iframe nodes, or null otherwise

#### elementHandle.dispose()
- returns: <[Promise]> Promise which resolves when the element handle is successfully disposed.

The `elementHandle.dispose` method stops referencing the element handle.

#### elementHandle.executionContext()
- returns: <[ExecutionContext]>

#### elementHandle.focus()
- returns: <[Promise]>

Calls [focus](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/focus) on the element.

#### elementHandle.getProperties()
- returns: <[Promise]<[Map]<[string], [JSHandle]>>>

The method returns a map with property names as keys and JSHandle instances for the property values.

```js
const listHandle = await page.evaluateHandle(() => document.body.children);
const properties = await listHandle.getProperties();
const children = [];
for (const property of properties.values()) {
  const element = property.asElement();
  if (element)
    children.push(element);
}
children; // holds elementHandles to all children of document.body
```

#### elementHandle.getProperty(propertyName)
- `propertyName` <[string]> property to get
- returns: <[Promise]<[JSHandle]>>

Fetches a single property from the objectHandle.

#### elementHandle.hover()
- returns: <[Promise]> Promise which resolves when the element is successfully hovered.

This method scrolls element into view if needed, and then uses [page.mouse](#pagemouse) to hover over the center of the element.
If the element is detached from DOM, the method throws an error.

#### elementHandle.isIntersectingViewport()
- returns: <[Promise]<[boolean]>> Resolves to true if the element is visible in the current viewport.

#### elementHandle.jsonValue()
- returns: <[Promise]<[Object]>>

Returns a JSON representation of the object. The JSON is generated by running [`JSON.stringify`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) on the object in page and consequent [`JSON.parse`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) in puppeteer.

> **NOTE** The method will throw if the referenced object is not stringifiable.

#### elementHandle.press(key[, options])
- `key` <[string]> Name of key to press, such as `ArrowLeft`. See [USKeyboardLayout] for a list of all key names.
- `options` <[Object]>
  - `text` <[string]> If specified, generates an input event with this text.
  - `delay` <[number]> Time to wait between `keydown` and `keyup` in milliseconds. Defaults to 0.
- returns: <[Promise]>

Focuses the element, and then uses [`keyboard.down`](#keyboarddownkey-options) and [`keyboard.up`](#keyboardupkey).

If `key` is a single character and no modifier keys besides `Shift` are being held down, a `keypress`/`input` event will also be generated. The `text` option can be specified to force an input event to be generated.

> **NOTE** Modifier keys DO effect `elementHandle.press`. Holding down `Shift` will type the text in upper case.

#### elementHandle.screenshot([options])
- `options` <[Object]> Same options as in [page.screenshot](#pagescreenshotoptions).
- returns: <[Promise]<[string]|[Buffer]>> Promise which resolves to buffer or a base64 string (depending on the value of `options.encoding`) with captured screenshot.

This method scrolls element into view if needed, and then uses [page.screenshot](#pagescreenshotoptions) to take a screenshot of the element.
If the element is detached from DOM, the method throws an error.

#### elementHandle.tap()
- returns: <[Promise]> Promise which resolves when the element is successfully tapped. Promise gets rejected if the element is detached from DOM.

This method scrolls element into view if needed, and then uses [touchscreen.tap](#touchscreentapx-y) to tap in the center of the element.
If the element is detached from DOM, the method throws an error.

#### elementHandle.toString()
- returns: <[string]>

#### elementHandle.type(text[, options])
- `text` <[string]> A text to type into a focused element.
- `options` <[Object]>
  - `delay` <[number]> Time to wait between key presses in milliseconds. Defaults to 0.
- returns: <[Promise]>

Focuses the element, and then sends a `keydown`, `keypress`/`input`, and `keyup` event for each character in the text.

To press a special key, like `Control` or `ArrowDown`, use [`elementHandle.press`](#elementhandlepresskey-options).

```js
elementHandle.type('Hello'); // Types instantly
elementHandle.type('World', {delay: 100}); // Types slower, like a user
```

An example of typing into a text field and then submitting the form:
```js
const elementHandle = await page.$('input');
await elementHandle.type('some text');
await elementHandle.press('Enter');
```

#### elementHandle.uploadFile(...filePaths)
- `...filePaths` <...[string]> Sets the value of the file input these paths. If some of the  `filePaths` are relative paths, then they are resolved relative to [current working directory](https://nodejs.org/api/process.html#process_process_cwd).
- returns: <[Promise]>

This method expects `elementHandle` to point to an [input element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input).

### class: Request

Whenever the page sends a request, such as for a network resource, the following events are emitted by puppeteer's page:
- ['request'](#event-request) emitted when the request is issued by the page.
- ['response'](#event-response) emitted when/if the response is received for the request.
- ['requestfinished'](#event-requestfinished) emitted when the response body is downloaded and the request is complete.

If request fails at some point, then instead of 'requestfinished' event (and possibly instead of 'response' event), the  ['requestfailed'](#event-requestfailed) event is emitted.

If request gets a 'redirect' response, the request is successfully finished with the 'requestfinished' event, and a new request is  issued to a redirected url.

#### request.abort([errorCode])
- `errorCode` <[string]> Optional error code. Defaults to `failed`, could be
  one of the following:
  - `aborted` - An operation was aborted (due to user action)
  - `accessdenied` - Permission to access a resource, other than the network, was denied
  - `addressunreachable` - The IP address is unreachable. This usually means
    that there is no route to the specified host or network.
  - `blockedbyclient` - The client chose to block the request.
  - `blockedbyresponse` - The request failed because the response was delivered along with requirements which are not met ('X-Frame-Options' and 'Content-Security-Policy' ancestor checks, for instance).
  - `connectionaborted` - A connection timed out as a result of not receiving an ACK for data sent.
  - `connectionclosed` - A connection was closed (corresponding to a TCP FIN).
  - `connectionfailed` - A connection attempt failed.
  - `connectionrefused` - A connection attempt was refused.
  - `connectionreset` - A connection was reset (corresponding to a TCP RST).
  - `internetdisconnected` - The Internet connection has been lost.
  - `namenotresolved` - The host name could not be resolved.
  - `timedout` - An operation timed out.
  - `failed` - A generic failure occurred.
- returns: <[Promise]>

Aborts request. To use this, request interception should be enabled with `page.setRequestInterception`.
Exception is immediately thrown if the request interception is not enabled.

#### request.continue([overrides])
- `overrides` <[Object]> Optional request overwrites, which can be one of the following:
  - `url` <[string]> If set, the request url will be changed
  - `method` <[string]> If set changes the request method (e.g. `GET` or `POST`)
  - `postData` <[string]> If set changes the post data of request
  - `headers` <[Object]> If set changes the request HTTP headers
- returns: <[Promise]>

Continues request with optional request overrides. To use this, request interception should be enabled with `page.setRequestInterception`.
Exception is immediately thrown if the request interception is not enabled.

```js
await page.setRequestInterception(true);
page.on('request', request => {
  // Override headers
  const headers = Object.assign({}, request.headers(), {
    foo: 'bar', // set "foo" header
    origin: undefined, // remove "origin" header
  });
  request.continue({headers});
});
```

#### request.failure()
- returns: <?[Object]> Object describing request failure, if any
  - `errorText` <[string]> Human-readable error message, e.g. `'net::ERR_FAILED'`.

The method returns `null` unless this request was failed, as reported by
`requestfailed` event.

Example of logging all failed requests:

```js
page.on('requestfailed', request => {
  console.log(request.url() + ' ' + request.failure().errorText);
});
```

#### request.frame()
- returns: <?[Frame]> A [Frame] that initiated this request, or `null` if navigating to error pages.

#### request.headers()
- returns: <[Object]> An object with HTTP headers associated with the request. All header names are lower-case.

#### request.isNavigationRequest()
- returns: <[boolean]>

Whether this request is driving frame's navigation.

#### request.method()
- returns: <[string]> Request's method (GET, POST, etc.)

#### request.postData()
- returns: <[string]> Request's post body, if any.

#### request.redirectChain()
- returns: <[Array]<[Request]>>

A `redirectChain` is a chain of requests initiated to fetch a resource.
- If there are no redirects and the request was successful, the chain will be empty.
- If a server responds with at least a single redirect, then the chain will
contain all the requests that were redirected.

`redirectChain` is shared between all the requests of the same chain.

For example, if the website `http://example.com` has a single redirect to
`https://example.com`, then the chain will contain one request:

```js
const response = await page.goto('http://example.com');
const chain = response.request().redirectChain();
console.log(chain.length); // 1
console.log(chain[0].url()); // 'http://example.com'
```

If the website `https://google.com` has no redirects, then the chain will be empty:
```js
const response = await page.goto('https://google.com');
const chain = response.request().redirectChain();
console.log(chain.length); // 0
```

#### request.resourceType()
- returns: <[string]>

Contains the request's resource type as it was perceived by the rendering engine.
ResourceType will be one of the following: `document`, `stylesheet`, `image`, `media`, `font`, `script`, `texttrack`, `xhr`, `fetch`, `eventsource`, `websocket`, `manifest`, `other`.

#### request.respond(response)
- `response` <[Object]> Response that will fulfill this request
  - `status` <[number]> Response status code, defaults to `200`.
  - `headers` <[Object]> Optional response headers
  - `contentType` <[string]> If set, equals to setting `Content-Type` response header
  - `body` <[string]|[Buffer]> Optional response body
- returns: <[Promise]>

Fulfills request with given response. To use this, request interception should
be enabled with `page.setRequestInterception`. Exception is thrown if
request interception is not enabled.

An example of fulfilling all requests with 404 responses:

```js
await page.setRequestInterception(true);
page.on('request', request => {
  request.respond({
    status: 404,
    contentType: 'text/plain',
    body: 'Not Found!'
  });
});
```

> **NOTE** Mocking responses for dataURL requests is not supported.
> Calling `request.respond` for a dataURL request is a noop.

#### request.response()
- returns: <?[Response]> A matching [Response] object, or `null` if the response has not been received yet.

#### request.url()
- returns: <[string]> URL of the request.

### class: Response

[Response] class represents responses which are received by page.

#### response.buffer()
- returns: <Promise<[Buffer]>> Promise which resolves to a buffer with response body.

#### response.frame()
- returns: <?[Frame]> A [Frame] that initiated this response, or `null` if navigating to error pages.

#### response.fromCache()
- returns: <[boolean]>

True if the response was served from either the browser's disk cache or memory cache.

#### response.fromServiceWorker()
- returns: <[boolean]>

True if the response was served by a service worker.

#### response.headers()
- returns: <[Object]> An object with HTTP headers associated with the response. All header names are lower-case.

#### response.json()
- returns: <Promise<[Object]>> Promise which resolves to a JSON representation of response body.

This method will throw if the response body is not parsable via `JSON.parse`.

#### response.ok()
- returns: <[boolean]>

Contains a boolean stating whether the response was successful (status in the range 200-299) or not.

#### response.remoteAddress()
- returns: <[Object]>
  - `ip` <[string]> the IP address of the remote server
  - `port` <[number]> the port used to connect to the remote server

#### response.request()
- returns: <[Request]> A matching [Request] object.

#### response.securityDetails()
- returns: <?[SecurityDetails]> Security details if the response was received over the secure connection, or `null` otherwise.

#### response.status()
- returns: <[number]>

Contains the status code of the response (e.g., 200 for a success).

#### response.statusText()
- returns: <[string]>

Contains the status text of the response (e.g. usually an "OK" for a success).

#### response.text()
- returns: <[Promise]<[string]>> Promise which resolves to a text representation of response body.

#### response.url()
- returns: <[string]>

Contains the URL of the response.

### class: SecurityDetails

[SecurityDetails] class represents the security details when response was received over the secure connection.

#### securityDetails.issuer()
- returns: <[string]> A string with the name of issuer of the certificate.

#### securityDetails.protocol()
- returns: <[string]> String with the security protocol, eg. "TLS 1.2".

#### securityDetails.subjectName()
- returns: <[string]> Name of the subject to which the certificate was issued to.

#### securityDetails.validFrom()
- returns: <[number]> [UnixTime] stating the start of validity of the certificate.

#### securityDetails.validTo()
- returns: <[number]> [UnixTime] stating the end of validity of the certificate.

### class: Target

#### target.browser()

- returns: <[Browser]>

Get the browser the target belongs to.

#### target.browserContext()

- returns: <[BrowserContext]>

The browser context the target belongs to.

#### target.createCDPSession()
- returns: <[Promise]<[CDPSession]>>

Creates a Chrome Devtools Protocol session attached to the target.

#### target.opener()
- returns: <?[Target]>

Get the target that opened this target. Top-level targets return `null`.

#### target.page()
- returns: <[Promise]<?[Page]>>

If the target is not of type `"page"` or `"background_page"`, returns `null`.

#### target.type()
- returns: <"page"|"background_page"|"service_worker"|"other"|"browser">

Identifies what kind of target this is. Can be `"page"`, [`"background_page"`](https://developer.chrome.com/extensions/background_pages), `"service_worker"`, `"browser"` or `"other"`.

#### target.url()
- returns: <[string]>

### class: CDPSession

* extends: [`EventEmitter`](https://nodejs.org/api/events.html#events_class_eventemitter)

The `CDPSession` instances are used to talk raw Chrome Devtools Protocol:
- protocol methods can be called with `session.send` method.
- protocol events can be subscribed to with `session.on` method.

Documentation on DevTools Protocol can be found here: [DevTools Protocol Viewer](https://chromedevtools.github.io/devtools-protocol/).

```js
const client = await page.target().createCDPSession();
await client.send('Animation.enable');
client.on('Animation.animationCreated', () => console.log('Animation created!'));
const response = await client.send('Animation.getPlaybackRate');
console.log('playback rate is ' + response.playbackRate);
await client.send('Animation.setPlaybackRate', {
  playbackRate: response.playbackRate / 2
});
```

#### cdpSession.detach()
- returns: <[Promise]>

Detaches the cdpSession from the target. Once detached, the cdpSession object won't emit any events and can't be used
to send messages.

#### cdpSession.send(method[, params])
- `method` <[string]> protocol method name
- `params` <[Object]> Optional method parameters
- returns: <[Promise]<[Object]>>

### class: Coverage

Coverage gathers information about parts of JavaScript and CSS that were used by the page.

An example of using JavaScript and CSS coverage to get percentage of initially
executed code:

```js
// Enable both JavaScript and CSS coverage
await Promise.all([
  page.coverage.startJSCoverage(),
  page.coverage.startCSSCoverage()
]);
// Navigate to page
await page.goto('https://example.com');
// Disable both JavaScript and CSS coverage
const [jsCoverage, cssCoverage] = await Promise.all([
  page.coverage.stopJSCoverage(),
  page.coverage.stopCSSCoverage(),
]);
let totalBytes = 0;
let usedBytes = 0;
const coverage = [...jsCoverage, ...cssCoverage];
for (const entry of coverage) {
  totalBytes += entry.text.length;
  for (const range of entry.ranges)
    usedBytes += range.end - range.start - 1;
}
console.log(`Bytes used: ${usedBytes / totalBytes * 100}%`);
```

_To output coverage in a form consumable by [Istanbul](https://github.com/istanbuljs),
  see [puppeteer-to-istanbul](https://github.com/istanbuljs/puppeteer-to-istanbul)._

#### coverage.startCSSCoverage(options)
- `options` <[Object]>  Set of configurable options for coverage
  - `resetOnNavigation` <[boolean]> Whether to reset coverage on every navigation. Defaults to `true`.
- returns: <[Promise]> Promise that resolves when coverage is started

#### coverage.startJSCoverage(options)
- `options` <[Object]>  Set of configurable options for coverage
  - `resetOnNavigation` <[boolean]> Whether to reset coverage on every navigation. Defaults to `true`.
  - `reportAnonymousScripts` <[boolean]> Whether anonymous scripts generated by the page should be reported. Defaults to `false`.
- returns: <[Promise]> Promise that resolves when coverage is started

> **NOTE** Anonymous scripts are ones that don't have an associated url. These are scripts that are dynamically created on the page using `eval` or `new Function`. If `reportAnonymousScripts` is set to `true`, anonymous scripts will have `__puppeteer_evaluation_script__` as their URL.

#### coverage.stopCSSCoverage()
- returns: <[Promise]<[Array]<[Object]>>> Promise that resolves to the array of coverage reports for all stylesheets
  - `url` <[string]> StyleSheet URL
  - `text` <[string]> StyleSheet content
  - `ranges` <[Array]<[Object]>> StyleSheet ranges that were used. Ranges are sorted and non-overlapping.
    - `start` <[number]> A start offset in text, inclusive
    - `end` <[number]> An end offset in text, exclusive

> **NOTE** CSS Coverage doesn't include dynamically injected style tags without sourceURLs.

#### coverage.stopJSCoverage()
- returns: <[Promise]<[Array]<[Object]>>> Promise that resolves to the array of coverage reports for all scripts
  - `url` <[string]> Script URL
  - `text` <[string]> Script content
  - `ranges` <[Array]<[Object]>> Script ranges that were executed. Ranges are sorted and non-overlapping.
    - `start` <[number]> A start offset in text, inclusive
    - `end` <[number]> An end offset in text, exclusive

> **NOTE** JavaScript Coverage doesn't include anonymous scripts by default. However, scripts with sourceURLs are
reported.

### class: TimeoutError

* extends: [Error]

TimeoutError is emitted whenever certain operations are terminated due to timeout, e.g. [page.waitForSelector(selector[, options])](#pagewaitforselectorselector-options) or [puppeteer.launch([options])](#puppeteerlaunchoptions).



[Array]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array "Array"
[boolean]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Boolean_type "Boolean"
[Buffer]: https://nodejs.org/api/buffer.html#buffer_class_buffer "Buffer"
[function]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function "Function"
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type "Number"
[Object]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object "Object"
[origin]: https://developer.mozilla.org/en-US/docs/Glossary/Origin "Origin"
[Page]: #class-page "Page"
[Promise]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise "Promise"
[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type "String"
[stream.Readable]: https://nodejs.org/api/stream.html#stream_class_stream_readable "stream.Readable"
[CDPSession]: #class-cdpsession  "CDPSession"
[BrowserFetcher]: #class-browserfetcher  "BrowserFetcher"
[BrowserContext]: #class-browsercontext  "BrowserContext"
[Error]: https://nodejs.org/api/errors.html#errors_class_error "Error"
[Frame]: #class-frame "Frame"
[ConsoleMessage]: #class-consolemessage "ConsoleMessage"
[ChildProcess]: https://nodejs.org/api/child_process.html "ChildProcess"
[Coverage]: #class-coverage "Coverage"
[iterator]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols "Iterator"
[Response]: #class-response  "Response"
[Request]: #class-request  "Request"
[Browser]: #class-browser  "Browser"
[Body]: #class-body  "Body"
[Element]: https://developer.mozilla.org/en-US/docs/Web/API/element "Element"
[Keyboard]: #class-keyboard "Keyboard"
[Dialog]: #class-dialog  "Dialog"
[JSHandle]: #class-jshandle "JSHandle"
[ExecutionContext]: #class-executioncontext "ExecutionContext"
[Mouse]: #class-mouse "Mouse"
[Map]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map "Map"
[selector]: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors "selector"
[Tracing]: #class-tracing "Tracing"
[ElementHandle]: #class-elementhandle "ElementHandle"
[UIEvent.detail]: https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/detail "UIEvent.detail"
[Serializable]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify#Description "Serializable"
[Touchscreen]: #class-touchscreen "Touchscreen"
[Target]: #class-target "Target"
[USKeyboardLayout]: ../lib/USKeyboardLayout.js "USKeyboardLayout"
[xpath]: https://developer.mozilla.org/en-US/docs/Web/XPath "xpath"
[UnixTime]: https://en.wikipedia.org/wiki/Unix_time "Unix Time"
[SecurityDetails]: #class-securitydetails "SecurityDetails"
[Worker]: #class-worker "Worker"
[Accessibility]: #class-accessibility "Accessibility"
[AXNode]: #accessibilitysnapshotoptions "AXNode"
[ConnectionTransport]: ../lib/WebSocketTransport.js "ConnectionTransport"