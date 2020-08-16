# eslint-changed-files
Github action to run eslint on changed files in a pull request.

```yml
...:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v1
        with:
          node-version: 9.8.0
      - name: Install
        run: npm ci
      - name: Run ESLint on changed files
        uses: tj-actions/eslint-changed-files@v4
        with:
          config-path: '/path/to/.eslintrc'
          ignore-path: '/path/to/.eslintignore'
          extensions: 'ts,tsx,js,jsx'
          extra-args: '--max-warnings=0'
```


## Inputs

|   Input        |    type     |  required     |  default              |
|:-------------:|:-----------:|:-------------:|:---------------------:|
| token         |  `string`   |    `false`    | `${{ github.token }}` |
| config-path   |  `string`   |    `false`    |  `'.eslintrc'`        |
| ignore-path   |  `string`   |    `false`    |  `''`                 |
| extensions    |  `string[]` |    `false`    |  `'ts,tsx,js,jsx'`    |
| extra-args    |  `string`   |    `false`    |  `''`                 |
