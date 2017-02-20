# Yarn --link-duplicates bug

Reference: https://github.com/yarnpkg/yarn/pull/2620#issuecomment-281146567

This appears to be caused by the multiple webpack versions installed (`@kadira/storybook` installs webpack@1, project
uses webpack@2).

### Reproduction

```
$ yarn --link-duplicates                                                                                                                                                                                     12:11:42
yarn install v0.21.2
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
error An unexpected error occurred: "EEXIST: file already exists, link '/home/git/forks/yarn-link-bug/node_modules/@kadira/storybook/node_modules/enhanced-resolve/node_modules/memory-fs/.npmignore' -> '/home/git/forks/yarn-link-bug/node_modules/babel-loader/node_modules/enhanced-resolve/node_modules/memory-fs/.npmignore'".
info If you think this is a bug, please open a bug report with the information provided in "/home/git/forks/yarn-link-bug/yarn-error.log".
info Visit https://yarnpkg.com/en/docs/cli/install for documentation about this command.
```
