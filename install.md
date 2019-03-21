# 安装问题

#### no such file or directory, open '/Users/fu/Desktop/package.json'

> npm init -y  生成默认的package.json文件

####  mac上执行 npm install -g vue-cli 警告 Missing write access to /usr/local/lib/node_modules

> 用sudo npm install -g vue-cli

#### `webpack-dev-server --inline --progress --config build/webpack.dev.conf.js`

> node-modules 意外改动 ，删除node-modules之后重新运行npm install 

#### vue脚手架升级

> npm uninstall -g vue-cli  先卸载

> npm install -g @vue-cli  再安装

#### 安装新版vue 

> vue create projectname

#### ajax请求

> npm install axios 安装axios

> 在src目录下建文件夹lib>axios.js

> import axios from 'axios';

const getXhrPromise = config => new Promise((resolve) => {
  axios(config).then((res) => {
    res.data = (typeof res.data === 'object' && res.data) || {};
    res.data._http_status = res.status;
    resolve(res.data);
  }).catch(() => {
    resolve();
  });
});

export default {
  all(params) {
    return axios.all(params);
  },
  spread(params) {
    return axios.spread(params);
  },
  postKibana(url, data) {
    const config = {
      url,
      method: 'post',
      data,
    };
    return getXhrPromise(config);
  },
  post(url, data) {
    const config = {
      url,
      method: 'post',
      data,
    };
    return getXhrPromise(config);
  },
  get(url, data) {
    const config = {
      url,
      method: 'get',
      params: data,
    };
    return getXhrPromise(config);
  },
};

> 在main.js 里面引入 axios import axios from './lib/axios'

> Vue.prototype.$http = axios;
