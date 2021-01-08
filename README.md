# Angular-ProxyConf

### angular.json

```javascript
"serve": {
    "builder": "@angular-devkit/build-angular:dev-server",
    "options": {
        "browserTarget": "appTest:build",
        "proxyConfig": "./src/proxy.conf.json"
    },
```
If you do not want edit angular.json: 
#### package.json
```javascript
{
"start": "ng serve --proxy-config proxy.conf.json"
```
### /src/proxy.conf.json

```javascript
{
  "/api/*": {
    "target": "http://127.0.0.1:8080",
    "secure": false,
    "pathRewrite": {
      "^/api": ""
    }
  }
}
```

# Solve strict Property Initialization 
### tsconfig.json

```javascript
{
  "compileOnSave": false,
  "compilerOptions": {
    "baseUrl": "./",
    "outDir": "./dist/out-tsc",
    "forceConsistentCasingInFileNames": true,
    "strict": true,
    "strictPropertyInitialization": false,
    "noImplicitReturns": true,
    "noFallthroughCasesInSwitch": true,
    "sourceMap": true,
    "declaration": false,
    "downlevelIteration": true,
    "experimentalDecorators": true,
    "moduleResolution": "node",
    "importHelpers": true,
    "target": "es2015",
    "module": "es2020",
    "lib": [
      "es2018",
      "dom"
    ]
  },
  "angularCompilerOptions": {
    "strictInjectionParameters": true,
    "strictInputAccessModifiers": true,
    "strictTemplates": true
  }
}
```
