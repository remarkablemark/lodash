# lodash

[Lodash](https://github.com/lodash/lodash)

## 3.10.1

[Branch](https://github.com/remarkablemark/lodash/tree/3.10.1):

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

[Branch](https://github.com/remarkablemark/lodash/tree/3.10.1) contains [prototype pollution fixes](https://github.com/lodash/lodash/pull/4627/files):

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
