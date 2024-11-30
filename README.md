# Next.js as Transitive Dep issue

1. Clone this repo
4. cd into `next-transitive` and run `npm install --install-links` (the option is so that the file: is actually installed instead of symlinked)
5. cd into `next-transitive/node_modules/next-app` and try to run `npx next build` or `npm run build`. They will both fail with the following:

```
> my-app@0.1.0 build
> next build

   ▲ Next.js 15.0.3

   Creating an optimized production build ...
Failed to compile.

./app/page.js
Module parse failed: Unexpected token (6:4)
File was processed with these loaders:
 * ../next/dist/build/webpack/loaders/next-flight-loader/index.js
 * ../next/dist/build/webpack/loaders/next-swc-loader.js
You may need an additional loader to handle the result of these loaders.
| export default function Home() {
|   return (
>     <div className={styles.page}>
|       <main className={styles.main}>
|         <Image

Import trace for requested module:
./app/page.js


> Build failed because of webpack errors
```