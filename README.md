## webpack-bundle-analyzer使用方法
### 一、安装依赖

```
cnpm i webpack-bundle-analyzer -D
```

### 二、配置webpack plugins

> 在webpack config中添加plugin

```js
const BundleAnalyzerPlugin = require('webpack-bundle-analyzer').BundleAnalyzerPlugin;

...
	plugins: [
		...
		new BundleAnalyzerPlugin({
			analyzerMode: 'server',
			analyzerHost: '127.0.0.1',
			analyzerPort: 8889,
			reportFilename: 'report.html',
			defaultSizes: 'parsed',
			openAnalyzer: true,
			generateStatsFile: false,
			statsFilename: 'stats.json',
			statsOptions: null,
			logLevel: 'info'
		})
	]
...
```

### 三、添加scripts脚本

> 在package.json的scripts中添加脚本

```json
scripts: {
	"analyz": "NODE_ENV=production npm_config_report=true npm run build"
}
```

-----
##### 大功告成，可以在`npm run build`之后看到资源的打包情况！