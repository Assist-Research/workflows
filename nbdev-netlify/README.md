# nbdev Netlify

This is a simple action to use `nbdev` to build the docs, and then deploy them
to Netlify.

## Usage

To use a GitHub action you can just reference it on your Workflow file
(for more info check [this article by GitHub](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/configuring-a-workflow))

```yml
name: 'My Workflow'

on:
  release:
    types: [published]

jobs:
  deploy:
    name: 'Deploy to Netlify'
    steps:
      - uses: assist-research/worklows/nbdev-netlify@v1.0.0
        with:
          NETLIFY_AUTH_TOKEN: ${{ secrets.MY_TOKEN_SECRET }}
          NETLIFY_SITE_ID: ${{ secrets.MY_SITE_ID_SECRET }}
```

## Inputs 

As most GitHub actions, this action requires and uses some inputs, that you define in
your workflow file.

The inputs this action uses are:

|           Name           | Required |     Default     |                                                   Description                                                        |
|:------------------------:|:--------:|:---------------:|:------------------------------------------------------------------------------------------------------------------------:|
|   `NETLIFY_AUTH_TOKEN`   |  `true`  |       N/A       | The token needed to deploy your site ([generate here](https://app.netlify.com/user/applications#personal-access-tokens)) |
|    `NETLIFY_SITE_ID`     |  `true`  |       N/A       |                    The site to where deploy your site (get it from the API ID on your Site Settings)                     |
