---
title: Mobx 学习笔记
date: 2018-02-12 09:25:07
tags: react
---
官方文档

http://cn.mobx.js.org/

mobx是react的一种状态管理器

下面是自己写的demo
state.js

<!-- more -->

```js
import { observable, computed, action } from 'mobx'

class AppStore {
  @observable text = '测试双向绑定'
  @observable num = 0

  @computed get msg() {
    return this.text
  }

  @action changeMsg(val) {
    this.text = val
  }

  @action addNum() {
    this.num += 1
  }
}

const appStore = new AppStore()

setInterval(() => {
  appStore.addNum()
}, 1000)

export default appStore

```
app.js

```js
import React from 'react'
import { observer, inject } from 'mobx-react'

@inject('appStore') @observer
class App extends React.Component {
  componentDidMount() {
    const val = this.text.value
    console.log(this.text.value)

    // this.text.value = ''
    // this.text.focus()
    this.text.value = val

    console.log(this.props);
  }

  handleChange = (e) => {
    this.props.appStore.changeMsg(e.target.value)
  }

  render() {
    return (
      <div>
        <p>
          <input
            type="text"
            value={this.props.appStore.msg}
            onChange={this.handleChange}
            ref={(text) => { this.text = text }}
          />
        </p>
        <p>{this.props.appStore.msg}</p>
        <p>距离打开页面已经过：{this.props.appStore.num} 秒</p>
        <div>hhahh</div>
      </div>
    )
  }
}

export default App


```

index.js

```js
import React from 'react'
import ReactDOM from 'react-dom'
import { Provider } from 'mobx-react'
import App from './App'
import appStore from './store/state'

import { AppContainer } from 'react-hot-loader'  // eslint-disable-line

const root = document.getElementById('root')

const render = (component) => {
  const node = (
    // <AppContainer>
      <Provider appStore={appStore}>
        { component }
      </Provider>
    // </AppContainer>
  )
  ReactDOM.render(node, root)
}

render(<App />)

```



### babel 修饰器配置

http://cn.mobx.js.org/best/decorators.html


### 参考




