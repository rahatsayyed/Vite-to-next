# 🚀 Next.js Project Setup

## 📌 Steps to Migrate from Vite to Next.js

Follow the steps below to successfully migrate your Vite + React + TypeScript project to Next.js.

---

### 🗑️ 1. Delete the Vite.js File
Remove the existing Vite configuration file (`vite.config.ts` or `vite.config.js`) & `tsconfig.node.json` from your project.

---

### 📦 2. Install Next.js & Required Dependencies
Run the following command in your terminal to install Next.js and update React dependencies:
```sh
npm install next@latest react@latest react-dom@latest
```

---

### 📜 3. Update `package.json`
Modify your `package.json` file as shown below:

```json
{
  "name": "vite_react_shadcn_ts",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint"
  }
}
```

---

### 📂 4. Create an `App` Folder Inside `src`
Inside your `src` directory, create a new folder named `App`. This will contain your main application components.

---

### 📄 5. Create `layout.tsx` & `page.tsx`
Inside the `src/App` folder, create two new files: `layout.tsx` and `page.tsx`.

#### `layout.tsx`
```tsx
import "./global.css";

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  );
}
```

#### `page.tsx`
```tsx
"use client";

import App from "./App";

export default function Page() {
  return <App />;
}
```

---

### 📌 6. Move `App.tsx` to the `App` Folder
Relocate the existing `App.tsx` file into the `src/App` directory.

---

### 🎨 7. Rename `index.css` to `global.css`
Rename the `index.css` file to `global.css` and move it inside the `src/App` folder.

---

###  8. Rename `pages` to `component_pages`
Rename the `page` dir to `component_pages`.

---
### 9. Update `tsconfig.json`
```
{
  "compilerOptions": {
    "target": "ES2020",
    "lib": ["dom", "dom.iterable", "esnext"],
    "allowJs": true,
    "skipLibCheck": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noEmit": true,
    "esModuleInterop": true,
    "module": "esnext",
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "jsx": "preserve",
    "incremental": true,
    "plugins": [
      {
        "name": "next"
      }
    ],

    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    },
    "noImplicitAny": false
  },
  "include": ["next-env.d.ts", ".next/types/**/*.ts", "**/*.ts", "**/*.tsx"],
  "exclude": ["node_modules"]
}
```

---

### ✅ Final Steps
- Run the development server using:
  ```sh
  npm run dev
  ```
- Ensure everything is working properly and make adjustments if necessary.
- 🎉 Congratulations! Your project is now successfully migrated to Next.js.

---

### 💡 Additional Notes
- You can customize your `global.css` to fit your design needs.
- Modify the `layout.tsx` file to include a `<head>` section for meta tags and SEO optimizations.
- Consider adding additional Next.js features like dynamic routing and API routes.

---

🔗 **Happy Coding! 🚀**

