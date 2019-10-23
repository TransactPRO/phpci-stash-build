# PHPCI Plugin for Atlassian Bitbucket Server (Stash) build status integration

[![SensioLabsInsight](https://insight.sensiolabs.com/projects/9e914e3d-c616-4a77-b001-00632c578e3d/big.png)](https://insight.sensiolabs.com/projects/9e914e3d-c616-4a77-b001-00632c578e3d)

[![Latest Stable Version](https://poser.pugx.org/transactpro/phpci-stash-build/v/stable?format=flat-square)](https://packagist.org/packages/transactpro/phpci-stash-build)
[![Total Downloads](https://poser.pugx.org/transactpro/phpci-stash-build/downloads?format=flat-square)](https://packagist.org/packages/transactpro/phpci-stash-build)
[![License](https://poser.pugx.org/transactpro/phpci-stash-build/license?format=flat-square)](https://packagist.org/packages/transactpro/phpci-stash-build)



## Install
First of all - `composer require transactpro/phpci-stash-build`

There are two ways this plugin can work - tokens and login/password.

Add settings from below to your PHPCI config (`/path/to/phpci/PHPCI/config.yml`):

### Login / password style:
```yml
stash_build:
    login: $STASH_USER
    password: $STASH_PASSWORD
    url: 'https://$STASH_URL:$PORT'
```

### Token style:
It's very similar to login/password style, but you have to install [Token Authenticator](https://marketplace.atlassian.com/plugins/com.thundermoose.plugins.stash-token-auth/server/overview) to your Bitbucket Server (Stash), before you can continue.

Add to your PHPCI config (`/path/to/phpci/PHPCI/config.yml`)
```yml
stash_build:
    auth_user: $STASH_USER
    auth_token: $STASH_TOKEN
    url: 'https://$STASH_URL:$PORT'
```

And you are ready to go.

## Usage
If installation was successful, then usage is easy as 1-2-3:

Example of `phpci.yml`:
```yml
setup:
  stash_build:
    status: INPROGRESS

success:
  stash_build:
    status: SUCCESSFUL

failure:
  stash_build:
    status: FAILED
```

That's all folks!
