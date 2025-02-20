## A Simple Expense Manager 💵

UM STUDENT NEW UPDATED SOFTWARE MAINTENANCE AND EVOLUTION PROJECT

New Hosting Link : [Updated Expense Manager](https://expense-manager-43d96.web.app/)


## DEMO Account

*_In case you need to have a quick look at the app without creating an account, use the below credentials_*

[Click Here For Demo](https://sad-shirley-6ef62f.netlify.com/)

`Username : testuser@examplemail.com`
`password : test123456`

## SCREENSHOTS

#### Mobile Views
[![Mobile Screens](https://i.postimg.cc/c1jZTXVX/mobile-Views.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Night Mode Home Page
[![Night Mode Home](https://i.postimg.cc/mZVBMTwf/Home1.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Month View Page Night Mode
[![Night Mode Month](https://i.postimg.cc/jqvn50nC/MONTHLY-NIGHT-MODE.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Daily View Night Mode
[![Daily View](https://i.postimg.cc/BQQDcQfx/DAILY-NIGHT-MODE.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Statistics Night Mode
[![Statistics](https://i.postimg.cc/1tm5hXHB/STATISTICS-NIGHT-MODE2.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Saving Goals Night Mode
[![Savings](https://i.postimg.cc/WbBNpX8h/SAVINGS-NIGHT-MODE.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Settings Night Mode
[![Settings](https://i.postimg.cc/CLBMVWj3/SETTINGS-NIGHT-MODE.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Filter Night Mode
[![Filter Page](https://i.postimg.cc/kM2rDJ8Y/FILTER-NIGHT-MODE.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Home Page Day Mode
[![Home Page](https://i.postimg.cc/25XXmXdt/HOMEDAY4.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Monthly View Day Mode
[![Monthly View](https://i.postimg.cc/qqmNZyH2/MONTH-VIEW-DAY.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Daily View Day Mode
[![Daily View](https://i.postimg.cc/cCT3yPwg/DAILY-DAY-MODE.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Statistics Day Mode
[![Statistics](https://i.postimg.cc/Wz43rzqz/STATISTICS-DAY-MODE.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Loan Page Day Mode
[![Loan Page](https://s25.postimg.cc/s16nf3kxb/loan.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Saving Goals Day Mode
[![Savings](https://i.postimg.cc/fRYwVmq5/SAVINGS-DAY-MODE.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Settings Day Mode
[![Settings](https://i.postimg.cc/59k9TxF5/SETTINGS-DAY-MODE.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Login Screen
[![Login Page](https://s25.postimg.cc/jvolgx1tb/login.png)](https://sad-shirley-6ef62f.netlify.com/)

#### Calendar Component
[![Calendar Component](https://i.postimg.cc/DyZ1TZnM/calendar-component.png)](https://sad-shirley-6ef62f.netlify.com/)

## SETUP

#### 1. Setting Up Firebase 
- Create a firebase account

- Create a new firebase project 

  [![Add Firebase Project](https://i.postimg.cc/sxvhPQB7/firebase-1.png)](https://i.postimg.cc/sxvhPQB7/firebase-1.png)
  [![Add Firebase Project](https://i.postimg.cc/QNy58bPb/firebase-2.png)](https://i.postimg.cc/QNy58bPb/firebase-2.png)
  [![Add Firebase Project](https://i.postimg.cc/NFSrdsTV/firebase-3.png)](https://i.postimg.cc/NFSrdsTV/firebase-3.png)
  
- From the console, expand 'Build' and select Firestore Database and follow the steps to setup the database

  [![Create Cloud Firestore](https://i.postimg.cc/wjsCvgVB/firestore-1.png)](https://i.postimg.cc/wjsCvgVB/firestore-1.png)
  [![Create Cloud Firestore](https://i.postimg.cc/jjHBHcB0/firestore-2.png)](https://i.postimg.cc/jjHBHcB0/firestore-2.png)
  [![Create Cloud Firestore](https://i.postimg.cc/nLb69gRG/firestore-3.png)](https://i.postimg.cc/nLb69gRG/firestore-3.png)  

- change database rules to 
  ```
  rules_version = '2';
  service cloud.firestore {
    match /databases/{database}/documents {
      match /expenseTable/{userId} {
        allow read, write: if request.auth.uid == userId;
        match /{document=**} {
          allow read, write: if request.auth.uid == userId;
        }
      }
      match /savingsTable/{userId} {
        allow read, write: if request.auth.uid == userId;
        match /{document=**} {
          allow read, write: if request.auth.uid == userId;
        }
      }
      match /loanTable/{userId} {
        allow read, write: if request.auth.uid == userId;
        match /{document=**} {
          allow read, write: if request.auth.uid == userId;
        }
      }
      match /settings/{userId} {
        allow read, write: if request.auth.uid == userId;
        match /{document=**} {
          allow read, write: if request.auth.uid == userId;
        }
      }
      match /users/{userId} {
        allow read, write: if request.auth.uid == userId;
        match /{document=**} {
          allow read, write: if request.auth.uid == userId;
        }
      }
      match /defaultCategories/{userId} {
        allow read, write: if request.auth.uid == userId;
        match /{document=**} {
          allow read, write: if request.auth.uid == userId;
        }
      }
    }
  }
  ```
  
- Now lets add the app in firebase by going to Settings -> Project Settings and clicking on the Web App under 'Your Apps'
  [![Adding the app](https://i.postimg.cc/DZsDvgdY/add-firebaseapp.png)](https://i.postimg.cc/DZsDvgdY/add-firebaseapp.png)
  [![Adding the app](https://i.postimg.cc/cCBbYLzR/add-firebaseapp-1.png)](https://i.postimg.cc/cCBbYLzR/add-firebaseapp-1.png)
  
- Now Lets add the config in ./src/firebase/firebase.js
  [![lets add the config](https://i.postimg.cc/YqfvGBCt/add-firebaseapp-2.png)](https://i.postimg.cc/YqfvGBCt/add-firebaseapp-2.png)
  
- OPTIONAL_STEP : If you're hosting this app somewhere make sure the api key comes from .env.local as environment variable, doing this does not expose yor api-key , and do not commit this file to github , add this in .gitignore 
    `# api Keys`
    `*.env`
 
    #### create a file named .env.local in root folder and add your firebase api key here
    
     `REACT_APP_FIREBASE_API_KEY = "your-api-key-here"`
     [![.env.local](https://i.postimg.cc/fLZcGv1q/env-local.png)](https://i.postimg.cc/fLZcGv1q/env-local.png)
  
- From Build -> Authentication, enable Google Authentication and Email Authentication , Feel Free to add other authentication methods and setup accordingly
  [![Enable Google Authentication](https://i.postimg.cc/dQ5XqL8F/firebase-auth1.png)](https://i.postimg.cc/dQ5XqL8F/firebase-auth1.png)
  
- Finally we need to set up the API-Key for currency converter , which is needed for travel mode.
    - Head over to [currencyconverterapi.com](https://free.currencyconverterapi.com/)
    - create your API-KEY 
    - Add this in .env.local as a environment variable
    
        `REACT_APP_FREE_CURRENCY_CONVERTER_API_KEY = "your-api-key-here"`
  
 2. Setup Repo Locally
 
    `git clone https://github.com/YogeshPrasanna/expense-manager-react.git`

### `npm install`

      This will install all the required packages and dependencies to run the app.

### `npm start`

  Runs the app in the development mode.<br>
  Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

  The page will reload if you make edits.<br>
  You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.<br>

### `npm run build`

Builds the app for production to the `build` folder.<br>
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br>
Your app is ready to be deployed!

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (Webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Supported Browsers

By default, the generated project uses the latest version of React.

You can refer [to the React documentation](https://reactjs.org/docs/react-dom.html#browser-support) for more information about supported browsers.

