# Miteru

[![Gem Version](https://badge.fury.io/rb/miteru.svg)](https://badge.fury.io/rb/miteru)
[![Build Status](https://travis-ci.org/ninoseki/miteru.svg?branch=master)](https://travis-ci.org/ninoseki/miteru)
[![Maintainability](https://api.codeclimate.com/v1/badges/d90e1b5bbdd9663a17d1/maintainability)](https://codeclimate.com/github/ninoseki/miteru/maintainability)
[![Coverage Status](https://coveralls.io/repos/github/ninoseki/miteru/badge.svg?branch=master)](https://coveralls.io/github/ninoseki/miteru?branch=master)

Miteru is an experimental phishing kit detection tool.

## How it works

- It collects phishing suspicious URLs from [urlscan.io](https://urlscan.io/search/#certstream-suspicious).
- It checks a suspicious URL whether it contains a phishing kit (`*.zip` file) or not.

## Installation

```sh
$ gem install miteru
```

## Usage

```sh
$ miteru
Commands:
  miteru execute         # Execute the crawler
  miteru help [COMMAND]  # Describe available commands or one specific command
```

```sh
$ miteru help execute
Usage:
  miteru execute

Options:
  [--auto-download], [--no-auto-download]  # Enable or disable auto-download of *.zip file(s)
  [--download-to=DOWNLOAD_TO]              # Directory to download file(s)
                                           # Default: /tmp
  [--size=N]                               # Number of urlscan.io's results. (Max: 100,000)
                                           # Default: 100
  [--post-to-slack], [--no-post-to-slack]  # Post a message to Slack if it detects a phishing kit
  [--verbose], [--no-verbose]
                                           # Default: true

Execute the crawler
```

```sh
$ miteru execute
...
https://dummy1.com: it doesn't contain a phishing kit.
https://dummy2.com: it doesn't contain a phishing kit.
https://dummy3.com: it doesn't contain a phishing kit.
https://dummy4.com: it might contain a phishing kit (dummy.zip).
```
