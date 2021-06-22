# 使用React作為前端

## 使用前端套件 - React
1. 安裝套件：`npm install -g create-react-app`
2. 建立專案：`mkdir react-web`
3. 進入專案：`cd react-web`
4. 建立react專案：`create-react-app .`
![](https://i.imgur.com/VdRp8bb.png)
5. 開啟伺服器：`npm satrt`
![](https://i.imgur.com/BNYMjJc.png)



## 更改Port

因為現在前端(專案react-web)占用port 3000，所以要把後端(專案javascript-express)的port改成3001
1. 將`javascript-express/package.json`裡的script改成`set PORT=3001 && node ./bin/www` (不同系統有差異)
![](https://i.imgur.com/2Bt4GXf.png)
2. 在`javascript-express/app.js`裡放入
```javascript=
var cors = require('cors'); //放最前面
app.use(cors());  //放在var app = express();後
```
3. 最後可以得到前端為`http://localhost:3000/`，後端則為`http://localhost:3001/`

4. 使用POSTMAN測試前後端有沒有通訊成功
![](https://i.imgur.com/mjSzRdX.png)
> 我們之前在後端那邊設了一個
```javascript=
router.get('/api/sayHi', function(req, res, next) {
  res.send('hi');
});
```
> 因此在「前端(3001)」使用「後端(3000)」的API的情況下送了一個request出去，也可以看到從後端response回了一個response回來



# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
