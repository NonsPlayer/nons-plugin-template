# Nons 插件模板

这是一个可直接复制使用的 Nons 前端插件仓库模板。它包含一个 React 页面、Manifest 页面贡献和 SDK 构建配置，不包含 WASM 后端。

## 开始开发

```bash
pnpm install
pnpm build
```

`pnpm build` 会执行 TypeScript 检查、前端打包、Manifest 校验，并生成：

- `dist/`：可安装的插件目录
- `nons-plugin-template-0.1.0.zip`：可在 Nons 设置 → 插件中安装的压缩包

## 修改插件

- `manifest.json`：修改插件 ID、名称、版本、权限和页面/导航贡献。
- `frontend/index.tsx`：实现页面组件；入口导出名必须与 Manifest 中 `pages[].export` 一致。
- `package.json`：维护插件自己的依赖和版本。
- `tsconfig.json`：使用 SDK 公开类型进行严格 TypeScript 检查。

React 和 `@nonsplayer/plugin-sdk` 由宿主提供，构建产物不会打包它们的副本。

## 安装验证

构建 ZIP 后，在 Nons 的“设置 → 插件”中选择安装，确认权限并打开插件页面。模板默认只申请 `ui` 权限。

WIT 契约和 Manifest schema 由 `@nonsplayer/plugin-sdk` 提供，位于 `node_modules/@nonsplayer/plugin-sdk/`。
