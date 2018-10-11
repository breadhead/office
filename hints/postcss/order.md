## ;TLDR

Такой CSS 
```
.mobileCardHolderOpen {
  @media (--mediumDown) {
    & .content {
      display: none;
    }

    & .aside {
      @media (--mediumDown) {
        display: flex;
        width: 100%;
        z-index: 2;
      }

      position: relative;
      top: auto;
      bottom: auto;
      right: auto;
      left: auto;
    }
  }
}
```


Так работает:

```
module.exports = {
  plugins: [
    require('postcss-preset-env'),
    require('postcss-import')({ path: context }),
    require('postcss-custom-media'),
    require('postcss-nesting'),
  ],
};
```

Так не работает:

```
module.exports = {
  plugins: [
    require('postcss-preset-env'),
    require('postcss-import')({ path: context }),
    require('postcss-nesting'),
    require('postcss-custom-media'),    
  ],
};
```

**Причина**: порядок подключения модулей `postcss-custom-media` и `postcss-nesting` имеет значение.
