# Node.js Installation

## Install Node.js
- Download node.js  
https://nodejs.org/en/download/

## Validation
- check the node.js version
``` bash
node -v
```

- output
``` bash
v12.18.3
```

## Install npm
- if you are in China
``` bash
apt update -y
apt install -y nodejs npm
npm config set registry https://registry.npm.taobao.org
npm install n -g
n stable
```

- if you are not in China, replace this command
``` bash
npm config set registry https://registry.npmjs.org/
```

- output
``` bash
+ package@1.0.1
added 1 package from 1 contributor in 0.754s
```

## Validation
- check the npm version
``` bash
npm -v
```

- output
``` bash
6.14.6
```


## References
> NPM 使用介绍  
https://www.runoob.com/nodejs/nodejs-npm.html