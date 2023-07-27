This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) to show an issue with next.js sourcemaps.

STR:
- `npm run build`
- upload `.next/static/chunks/main-26f0defd1fe4aedb.js[.map]` to https://evanw.github.io/source-map-visualization/
- select `webpack://_N_E/node_modules/@swc/helpers/esm/_interop_require_wildcard.js` as the original source
- for comparison, upload `.next/static/chunks/pages/_app-27374a655d3a2ebe.js[.map]` to https://evanw.github.io/source-map-visualization/ and select `webpack://_N_E/src/_interop_require_wildcard.js`

Alternatively, you can look at these sourcemaps here:
- `webpack://_N_E/node_modules/@swc/helpers/esm/_interop_require_wildcard.js`: https://app.replay.io/recording/5072126e-507f-43d9-8c9e-889ad2bfd0dd/sourcemap/o4-80-c194bb-ec5646
- `webpack://_N_E/src/_interop_require_wildcard.js`: https://app.replay.io/recording/5072126e-507f-43d9-8c9e-889ad2bfd0dd/sourcemap/o6-6-c194bb-5d30d7

The sourcemap viewer shows that in the first sourcemap (of a source under `node_modules`) almost all sourcemap entries point to the first column of a line in the original source. This makes it impossible to do "scope mapping" (showing scopes with original variable names) in a debugger.
