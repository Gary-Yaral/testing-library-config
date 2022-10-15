
# How to install and configured Testing Library to use it with Vitejs and Reactjs

## 1- Install jest and jest-environment-jsdom and jsdom
``` console
 npm install -D jest jest-environment-jsdom jsdom
 ```

## 2- Install testing-library and its presets
``` console
 npm install @testing-library/jest-dom @testing-library/react @testing-library/user-event
 ```
 
## 3- Install babel presets
``` console
 npm install -D @babel/core @babel/preset-env @babel/preset-react babel-jest babel-loader
 
 ```
 # How to configure all
 You must create in the root directory that files:
 - babel.config.json
 - jest.setup.js
 - jest.config.js
 - setupTest.js


 ## babel.config.json file
 
``` console
 {
  "presets": [
    "@babel/preset-env",
    ["@babel/preset-react", { "runtime": "automatic" }]
  ]
}
``` 

## jest.setup.js

``` console
 import '@testing-library/jest-dom/extend-expect';

``` 

## jest.config.js

``` console 
 export default {
  testEnvironment: 'jsdom',
  testMatch: [
    '**/__tests__/**/*.[jt]s?(x)',
    '**/?(*.)+(spec|test|tests).[tj]s?(x)',
  ],
  setupFilesAfterEnv: ['<rootDir>/jest.setup.js'],
};

```

## setupTest.js

```console
 import '@testing-library/jest-dom';

```




