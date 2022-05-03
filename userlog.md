> :information_source: this log lists user most visible changes

> :warning: to find all changes use [changelog.txt](https://github.com/andry81-devops/gh-action--accum-gh-rate-limits/blob/master/changelog.txt) file in a directory

## 2022.05.04:
* new: action.yml: added `COMMIT_MESSAGE_PREFIX` to split an automated user commit message into prefix and suffix parts

## 2022.04.16:
* fixed: action.yml: `mkdir` in a working copy moved after git checkout instead of before to avoid accidental remove on cleanup
* changed: action.yml: added `mkdir-p` parameter usage

## 2022.04.15:
* changed: action.yml: switched to use `andry81-devops/gh-action--git-checkout` action instead of `actions/checkout`

## 2022.04.02:
* changed: action.yml: switch to use `actions/checkout@v3` action

## 2022.03.30:
* changed: `commit_message_insert_time` composite action input parameter replaced by `ENABLE_COMMIT_MESSAGE_DATE_WITH_TIME` environment variable

## 2022.03.23:
* new: action.yml: `env` input parameter to explicitly declare global environment variables
* new: action.yml: `changelog_dir` variable usage is added

## 2022.02.19:
* new: action.yml: added `commit_message_insert_time` input optional parameter and use `COMMIT_MESSAGE_DATE_TIME_PREFIX` instead of `STATS_DATE_UTC`
