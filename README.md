# codescan-export

CSV export is available in CodeScan Cloud with this command line tool available through npm.

[![oclif](https://img.shields.io/badge/cli-oclif-brightgreen.svg)](https://oclif.io)
[![Version](https://img.shields.io/npm/v/codescan-export.svg)](https://npmjs.org/package/codescan-export)
[![Downloads/week](https://img.shields.io/npm/dw/codescan-export.svg)](https://npmjs.org/package/codescan-export)
[![License](https://img.shields.io/npm/l/codescan-export.svg)](https://github.com/https://github.com/villagechief/codescan-export/https://github.com/villagechief/codescan-export/blob/master/package.json)

# Prerequisites

You will need:

- A CodeScan Cloud account.
- npm installed - [Installation Instructions](https://www.npmjs.com/get-npm)

# Installation

There are 2 ways to install the CodeScan Export tool.

### Install from Git

- Clone the repository.
- Navigate to the folder in your command line.
- Type npm install -g
- Once the installation is finished, type codescan-export -v to check the tool is available.

### Install from npm

- In your command line, type npm install -g codescan-export
- Once the installation is finished, type codescan-export -v to check the tool is available.

# Usage

## CLI Options

```
  $ codescan-export [ORGANIZATIONKEY] [PROJECTKEY]
```

| FLAG                                | USAGE                                                                                                                                                                                                                                                                  |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-f, --outputFile=outputFile`       | Output file                                                                                                                                                                                                                                                            |
| `-h, --help`                        | show CLI help                                                                                                                                                                                                                                                          |
| `-s, --server=server`               | Override server URL                                                                                                                                                                                                                                                    |
| `-t, --token=token`                 | Pass security token                                                                                                                                                                                                                                                    |
| `-v, --version`                     | show CLI version                                                                                                                                                                                                                                                       |
| `--assigned=assigned`               | To retrieve assigned or unassigned issues<br>Possible values: true, false, yes, no                                                                                                                                                                                     |
| `--assignees=assignees`             | Comma-separated list of assignee logins.The value '**me**' can be used as a placeholder for user who performs the request<br>Example value: admin,usera,**me**                                                                                                         |
| `--author=author`                   | SCM accounts. To set several values, the parameter must be called once for each value.`<br>Example value: author=torvalds@linux-foundation.org&author=linux@fondation.org                                                                                              |
| `--branch=branch`                   | The branch. To pull from a non-main branch, the parameter must specify the branch name.<br>Example value: dev                                                                                                                                                          |
| `--createdAfter=createdAfter`       | To retrieve issues created after the given date (inclusive).<br>Either a date (server timezone) or datetime can be provided.<br>If this parameter is set, createdSince must not be set<br>Example value: 2017-10-19 or 2017-10-19T13:00:00+0200                        |
| `--createdAt=createdAt`             | Datetime to retrieve issues created during a specific analysis<br>Example value: 2017-10-19T13:00:00+0200                                                                                                                                                              |
| `--createdBefore=createdBefore`     | To retrieve issues created before the given date (inclusive).Either a date (server timezone) or datetime can be provided.<br>Example value: 2017-10-19 or 2017-10-19T13:00:00+0200                                                                                     |
| `--createdInLast=createdInLast`     | To retrieve issues created during a time span before the current time (exclusive).<br>Accepted units are 'y' for year, 'm' for month, 'w' for week and 'd' for day.<br>If this parameter is set, createdAfter must not be set<br>Example value: 1m2w (1 month 2 weeks) |
| `--cwe=cwe`                         | Comma-separated list of CWE identifiers. Use 'unknown' to select issues not associated to any CWE.<br>Example value: 12,125,unknown                                                                                                                                    |
| `--delimiter=delimiter`             | Delimiter mark. Defaults to ,                                                                                                                                                                                                                                          |
| `--escape=escape`                   | Escape mark. Defaults to "                                                                                                                                                                                                                                             |
| `--quote=quote`                     | Quote mark. Defaults to "                                                                                                                                                                                                                                              |
| `--resolutions=resolutions`         | Comma-separated list of resolutions<br>Possible values: FALSE-POSITIVE, WONTFIX, FIXED, REMOVED<br>Example value: FIXED,REMOVED                                                                                                                                        |
| `--resolved=resolved`               | To match resolved or unresolved issues<br>Possible values: true, false, yes, no                                                                                                                                                                                        |
| `--severities=severities`           | Comma-separated list of severities<br>Possible values: INFO, MINOR, MAJOR, CRITICAL, BLOCKER<br>Example value: BLOCKER,CRITICAL                                                                                                                                        |
| `--sinceLeakPeriod=sinceLeakPeriod` | To retrieve issues created since the leak period.<br>If this parameter is set to a truthy value, createdAfter must not be set and one component id or key must be provided.<br>Possible values: true, false, yes, no                                                   |
| `--statuses=statuses`               | Comma-separated list of statuses<br>Possible values: OPEN, CONFIRMED, REOPENED, RESOLVED, CLOSED<br>Example value: OPEN,REOPENED                                                                                                                                       |
| `--tags=tags`                       | Comma-separated list of tags<br>Example value: security,convention                                                                                                                                                                                                     |
| `--types=types`                     | Comma-separated list of types<br>Possible values: CODE_SMELL, BUG, VULNERABILITY, SECURITY_HOTSPOT<br>Default value: BUG,VULNERABILITY,CODE_SMELL<br>Example value: CODE_SMELL,BUG                                                                                     |
| `--[no-]verifySslCa`                | Use--no-verifySslCa to skip verification of the server certificate against the list of supplied CAs.`<br>This can be helpful in case of using self-signed certificates.                                                                                                |

## Authentication

It is recommended that you create an environment variable for your CodeScan Cloud token to avoid using it in plaintext for each call. Name the variable `CODESCAN_TOKEN` and assign it the token created in your [Account Security Settings](https://app.codescan.io/account/security/).

With the token set as an environment variable you can run the tool with the following command.

`codescan-export [ORGANISATION KEY] [PROJECT KEY]`

[How to find your Organisation Key](https://docs.codescan.io/hc/en-us/articles/360020037992-How-to-find-an-Organization-Key-in-CodeScan-Cloud)

[How to find your Project Key](https://docs.codescan.io/hc/en-us/articles/360020038192-How-to-find-a-Project-Key-in-CodeScan)

Without the token set as an environment variable you can run the tool with the following command. Click on the links for information on how to find the keys.

`CODESCAN_TOKEN=[TOKEN] codescan-export [ORGANISATION KEY] [PROJECT KEY]`

[Generate your Security Token](https://app.codescan.io/account/security/)

[How to find your Organisation Key](https://docs.codescan.io/hc/en-us/articles/360020037992-How-to-find-an-Organization-Key-in-CodeScan-Cloud)

[How to find your Project Key](https://docs.codescan.io/hc/en-us/articles/360020038192-How-to-find-a-Project-Key-in-CodeScan)

Type `codescan-export -h` to see the detailed usage for this tool including how to filter the issues.
