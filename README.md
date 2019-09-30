# WordPress starter for Gridsome

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/gridsome/gridsome-starter-wordpress)

## Install

`gridsome create my-gridsome-project wordpress`

## Guide

Add your WordPress URL to the plugin options.

```js
// gridsome.config.js

module.exports = {
  plugins: [
    {
      use: '@gridsome/source-wordpress',
      options: {
        baseUrl: 'YOUR_WEBSITE_URL', // required
        typeName: 'WordPress', // GraphQL schema name
      }
    }
  ],
  // Setup template routes for any WordPress collection
  templates: {
    WordPressPost: '/:year/:month/:day/:slug',
    WordPressTag: '/tag/:slug'
  },
}

```

See all [options](https://gridsome.org/plugins/@gridsome/source-wordpress).

## Included templates

This starter includes basic templates for categories, tags and posts.
