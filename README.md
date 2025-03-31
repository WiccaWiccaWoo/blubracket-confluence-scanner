# Confluence Risk Scanner

The easiest way to scan Atlassian Confluence Cloud/Server for secrets, PII, and non-inclusive language.

This fully-functional solution uses the BluBracket CLI to do the risk detection heavy lifting,
combined with open-source helper code written in Python to interact with CLI.

This tool runs entirely locally. Installation is almost as easy as cloning the repo,
and you should have a working POC in minutes.

**This is a modified Python wrapper script based on [this POC](https://github.com/BluBracket/confluence-risk-scanner) by BluBracket.**

This POC enables users to scan **all** spaces in Atlassian Confluence Cloud/Server.

## Installation

1. Install the BluBracket CLI (see below)
2. Clone or download this repo

### Install the BluBracket CLI

The BluBracket CLI is a high-performance, compact risk scanner written in Go. Unlike some tools, it runs entirely locally without sending any data to remote hosts (unless explicitly configured otherwise).

macOS, multiple Linux distros, and Windows are all supported.

Use these direct links to download the executables:

- macOS: https://static.blubracket.com/cli/latest/blubracket-macos
- Linux: https://static.blubracket.com/cli/latest/blubracket-linux
- Windows: https://static.blubracket.com/cli/latest/blubracket-win.exe


## Usage
### Set Credentials
Enter username and API key into `constants.py` file.

```
USERNAME="<username@domain>"
API_KEY="<confluence api key>"
```
### Examples
```
# Scan all pages in a space
python confluence_risk_scanner.py \
    --url https://<domain>.atlassian.net \
    --space-key <confluence space key> \
    --output result.jsonl

# Scan all pages in all spaces
python confluence_risk_scanner.py \
    --url https://<domain>.atlassian.net \
    --scan-all \
    --output result.jsonl
```

To see more options `python confluence_risk_scanner.py --help`.


