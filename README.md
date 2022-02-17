<p align="center">
  <a href="#"><img src="https://img.shields.io/github/repo-size/andry81-devops/gh-action--accum-gh-rate-limits" valign="middle" alt="GitHub repo size in bytes" /></a>
• <a href="https://github.com/XAMPPRocky/tokei"><img src="https://tokei.rs/b1/github/andry81-devops/gh-action--accum-gh-rate-limits?category=lines" valign="middle" alt="lines of text by tokei.rs" /></a>
</p>

<p align="center">
  <a href="https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/commits/master/traffic/views">
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=Github%20views|all&query=count&url=https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/raw/master/traffic/views/latest-accum.json?raw=True&logo=github" valign="middle" alt="GitHub views|any|total" />
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=14d&query=count&url=https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/raw/master/traffic/views/latest.json?raw=True" valign="middle" alt="GitHub views|any|14d" /></a>
• <a href="https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/commits/master/traffic/views">
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=Github%20views|unq&query=uniques&url=https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/raw/master/traffic/views/latest-accum.json?raw=True&logo=github" valign="middle" alt="GitHub views|unique per day|total" />
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=14d&query=uniques&url=https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/raw/master/traffic/views/latest.json?raw=True" valign="middle" alt="GitHub views|unique per day|14d" /></a>
</p>

<p align="center">
  <a href="https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/commits/master/traffic/clones">
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=Github%20clones|all&query=count&url=https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/raw/master/traffic/clones/latest-accum.json?raw=True&logo=github" valign="middle" alt="GitHub clones|any|total" />
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=14d&query=count&url=https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/raw/master/traffic/clones/latest.json?raw=True" valign="middle" alt="GitHub clones|any|14d" /></a>
• <a href="https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/commits/master/traffic/clones">
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=Github%20clones|unq&query=uniques&url=https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/raw/master/traffic/clones/latest-accum.json?raw=True&logo=github" valign="middle" alt="GitHub clones|unique per day|total" />
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=14d&query=uniques&url=https://github.com/andry81-stats/gh-action--accum-gh-rate-limits--gh-stats/raw/master/traffic/clones/latest.json?raw=True" valign="middle" alt="GitHub clones|unique per day|14d" /></a>
</p>

<p align="center">
  <a href="https://github.com/andry81-devops/gh-action--accum-gh-rate-limits/commits">
    <img src="https://img.shields.io/github/commits-since/andry81-devops/gh-action--accum-gh-rate-limits/latest?sort=semver&label=Github%20commits%20since%20latest" valign="middle" alt="GitHub commits since latest version" /></a>
  <a href="https://github.com/andry81-devops/gh-action--accum-gh-rate-limits/releases">
    <img src="https://img.shields.io/github/v/release/andry81-devops/gh-action--accum-gh-rate-limits?include_prereleases&label=latest" valign="middle" alt="latest release name" /></a>
</p>

---

<p align="center">
  <a href="https://github.com/andry81-devops/gh-action--accum-gh-rate-limits/blob/master/userlog.md">Userlog</a>
• <a href="https://github.com/andry81-devops/gh-action--accum-gh-rate-limits/blob/master/changelog.txt">Changelog</a>
• <a href="#dependecies">Dependencies</a>
• <a href="#known_issues">Known issues</a>
• <a href="#copyright-and-license"><img src="https://github.com/andry81/andry81/raw/master/badges/mit-license.svg" valign="middle" alt="copyright and license" />&nbsp;Copyright and License</a>
</p>

<h4 align="center">GitHub composite action to request and accumulate an account rate limits.<br/>
<br/>
Tutorial to use with: https://github.com/andry81-devops/github-accum-stats</h4>

##

# gh-action--accum-gh-rate-limits@master

**Features**:

* You may directly point the statistic as commits list:
  `https://github.com/{{REPO_OWNER}}/{{REPO}}--gh-stats/commits/master/traffic/rate/limits`

* Workflow is used [accum-rate-limits.sh](https://github.com/andry81-devops/gh-workflow/blob/master/bash/github/accum-rate-limits.sh) bash script to accumulate rate limits statistic

* The script accumulates statistic both into a single file and into a set of files grouped by year and allocated per day:
  `traffic/rate/limits/by_year/YYYY/YYYY-MM-DD.json`

# USAGE

> :warning: You must replace all placeholder into respective values:

* `{{REPO_OWNER}}` -> repository owner
* `{{REPO}}` -> your repository

## Examples:

`.github/workflows/accum-gh-rate-limits.yml`:

```yml
name: GitHub rate limits at every 8 hours accumulator

on:
  schedule:
    - cron: "0 */8 * * *"
  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

jobs:
  accum-gh-rate-limits:
    runs-on: ubuntu-latest

    steps:
      - uses: {{REPO_OWNER}}/gh-action--accum-gh-rate-limits@master
        with:
          deps_repo_owner:          {{REPO_OWNER}}
          deps_repo_branch:         master
          deps_repo_read_token:     ${{ github.token }}

          stat_owner:               {{REPO_OWNER}}
          stat_entity_path:         rate_limit
          stat_read_token:          ${{ secrets.READ_STATS_TOKEN }}

          curl_flags: >-
            -H 'Cache-Control: no-cache'

          output_repo_owner:        {{REPO_OWNER}}
          output_repo:              {{REPO}}--gh-stats
          output_repo_branch:       master
          output_repo_dir:          traffic/rate/limits
          output_repo_write_token:  ${{ secrets.WRITE_STATS_TOKEN }}
```

> :information_source: You can use `secrets.READ_STATS_TOKEN` instead of `secrets.WRITE_STATS_TOKEN` as long as there is the same owner.

> :warning: You must use different values for `deps_repo_owner` and `output_repo_owner` if there is actually different owners.

> :information_source: See <a href="https://github.com/andry81-devops/github-accum-stats/blob/master/README.md#reuse">REUSE</a> section for details if you have multiple repositories and want to store all workflow scripts in a single repository.

## Dependencies<a name="dependecies"></a>

* https://github.com/andry81-devops/gh-workflow

## Known Issues<a name="known_issues"></a>

The action has supported not all features of a generic GitHub action: https://github.com/actions/runner/issues/646

> **What does Composite Run Steps Not Support**
>
> We don't support setting conditionals, continue-on-error, timeout-minutes, "uses", and secrets on individual steps within a composite action right now.
>
> (Note: we do support these attributes being set in workflows for a step that uses a composite run steps action)

## Copyright and License<a name="copyright-and-license"></a>

Code and documentation copyright 2022 Andrey Dibrov. Code released under [MIT License](https://github.com/andry81-devops/gh-action--accum-gh-rate-limits/blob/master/license.txt)
