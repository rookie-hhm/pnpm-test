### 问题1
在任何目录下执行 `pnpm install typescript -D -w`,
都会出现 

`
ERROR  --workspace-root may only be used inside a workspace
`

### 问题2
在packages/components 执行 `pnpm install @tt-ui/utils`命令的时候，不会从我本地`packages/utils`这个包下载，而是从远程仓库查找这个仓库，后来改成在`packages/components/package.json`直接写了包依赖如下:
```
"devDependencies": {
  "@tt-ui/utils": "workspace:1.0.0"
}
```
接着在`packages/components/`目录下执行`pnpm install`安装依赖包
发生错误如下:
` ERR_PNPM_NO_MATCHING_VERSION_INSIDE_WORKSPACE  In : No matching version found for @tt-ui/utils@1.0.0 inside the workspace`
