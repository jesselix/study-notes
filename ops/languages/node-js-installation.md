# Node.js Installation

## Install Node.js
- Download node.js  
https://nodejs.org/en/download/

## Validation
- Check the node.js version
``` bash
node -v
```

- Output
``` bash
v18.13.0
```

## Install npm
- If you are in China
``` bash
apt update -y
apt install -y nodejs npm
npm config set registry https://registry.npm.taobao.org
npm install n -g
n stable
```

- If you are not in China, replace this command
``` bash
npm config set registry https://registry.npmjs.org/
```

- Output
``` bash
+ package@1.0.1
added 1 package from 1 contributor in 0.754s
```

## Validation
- Check the npm version
``` bash
npm -v
```

- Output
``` bash
8.19.3
```


## References
> NPM 使用介绍  
https://www.runoob.com/nodejs/nodejs-npm.html