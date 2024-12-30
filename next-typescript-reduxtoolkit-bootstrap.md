
# Frontend Project Setup Guide

This guide will help you set up a frontend project using the following technologies:
- **Bootstrap 5**
- **React**
- **Redux Toolkit**
- **Next.js**
- **SASS**

---

## 1. Initialize the Project

1. Create a new Next.js app:
   ```bash
   npx create-next-app@latest my-frontend-project
   cd my-frontend-project
   ```

2. Choose TypeScript for type safety (optional but recommended):
   ```bash
   touch tsconfig.json
   npm install --save-dev typescript @types/react @types/node
   ```

---

## 2. Install Dependencies

Install the required libraries for your stack:
```bash
npm install react-redux @reduxjs/toolkit bootstrap sass
```

For additional utilities:
```bash
npm install axios
npm install --save-dev eslint prettier eslint-config-prettier eslint-plugin-react eslint-plugin-react-hooks
```

---

## 3. Configure SASS

1. Rename any CSS file (e.g., `styles/globals.css`) to SASS:
   ```bash
   mv styles/globals.css styles/globals.scss
   ```

2. Update `pages/_app.js` or `pages/_app.tsx` to use the new SASS file:
   ```javascript
   import '../styles/globals.scss';
   import 'bootstrap/dist/css/bootstrap.min.css';
   ```

3. Customize Bootstrap using SASS variables by creating a new file, e.g., `styles/bootstrap-custom.scss`:
   ```scss
   @import "~bootstrap/scss/bootstrap";
   ```

---

## 4. Setup Redux Toolkit

1. Create a `store` folder:
   ```bash
   mkdir store
   touch store/index.ts
   ```

2. Configure the Redux store in `store/index.ts`:
   ```typescript
   import { configureStore } from '@reduxjs/toolkit';

   export const store = configureStore({
     reducer: {},
   });

   export type RootState = ReturnType<typeof store.getState>;
   export type AppDispatch = typeof store.dispatch;
   ```

3. Provide the store to your app in `pages/_app.js` or `pages/_app.tsx`:
   ```typescript
   import { Provider } from 'react-redux';
   import { store } from '../store';

   function MyApp({ Component, pageProps }: any) {
     return (
       <Provider store={store}>
         <Component {...pageProps} />
       </Provider>
     );
   }

   export default MyApp;
   ```

---

## 5. Set Up ESLint and Prettier

1. Initialize ESLint:
   ```bash
   npx eslint --init
   ```

2. Create a `.prettierrc` file for Prettier:
   ```json
   {
     "semi": true,
     "singleQuote": true,
     "trailingComma": "es5"
   }
   ```

---

## 6. Add Sample Components

1. Create a `components` folder for reusable components:
   ```bash
   mkdir components
   touch components/Navbar.tsx
   ```

2. Example Navbar with Bootstrap 5:
   ```typescript
   const Navbar = () => {
     return (
       <nav className="navbar navbar-expand-lg navbar-light bg-light">
         <div className="container">
           <a className="navbar-brand" href="/">My App</a>
         </div>
       </nav>
     );
   };

   export default Navbar;
   ```

3. Import and use the Navbar in `pages/index.tsx`:
   ```typescript
   import Navbar from '../components/Navbar';

   export default function Home() {
     return (
       <>
         <Navbar />
         <div className="container mt-5">
           <h1>Welcome to My App!</h1>
         </div>
       </>
     );
   }
   ```

---

## 7. Add Global Styles

In `styles/globals.scss`, customize the theme:
```scss
$primary: #0d6efd;
$secondary: #6c757d;

@import "~bootstrap/scss/bootstrap";

body {
  font-family: 'Arial', sans-serif;
}
```

---

## 8. Run the Project

Start the development server:
```bash
npm run dev
```

Open your browser at `http://localhost:3000`.

---

## Optional Enhancements

1. Add **React Testing Library** for unit tests:
   ```bash
   npm install --save-dev @testing-library/react @testing-library/jest-dom @testing-library/user-event
   ```

2. Install **React Icons** for scalable icons:
   ```bash
   npm install react-icons
   ```

3. Install **next-seo** for advanced SEO:
   ```bash
   npm install next-seo
   ```

---

Happy Coding! 🚀
