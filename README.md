# vue-cli-typescript-components

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Run your unit tests
```
yarn test:unit
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


## Dockerize
Follow guidelines from [Dockerize VueJS](https://vuejs.org/v2/cookbook/dockerize-vuejs-app.html)

### To build a Docker image
```
docker build -t vuejs-cookbook/dockerize-vuejs-app .
```

### To run VueJS app in a Docker container
```
docker run -it -p 8080:80 --rm --name dockerize-vuejs-app-1 vuejs-cookbook/dockerize-vuejs-app
```

## Azure pipelines
