# Node.js Installation

## Install Node.js
- Download node.js  
https://nodejs.org/en/download/

## Validation
- Check the node.js version
``` zsh
node -v
```

- Output
``` zsh
v16.10.0
```

## Install npm
- If you are in China
``` zsh
apt update -y
apt install -y nodejs npm
npm config set registry https://registry.npm.taobao.org
npm install n -g
n stable
```

- If you are not in China, replace this command
``` zsh
npm config set registry https://registry.npmjs.org/
```

- Output
``` zsh
+ package@1.0.1
added 1 package from 1 contributor in 0.754s
```

## Validation
- Check the npm version
``` zsh
npm -v
```

- Output
``` zsh
7.24.2
```


## References
> NPM 使用介绍  
https://www.runoob.com/nodejs/nodejs-npm.html