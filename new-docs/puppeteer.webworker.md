<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [puppeteer](./puppeteer.md) &gt; [WebWorker](./puppeteer.webworker.md)

## WebWorker class

The WebWorker class represents a [WebWorker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)<!-- -->.

<b>Signature:</b>

```typescript
export declare class WebWorker extends EventEmitter 
```
<b>Extends:</b> [EventEmitter](./puppeteer.eventemitter.md)

## Remarks

The events `workercreated` and `workerdestroyed` are emitted on the page object to signal the worker lifecycle.

The constructor for this class is marked as internal. Third-party code should not call the constructor directly or create subclasses that extend the `WebWorker` class.

## Example


```js
page.on('workercreated', worker => console.log('Worker created: ' + worker.url()));
page.on('workerdestroyed', worker => console.log('Worker destroyed: ' + worker.url()));

console.log('Current workers:');
for (const worker of page.workers()) {
  console.log('  ' + worker.url());
}

```

## Properties

|  Property | Modifiers | Type | Description |
|  --- | --- | --- | --- |
|  [\_client](./puppeteer.webworker._client.md) |  | [CDPSession](./puppeteer.cdpsession.md) |  |
|  [\_executionContextCallback](./puppeteer.webworker._executioncontextcallback.md) |  | (value: [ExecutionContext](./puppeteer.executioncontext.md)<!-- -->) =&gt; void |  |
|  [\_executionContextPromise](./puppeteer.webworker._executioncontextpromise.md) |  | Promise&lt;[ExecutionContext](./puppeteer.executioncontext.md)<!-- -->&gt; |  |
|  [\_url](./puppeteer.webworker._url.md) |  | string |  |

## Methods

|  Method | Modifiers | Description |
|  --- | --- | --- |
|  [evaluate(pageFunction, args)](./puppeteer.webworker.evaluate.md) |  | If the function passed to the <code>worker.evaluate</code> returns a Promise, then <code>worker.evaluate</code> would wait for the promise to resolve and return its value. If the function passed to the <code>worker.evaluate</code> returns a non-serializable value, then <code>worker.evaluate</code> resolves to <code>undefined</code>. DevTools Protocol also supports transferring some additional values that are not serializable by <code>JSON</code>: <code>-0</code>, <code>NaN</code>, <code>Infinity</code>, <code>-Infinity</code>, and bigint literals. Shortcut for <code>await worker.executionContext()).evaluate(pageFunction, ...args)</code>. |
|  [evaluateHandle(pageFunction, args)](./puppeteer.webworker.evaluatehandle.md) |  | The only difference between <code>worker.evaluate</code> and <code>worker.evaluateHandle</code> is that <code>worker.evaluateHandle</code> returns in-page object (JSHandle). If the function passed to the <code>worker.evaluateHandle</code> returns a \[Promise\], then <code>worker.evaluateHandle</code> would wait for the promise to resolve and return its value. Shortcut for <code>await worker.executionContext()).evaluateHandle(pageFunction, ...args)</code> |
|  [executionContext()](./puppeteer.webworker.executioncontext.md) |  | Returns the ExecutionContext the WebWorker runs in |
|  [url()](./puppeteer.webworker.url.md) |  |  |
