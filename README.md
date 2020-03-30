# mock

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Deploy
First, merge changes into gh-pages branch. Then
```
npm run build
git add dist && git commit -m "Commit message"
git subtree push --prefix dist origin gh-pages
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


