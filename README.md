# lodash

The repository contains [lodash](https://github.com/lodash/lodash) versions:

- 3.10.1
- 3.10.2

This repository was created because lodash 3.10.1 is vulnerable to [Prototype Pollution](https://snyk.io/vuln/SNYK-JS-LODASH-450202). However, [lodash](https://www.npmjs.com/package/lodash) has not published [3.x.x versions](https://www.npmjs.com/package/lodash/v/3.10.1) to npm in over 5 years.

As a result, for those who cannot upgrade to [4.17.15](https://www.npmjs.com/package/lodash/v/4.17.15) due to breaking changes, a patch for 3.10.2 was created here.

To install lodash@3.10.2:

```sh
npm install remarkablemark/lodash#3.10.2
```

## 3.10.1

The [branch](https://github.com/remarkablemark/lodash/tree/3.10.1) was created by running the following commands:

```sh
git clone https://github.com/remarkablemark/lodash.git
cd lodash
git checkout --orphan 3.10.1-post
git rm -rf .
rm package-lock.json
npm install lodash@3
mv node_modules/lodash/* .
rm -rf node_modules
# vim package.json
git add .
git commit -m 'feat: add lodash 3.10.1'
git push origin 3.10.1
```

## 3.10.2

The [branch](https://github.com/remarkablemark/lodash/tree/3.10.1) addresses [prototype pollution](https://github.com/lodash/lodash/pull/4627/files):

```sh
git checkout 3.10.1
git checkout -b 3.10.2
# https://github.com/lodash/lodash/pull/4627/files
git add .
git commit -m 'fix: fix prototype pollution vulnerabilities for baseMerge and set'
git grep -l '3.10.1' | xargs sed -i '' -e 's/3.10.1/3.10.2/g'
# vim README.md
git add .
git commit -m 'chore: upgrade version to 3.10.2'
git push origin 3.10.2
```
