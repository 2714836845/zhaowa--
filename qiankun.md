import { createApp } from 'vue';
import App from './App.vue';
import { createRouter, createWebHistory } from 'vue-router';
import { createApp as createMicroApp } from 'qiankun';
import store from './store';

const app = createApp(App);
app.use(store);

const router = createRouter({
  history: createWebHistory(),
  routes: [
    // 主应用的路由配置
    // ...
  ]
});

app.use(router);
app.mount('#app');

// 创建子应用
const microApp = createMicroApp({
  // 子应用配置
});

// 将主应用的 Vuex store 传递给子应用
microApp.props(store);

