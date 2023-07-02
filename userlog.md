> :information_source: this log lists user most visible changes

> :warning: to find all changes use [changelog.txt](https://github.com/andry81-devops/gh-action--accum-gh-rate-limits/tree/HEAD/changelog.txt) file in a directory

> :information_source: Legend: :shield: - security; :wrench: - fixed; :new: - new; :pencil: - changed; :twisted_rightwards_arrows: - refactor

## 2023.07.02:
* :new: new: action.yml: added `ENABLE_REPO_STATS_COMMITS_URL_PRINT_TO_CHANGELOG` variable to be able to print Statistic Output Repository commit URL (approximated by +5min date) into being committed changelog file

## 2022.12.18:
* :pencil: changed: action.yml: removed `ENABLE_COMMIT_REFERENCE_URL_PRINT_TO_CHANGELOG` variable because is not possible to make a commit and in the same time save the commit hash in a being committed file

## 2022.12.11:
* :new: new: action.yml: added `ENABLE_COMMIT_REFERENCE_URL_PRINT_TO_CHANGELOG` variable to be able to print Commit Reference URL into the changelog file

## 2022.10.12:
* :new: new: action.yml: added `flags` parameter with builtin parse into `GH_WORKFLOW_FLAGS` environment variable as a single line string
* :new: new: action.yml: added ability to insert workflow run number into commit message after date/time prefix (`ENABLE_COMMIT_MESSAGE_WITH_WORKFLOW_RUN_NUMBER=1`)
* :pencil: changed: action.yml: use `$GH_WORKFLOW_ROOT/_common/update-permissions.sh` script to automate permissions update

## 2022.09.08:
* :wrench: fixed: action.yml: multiline input in `${{ input.env }}`

## 2022.08.26:
* :new: new: action.yml: added `ENABLE_GITHUB_ACTIONS_RUN_URL_PRINT_TO_CHANGELOG` and `GHWF_GITHUB_ACTIONS_RUN_URL` variables to be able to print GitHub Actions run URL into the changelog file

## 2022.08.12:
* :new: new: action.yml: flush print annotations at the last always executed step

## 2022.08.09:
* :new: new: action.yml: print commit reference url to the log

## 2022.05.11:
* :new: new: action.yml: added `commit_msg_entity` optional input parameter as replacement of `stat_entity` in the commit message
* :pencil: changed: action.yml: renamed `stat_entity_path` to `stat_entity` to select implementation
* :pencil: changed: action.yml: swapped `COMMIT_MESSAGE_PREFIX` and `COMMIT_MESSAGE_SUFFIX` in all scripts to further improve readability in case of GitHub commit message truncation

## 2022.05.06:
* :wrench: fixed: action.yml: `CHANGELOG_FILE` must be always not empty

## 2022.05.05:
* :new: new: bash: curl stderr print on error

## 2022.05.04:
* :new: new: action.yml: added `COMMIT_MESSAGE_PREFIX` to split an automated user commit message into prefix and suffix parts

## 2022.04.16:
* :wrench: fixed: action.yml: `mkdir` in a working copy moved after git checkout instead of before to avoid accidental remove on cleanup
* :pencil: changed: action.yml: added `mkdir-p` parameter usage

## 2022.04.15:
* :pencil: changed: action.yml: switched to use `andry81-devops/gh-action--git-checkout` action instead of `actions/checkout`

## 2022.04.02:
* :pencil: changed: action.yml: switch to use `actions/checkout@v3` action

## 2022.03.30:
* :pencil: changed: `commit_message_insert_time` composite action input parameter replaced by `ENABLE_COMMIT_MESSAGE_DATE_WITH_TIME` environment variable

## 2022.03.23:
* :new: new: action.yml: `env` input parameter to explicitly declare global environment variables
* :new: new: action.yml: `changelog_dir` variable usage is added

## 2022.02.19:
* :new: new: action.yml: added `commit_message_insert_time` input optional parameter and use `COMMIT_MESSAGE_DATE_TIME_PREFIX` instead of `STATS_DATE_UTC`
