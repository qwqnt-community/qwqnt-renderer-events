# qwqnt-renderer-events

本插件是 QwQNT 框架下，用于为 Renderer 提供一系列事件的插件。

本插件使用 `IpcInterceptor` 插件作为前置。

## 使用

在 Renderer 中，使用 `RendererEvents.onSettingsWindowCreated` 对设置窗口的创建进行监听。

对于一次性的监听，请使用 `RendererEvents.onSettingsWindowCreatedOnce` 。

下面是一个实例：

```typescript
// renderer
RendererEvents.onSettingsWindowCreated(() => {
  alert('settings');
});
```

在 Renderer 中，使用 `RendererEvents.onMessageWindowCreated` 对主窗口的创建进行监听。

对于一次性的监听，请使用 `RendererEvents.onMessageWindowCreatedOnce` 。

下面是一个实例：

```typescript
// renderer
RendererEvents.onMessageWindowCreated(() => {
  alert('message');
});
```

在 Renderer 中，使用 `RendererEvents.onLogin` 对用户登录进行监听。

下面是一个实例：

```typescript
// renderer
RendererEvents.onLogin((uid: string) => {
  alert(uid);
});
```

对于使用 Typescript 编写插件的开发者，你可能需要将 `RendererEvents` 写入 `global.d.ts` 中。

```typescript
// global
declare namespace RendererEvents {
  const onLogin: (callback: (uid?: string) => void) => void;
  const onSettingsWindowCreated: (callback: () => void) => void;
  const onSettingsWindowCreatedOnce: (callback: () => void) => void;
  const onMessageWindowCreated: (callback: () => void) => void;
  const onMessageWindowCreatedOnce: (callback: () => void) => void;
}
```

## License
```
    MIT License

    qwqnt-renderer-events
    Copyright (C) 2025  風間青祢

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.
```