## Build and Deploy React app to GitHub Pages

This GitHub Workflow Action will automate the process of building and deploying React app to GitHub page into `gh-pages` branch.

## Steps
### 1. Add `homepage` config
Add following config to your App's `package.json` file
```
"homepage": "https://<github_username>.github.io/<app_repo>"
```

### 2. Enable GitHub Pages
Enabling GitHub Pages from App Repository's Settings will create separate branch to deploy from and this helps us to keep our source code separate from the static website.

Set your source branch for GitHub Pages (Example: gh-pages) in `Settings -> Pages` section

### 3. Create GitHub Workflow Action 
Add this action inside your App Repository's Actions

```
name: Build and Deploy

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:

    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v3

    - name: Build and Deploy React app to GitHub Pages
      uses: omkartapale/react-deployment-gh-pages@v1.0.0
```

## License
[![GitHub license](https://img.shields.io/github/license/omkartapale/react-deployment-gh-pages?style=for-the-badge)](https://github.com/omkartapale/react-deployment-gh-pages/blob/main/LICENSE)

Copyright (c) 2022 Omkar Tapale
