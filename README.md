# Test github actions

## Overview

This is base code for testing [packagecloud-github-action](https://github.com/computology/packagecloud-github-action)
The github action merely pushes a package to packagecloud.io.
The main file is [.github/workflows/upload.yml] (https://github.com/nethsix/pc_push_test/blob/master/.github/workflows/upload.yml)
The `upload.yml` workflow:

* Build a python package from source code in `packagecloud-test` directory, which is from [packagecloud-test-package](https://github.com/computology/python-test-packages)
* Use packagecloud-github-action, which contains [package_cloud gem](https://rubygems.org/gems/package_cloud/) to push the package to your packagecloud.io repository

## Pre-requisites

You need to create an account on <https://packagecloud.io>.

## Steps

* Fork this repo from github.com
* Clone the repo to your local host
* On your local host, `cd` into the repo
* Download `gh` cli (if you don't have it)
* `gh secret set packagecloud_token -b "<YOUR PACKAGECLOUD API TOKEN"`
  * You can get your packagecloud api token from: <https://packagecloud.io/api_token>
* Modify `.github/workflows/upload.yml` section as commented in the file (look for '###### MODIFY')
  * You can set your packagecloud user, repo, etc.
* Make commit
* Push to github
  * This will trigger the github action
