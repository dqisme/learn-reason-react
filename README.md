# learn-reason-react

## Setup

1. Initialize NodeJS project

```bash
npm init --yes
```

2. Install dependencies

```bash
npm install --save-dev bs-platform
npm install --save reason-react
```

3. Add to scripts of `package.json`

```json
{
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

  - `src/index.res`
  ```rescript
  Js.log("hello world")
  ```