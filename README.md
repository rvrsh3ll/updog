![Version 2.0](http://img.shields.io/badge/version-v2.0-green.svg)
![Python 3.11+](http://img.shields.io/badge/python-3.11+-blue.svg)
[![MIT License](http://img.shields.io/badge/license-MIT%20License-blue.svg)](https://github.com/sc0tfree/updog/blob/master/LICENSE)
[![sc0tfree Twitter](http://img.shields.io/twitter/url/http/shields.io.svg?style=social&label=Follow)](https://twitter.com/sc0tfree)

<p>
  <img src="https://sc0tfree.squarespace.com/s/updog.png" width=85px alt="updog"/>
</p>

Updog is a replacement for Python's `SimpleHTTPServer`. 
It allows uploading and downloading via HTTP/S, 
can set ad hoc SSL certificates and use HTTP basic auth.

<p align="center">
  <img src="https://sc0tfree.squarespace.com/s/updog-screenshot.png" alt="Updog screenshot"/>
</p>

## Installation

Install using pip:

`pip install updog`

Or using pipx (recommended for CLI tools):

`pipx install updog`

For development:

```bash
git clone https://github.com/sc0tfree/updog.git
cd updog
poetry install
poetry run updog
```

## Usage

`updog [-d DIRECTORY] [-b ADDRESS] [-p PORT] [--password PASSWORD] [--ssl | --ssl-cert CERT --ssl-key KEY] [--cors] [--hide-base-path]`

| Argument                            | Description                                      |
|-------------------------------------|--------------------------------------------------| 
| -d DIRECTORY, --directory DIRECTORY | Root directory [Default=.]                       | 
| -b ADDRESS, --bind ADDRESS          | Bind to specific address [Default=0.0.0.0]       |
| -p PORT, --port PORT                | Port to serve [Default=9090]                     |
| --password PASSWORD                 | Use a password to access the page. (No username) |
| --ssl                               | Enable SSL with ad-hoc certificate               |
| --ssl-cert CERT                     | Path to custom SSL certificate                   |
| --ssl-key KEY                       | Path to custom SSL private key                   |
| --cors                              | Enable CORS headers                              |
| --hide-base-path                    | Hide full directory path (show relative paths)   |
| --version                           | Show version                                     |
| -h, --help                          | Show help                                        |

## Examples

**Serve from your current directory:**

`updog`

**Serve from another directory:**

`updog -d /another/directory`

**Serve from port 1234:**

`updog -p 1234`

**Password protect the page:**

`updog --password examplePassword123!`

*Please note*: updog uses HTTP basic authentication.
To login, you should leave the username blank and just
enter the password in the password field.

**Use an SSL connection (ad-hoc certificate):**

`updog --ssl`

**Use an SSL connection with custom certificates:**

`updog --ssl-cert /path/to/cert.pem --ssl-key /path/to/key.pem`

**Bind to a specific IP address:**

`updog -b 192.168.1.10 -p 8080`

**Enable CORS for web application testing:**

`updog --cors`

**Hide full directory paths (OpSec):**

`updog --hide-base-path`

## Thanks

A special thank you to [Nicholas Smith](http://nixmith.com) for
designing the updog logo.
