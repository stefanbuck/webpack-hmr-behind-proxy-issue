# webpack-hmr-behind-proxy-issue

This repository is a reproduction of the issue https://github.com/webpack/webpack-dev-server/issues/2164

### Steps to reproduce

- `git clone git@github.com:maxlk/webpack-hmr-behind-proxy-issue.git`
- `cd webpack-hmr-behind-proxy-issue`
- `npm install`
- `npm start`
- Open `http://localhost:9876/www/` in web browser.
- Open DevTools and make sure that *Preserve log* is enabled in *Console* and *Network*.
- Make any change in `src/print.js` and save it.

### Expected

- HMR successfully applies hot update (update shuold be loaded from url `http://localhost:8080/5cc71fea9aecb707e3fc.hot-update.json`)

### Actual

- Error `GET http://localhost:9876/www/5cc71fea9aecb707e3fc.hot-update.json 404 (Not Found)` occurs and ***full reload*** (instead of hot reload) is triggered.
