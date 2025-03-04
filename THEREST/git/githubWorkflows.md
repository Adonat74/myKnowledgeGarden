# github workflows / actions

## permet qu'au push les test soient lancés ( important de faire npm install )

```yml
name: pushTest
run-name: ${{ github.actor }} is testing out GitHub Actions 🚀
on:
  push:
    branches:
      - main

jobs:
  Explore-GitHub-Actions:
    runs-on: ubuntu-latest

    strategy:
      matrix:
        node-version: [18.x, 20.x, 22.x]
        # See supported Node.js release schedule at https://nodejs.org/en/about/releases/

    steps:

      - uses: actions/checkout@v4

      - name: Use Node.js ${{ matrix.node-version }}
        uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node-version }}
          cache: 'npm'


      # Install dependencies
      - name: Install dependencies
        run: npm install


      - run: npm test
```

