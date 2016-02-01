# git-credential-env

[![Build status][build-badge]][build-href]


A git credential helper for setting git credentials from environment variables. Useful for CI deployments with Travis.

## quick example
#### local install
```bash
npm install git-credential-env
SOME_ENV_VAR=foo
ANOTHER_ENV_VAR=bar
git config --global credential.helper "$PWD/node_modules/.bin/git-credential-env -u=SOME_ENV_VAR -p=ANOTHER_ENV_VAR"
```

#### global install
```bash
npm install git-credential-env -g
SOME_ENV_VAR=foo
ANOTHER_ENV_VAR=bar
git config --global credential.helper "env --username=SOME_ENV_VAR --password=ANOTHER_ENV_VAR"
```

The git username will be `foo` and the password will be `bar`, i.e. git-credential-env will return:

```
username=foo
password=bar
```

You can read more about git credential helpers here: http://git-scm.com/book/en/v2/Git-Tools-Credential-Storage

## usage
```
Usage: git-credential-env get {OPTIONS}

Options:

  --username, -u The name of environment variable containing the git username

  --password, -p The name of environment variable containing the git password
```



[build-badge]: https://travis-ci.org/L33T-KR3W/git-credential-env.svg
[build-href]: https://travis-ci.org/L33T-KR3W/git-credential-env
