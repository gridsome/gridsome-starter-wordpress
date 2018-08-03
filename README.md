# WordPress starter for Gridsome

## Guide

Add your WordPress URL to the plugin options.

```js
// gridsome.config.js

module.exports = {
  plugins: [
    {
      use: '@gridsome/source-wordpress',
      options: {
        baseUrl: 'YOUR_WORDPRESS_URL'
      }
    }
  ]
}

```

## Included templates

This starter includes basic templates for categories, tags and posts.
