

# Netlify - build error - can not find rollup


## Example:

```
3:07:38 PM: $ npm run build
3:07:39 PM: > cinema-time-frontend@0.0.0 build
3:07:39 PM: > vite build
3:07:40 PM: Failed during stage 'building site': Build script returned non-zero exit code: 2 (https://ntl.fyi/exit-code-2)
3:07:40 PM: /opt/build/repo/node_modules/rollup/dist/native.js:64
3:07:40 PM: 		throw new Error(
3:07:40 PM: 		      ^
3:07:40 PM: Error: Cannot find module @rollup/rollup-linux-x64-gnu. npm has a bug related to optional dependencies (https://github.com/npm/cli/issues/4828). Please try `npm i` again after removing both package-lock.json and node_modules directory.

// ...
// ...

3:07:40 PM: Node.js v22.16.0
3:07:40 PM:
3:07:40 PM: "build.command" failed                                       
3:07:40 PM: ────────────────────────────────────────────────────────────────
3:07:40 PM:

// ...
// ...

```


## Fix:

- delete node_modules
- delete package-lock.json
- run "npm install"
- commit & push


