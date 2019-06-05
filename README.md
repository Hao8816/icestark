# icestark

> Icestark is a JavaScript library for multiple react projects, Ice workbench solution.

[![NPM version](https://img.shields.io/npm/v/@ice/stark.svg?style=flat)](https://npmjs.org/package/@ice/stark)
[![Package Quality](https://npm.packagequality.com/shield/@ice/stark.svg)](https://packagequality.com/#?package=@ice/stark)
[![build status](https://img.shields.io/travis/ice-lab/@ice/stark.svg?style=flat-square)](https://travis-ci.org/ice-lab/@ice/stark)
[![Test coverage](https://img.shields.io/codecov/c/github/ice-lab/@ice/stark.svg?style=flat-square)](https://codecov.io/gh/ice-lab/@ice/stark)
[![NPM downloads](http://img.shields.io/npm/dm/@ice/stark.svg?style=flat)](https://npmjs.org/package/@ice/stark)
[![David deps](https://img.shields.io/david/ice-lab/@ice/stark.svg?style=flat-square)](https://david-dm.org/ice-lab/@ice/stark)

## Installation

```bash
npm install @ice/stark --save
```

## Example

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import { AppRouter, AppRoute } from '@ice/stark';

class Layout extends React.Component {
  onRouteChange = (pathname, query) => {
    console.log(pathname, query);
  }

  render() {
    return (
      <div>
        <div>this is common header</div>
        <AppRouter
          onRouteChange={this.onRouteChange}
          useShadow
        >
          <AppRoute
            path={['/', '/home', '/about']}
            exact
            title="主页"
            url={['//127.0.0.1:4444/js/index.js', '//127.0.0.1:4444/css/index.css']}
          />
          <AppRoute
            path="/user"
            title="用户页面"
            url={['//127.0.0.1:5555/js/index.js', '//127.0.0.1:5555/css/index.css']}
          />
        </AppRouter>
        <div>this is common footer</div>
      </div>
    );
  }
}
```

## Configuration

### AppRouter

|        Property        |              Description              |     Type     | Default |
| :--------------------: | :-----------------------------------: | :----------: | :-----: |
|     onRouteChange      | callback executed when route changed  |   function   |  noop   |
|   NotFoundComponent    |  render when the route changed error  | ReactElement |         |
|  BundleErrorComponent  | render when the bundle pulls an error | ReactElement |         |
| BundleLoadingComponent |     render when Bundle is Loading     | ReactElement |         |
|       shadowRoot       |       whether to use shadowRoot       |   boolean    |  false  |


### AppRoute

| Property  |                    Description                    |      Type       | Default |
| :-------: | :-----------------------------------------------: | :-------------: | :-----: |
|   path    | app router path, reference react-router, required | string/string[] |         |
|    url    |             assets load url, required             | string/string[] |         |
|   title   |                   documentTitle                   |     string      |         |
|   exact   |              reference react-router               |     boolean     |  false  |
|  strict   |              reference react-router               |     boolean     |  false  |
| sensitive |              reference react-router               |     boolean     |  false  |
