# corwin-web

> A website just for Corwin <3

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

## Application Thoughts

The intent is to first provide a site that displays artwork well and automatically based on the popularity of tags. The most recent set of posts (judged by being posted at the same time) will be displayed in a larger pane occupying most of the screen at first. Other posts will be grouped based on tag frequency below the main set.

## Data Model
```javascript
var posts = {
    "title": string,
    "time": unix time,
    "resources": {
        string (resource name): string (resource relative path),
    },
    "content": string (can contain {r:"resource name"} to embed images),
}

var config = {
    "profile": {
        "image":
        "hover_image":
        "name":
        "bio":
    }
}
```