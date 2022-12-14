# v-spoiler

<img src="src/assets/logo.png" alt="logo" width="200"/>

Vue Spoiler is simple component for showing and hiding content. It could be useful for build accordions, or to hiding long agreements.

Component based on slot body height and give possibility to trigger toggling content visibility by your way.

## [Documents and live demo](http://bonilka.github.io/v-spoiler/)
## Quick start

### Install

```
npm install v-spoiler
```

### Include

1. Global include

```
// main.js

import VSpoiler from 'v-spoiler';
import 'v-spoiler/dist/v-spoiler.css';
app.component('VSpoiler', VSpoiler);

```

2. Local include

```
// App.vue

import VSpoiler from 'v-spoiler';
import 'v-spoiler/dist/v-spoiler.css';

export default {
  components: {
    VSpoiler
  }
}

```

### Usage

```
<v-spoiler v-model="value">
      <div>
        Long content here...
      </div>
</v-spoiler>
```

## Development
```
npm install
npm run serve
```

### Compiles and minifies for demo production
```
npm run build
```

### Compiles and minifies lib for production
```
npm run build:lib
```

### Lints and fixes files
```
npm run lint
```
