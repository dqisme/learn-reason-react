# learn-reason-react

## Setup

Steps:

> For every step, you can check the bundle under `lib/js/src/index.js` after running `npm run build`.

- ReScript environment
- React
- JSX

### Steps for ReScript environment

1. Initialize NodeJS project

```bash
npm init --yes
```

2. Install BuckleScript

```bash
npm install --save-dev bs-platform
```

3. Add to scripts of `package.json`

```json
{
  "build:src": "bsb",
  "build": "bsb -make-world",
  "clean": "bsb -clean-world"
}
```

4. Add `bsconfig.json`

```json
{
    "name": "learn-reason-react",
    "sources": "src"
}
```

5. Add `.gitignore`

```
node_modules/
lib/
.merlin
.bsb.lock
```

6. Add source codes

  - `src/Index.res`
  ```rescript
  Js.log("hello world")
  ```

### Steps for React

7. Install React

```bash
npm install --save react react-dom reason-react
```

8. Add BuckleScript dependencies to `bsconfig.json`

```json
{
  // ...
  "bs-dependencies": [
    "reason-react"
  ]
}
```

9. Change the `Index.res` with React snippets

```rescript
switch ReactDOM.querySelector("#root") {
| Some(root) => ReactDOM.render(React.string("hello world"), root)
| None => ()
}
```

### Steps for JSX

10. Add Reason configuration in `bsconfig.json` to recognize JSX

```json
{
  // ...
  "reason": {"react-jsx": 3}
}
```

11. Change the `Index.res` with JSX syntax

```rescript
switch ReactDOM.querySelector("#root") {
| Some(root) => ReactDOM.render(<p>{React.string("hello world")}</p>, root)
| None => ()
}
```