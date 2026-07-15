# Vite / Next.js / Vue → Android Native App (Capacitor)

> Works for: Next.js • Vite • Vue • React (CRA)

---

# 1. Identify Framework

## Check package.json

| Dependency | Framework |
|------------|-----------|
| next | Next.js |
| vite | Vite |
| vue | Vue |
| react-scripts | React (CRA) |

---

# 2. Check Build Directory

## Next.js

Check:

```ts
next.config.ts
```

Required:

```ts
output: "export"
```

Build Directory:

```
out/
```

---

## Vite

Check:

```ts
vite.config.ts
```

Default:

```ts
build: {
  outDir: "dist"
}
```

If `outDir` isn't specified:

```
dist/
```

---

## Vue (Vite)

Same as Vite

```
dist/
```

---

## React (CRA)

```
build/
```

---

## Verify Build Directory

Run

```bash
npm run build
```

A new folder should appear.

Examples

```
out/
dist/
build/
```

---

# 3. Bun → npm Migration

## Remove Bun

Linux/macOS

```bash
rm bun.lock
```

Windows

```cmd
del bun.lock
```

---

## Install Dependencies

```bash
npm install
```

Generates

```
package-lock.json
```

---

## Remove Old Dependencies (Optional)

Linux/macOS

```bash
rm -rf node_modules
rm package-lock.json
npm install
```

Windows

```cmd
rmdir /s /q node_modules
del package-lock.json
npm install
```

---

## Update Scripts

Replace Bun commands.

Example

```json
"scripts": {
  "dev": "next dev",
  "build": "next build",
  "start": "next start"
}
```

Remove things like

```json
"start": "NODE_ENV=production bun .next/standalone/server.js"
```

---

# 4. Configure Framework

## Next.js (REQUIRED)

Open

```
next.config.ts
```

Replace

```ts
output: "standalone"
```

with

```ts
output: "export",

trailingSlash: true,

images: {
    unoptimized: true
}
```

Keep existing options like

```ts
reactStrictMode
typescript
eslint
```

unless you specifically want to change them.

---

## Vite

Usually no changes required.

If needed

```ts
build: {
    outDir: "dist"
}
```

---

## Vue

Usually no changes required.

---

## React CRA

Usually no changes required.

---

# 5. Install Capacitor

Core packages

```bash
npm install @capacitor/core @capacitor/cli @capacitor/android
```

Useful plugins

```bash
npm install \
@capacitor/app \
@capacitor/status-bar \
@capacitor/splash-screen \
@capacitor/keyboard
```

---

# 6. Initialize Capacitor

```bash
npx cap init
```

Example

```
App Name

My App

Package Name

com.example.myapp
```

---

# 7. Configure webDir

Open

```
capacitor.config.ts
```

Set according to framework

| Framework | webDir |
|------------|--------|
| Next.js | out |
| Vite | dist |
| Vue | dist |
| CRA | build |

Example

```ts
webDir: "out"
```

---

# 8. Build Project

```bash
npm run build
```

Verify build folder exists.

---

# 9. Add Android Platform

```bash
npx cap add android
```

Creates

```
android/
```

---

# 10. Sync Web Assets

```bash
npx cap sync
```

Run after every frontend build.

---

# 11. Open Android Studio

```bash
npx cap open android
```

---

# 12. Run on Device

Inside Android Studio

```
Run ▶
```

or

```bash
npx cap run android
```

---

# 13. Daily Development Workflow

```
Modify frontend
        │
        ▼
npm run build
        │
        ▼
npx cap sync
        │
        ▼
npx cap open android
        │
        ▼
Run app
```

---

# 14. Folder Reference

| Folder | Purpose |
|---------|----------|
| src | Source code |
| public | Static assets |
| node_modules | Installed packages |
| android | Native Android project |
| out | Next.js exported website |
| dist | Vite/Vue build output |
| build | CRA build output |
| .next | Next.js build cache |

---

# 15. public vs Build Folder

| Folder | Edit? | Purpose |
|---------|-------|----------|
| public | ✅ | Images, icons, fonts, static assets |
| out | ❌ | Next.js generated website |
| dist | ❌ | Vite/Vue generated website |
| build | ❌ | CRA generated website |

Never set

```
webDir = public
```

Always use

```
out
dist
build
```

---

# 16. Common Issues

## Blank / White Screen

- Verify `webDir`
- Run `npm run build`
- Run `npx cap sync`

---

## Old App Showing

```bash
npm run build
npx cap sync
```

---

## Images Missing

Next.js

```ts
images: {
    unoptimized: true
}
```

---

## 404 / Routing Issues

Next.js

```ts
trailingSlash: true
```

---

## Wrong Build Folder

Check

```
next.config.ts
vite.config.ts
capacitor.config.ts
```

---

## Plugins Not Working

```bash
npx cap sync
```

---

## Android Folder Missing

```bash
npx cap add android
```

---

# 17. Command Cheat Sheet

Install packages

```bash
npm install
```

Development

```bash
npm run dev
```

Build

```bash
npm run build
```

Initialize Capacitor

```bash
npx cap init
```

Add Android

```bash
npx cap add android
```

Sync

```bash
npx cap sync
```

Open Android Studio

```bash
npx cap open android
```

Run Android

```bash
npx cap run android
```

---

# 18. Framework Comparison

| Framework | Config File | Build Folder | webDir |
|------------|------------|-------------|--------|
| Next.js | next.config.ts | out | out |
| Vite | vite.config.ts | dist | dist |
| Vue (Vite) | vite.config.ts | dist | dist |
| React CRA | package.json | build | build |

---

# 19. Useful References

## Capacitor

https://capacitorjs.com/docs

## Android Platform

https://capacitorjs.com/docs/android

## Next.js Static Export

https://nextjs.org/docs/app/building-your-application/deploying/static-exports

## Vite Build

https://vite.dev/guide/build

## Vue + Vite

https://vuejs.org/guide/scaling-up/tooling.html

## Android Studio

https://developer.android.com/studio