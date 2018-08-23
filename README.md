<p align='center'>
  <img src="https://i.imgur.com/n2U6nVH.png" alt="Logo"> <br>
  <img src="https://img.shields.io/badge/Version-1.0.9-brightgreen.svg?style=style=flat-square" alt="version">
  <img src="https://img.shields.io/badge/python-3-orange.svg?style=style=flat-square" alt="Python Version">
  <img src="https://img.shields.io/aur/license/yaourt.svg?style=style=flat-square" alt="License">
</p>

## What is a CMS?
> A content management system (CMS) manages the creation and modification of digital content. It typically supports multiple users in a collaborative environment. Some noteable examples are: *WordPress, Joomla, Drupal etc*.

## Release History
```
- Version 1.0.9 [21-08-2018]
- Version 1.0.8 [14-08-2018]
- Version 1.0.7 [07-08-2018]
- Version 1.0.6 [23-07-2018]
- Version 1.0.5 [19-07-2018]
- Version 1.0.4 [17-07-2018]
- Version 1.0.3 [06-07-2018]
- Version 1.0.2 [06-07-2018]
- Version 1.0.1 [19-06-2018]
- Version 1.0.0 [15-06-2018]
```
[Changelog File](https://github.com/Tuhinshubhra/CMSeeK/blob/master/CHANGELOG)

## Functions Of CMSeek:
- Basic CMS Detection of over 80 CMS
- Drupal version detection
- Advanced Wordpress Scans
  - Detects Version
  - User Enumeration
  - Plugins Enumeration
  - Theme Enumeration
  - Detects Users (3 Detection Methods)
  - Looks for Version Vulnerabilities and much more!
- Advanced Joomla Scans
  - Version detection
  - Backup files finder
  - Admin page finder
  - Core vulnerability detection
  - Directory listing check
  - Config leak detection
  - Various other checks
- Modular bruteforce system
  - Use pre made bruteforce modules or create your own and integrate with it

## Requirements and Compatibility:
CMSeeK is built using **python3**, you will need python3 to run this tool and is compitable with **unix based systems** as of now. Windows support will be added later. CMSeeK relies on **git** for auto-update so make sure git is installed.

## Installation and Usage:
It is fairly easy to use CMSeeK, just make sure you have python3 and git (just for cloning the repo) installed and use the following commands:

- git clone `https://github.com/Tuhinshubhra/CMSeeK`
- cd CMSeeK
- pip install -r requirements.txt

For guided scanning:

- python3 cmseek.py

Else:

- python3 cmseek.py -u <target_url> [...]

Help menu from the program:

```
USAGE:
       python3 cmseek.py (for a guided scanning) OR
       python3 cmseek.py [OPTIONS] <Target Specification>

SPECIFING TARGET:
      -u URL, --url URL            Target Url
      -l LIST, -list LIST          path of the file containing list of sites
                                   for multi-site scan (comma separated)

USER AGENT:
      -r, --random-agent           Use a random user agent
      --user-agent USER_AGENT      Specify a custom user agent

OUTPUT:
      -v, --verbose                Increase output verbosity

VERSION & UPDATING:
      --update                     Update CMSeeK (Requires git)
      --version                    Show CMSeeK version and exit

HELP & MISCELLANEOUS:
      -h, --help                   Show this help message and exit
      --clear-result               Delete all the scan result

EXAMPLE USAGE:
      python3 cmseek.py -u example.com                           # Scan example.com
      python3 cmseek.py -l /home/user/target.txt                 # Scan the sites specified in target.txt (comma separated)
      python3 cmseek.py -u example.com --user-agent Mozilla 5.0  # Scan example.com using custom user-Agent Mozilla is 5.0 used here
      python3 cmseek.py -u example.com --random-agent            # Scan example.com using a random user-Agent
      python3 cmseek.py -v -u example.com                        # enabling verbose output while scanning example.com
```

## Checking For Update:
You can check for update either from the main menu or use `python3 cmseek.py --update` to check for update and apply auto update.

P.S: Please make sure you have `git` installed, CMSeeK uses git to apply auto update.

## Detection Methods:
CMSeek detects CMS via the following:
- HTTP Headers
- Generator meta tag
- Page source code
- robots.txt

## Supported CMSs:
CMSeeK currently can detect **102** CMSs, you can find the list on [cmss.py](https://github.com/Tuhinshubhra/CMSeeK/blob/master/cmseekdb/cmss.py) file which is present in the `cmseekdb` directory.
All the cmss are stored in the following way:
```
 cmsID = {
   'name':'Name Of CMS',
   'url':'Official URL of the CMS',
   'vd':'Version Detection (0 for no, 1 for yes)',
   'deeps':'Deep Scan (0 for no 1 for yes)'
 }
```

## Scan Result:
All of your scan results are stored in a json file named `cms.json`, you can find the logs inside the `Result\<Target Site>` directory, and as of the bruteforce results they're stored in a txt file under the site's result directory as well.

Here is an example of the json report log:

![Json Log](https://i.imgur.com/5dA9jQg.png)

## Bruteforce Modules:
CMSeek has a modular bruteforce system meaning you can add your custom made bruteforce modules to work with cmseek. A proper documentation for creating modules will be created shortly but in case you already figured out how to (pretty easy once you analyze the pre-made modules) all you need to do is this:

1. Add a comment exactly like this `# <Name Of The CMS> Bruteforce module`. This will help CMSeeK to know the name of the CMS using regex

2. Add another comment `### cmseekbruteforcemodule`, this will help CMSeeK to know it is a module

3. Copy and paste the module in the `brutecms` directory under CMSeeK's directory

4. Open CMSeeK and Rebuild Cache using `U` as the input in the first menu.

5. If everything is done right you'll see something like this (refer to screenshot below) and your module will be listed in bruteforce menu the next time you open CMSeeK.

<p align='center'>
  <img alt="Cache Rebuild Screenshot" width="400px" src="https://i.imgur.com/2Brl7pl.png" />
</p>

## Need More Reasons To Use CMSeeK?
If not anything you can always enjoy exiting CMSeeK *(please don't)*, it will bid you goodbye in a random goodbye message in various languages.

Also you can try reading comments in the code those are pretty random and weird!!!

## Screenshots:

<p align="center">
  <img alt="Main Menu" width="600px" src="https://i.imgur.com/KdRSYzP.png" />
  <br><em>Main Menu</em><br>
  <img alt="Scan Result" width="600px" src="https://i.imgur.com/yiKQoZw.png" />
  <br><em>Scan Result</em><br>
  <img alt="WordPress Scan Result" width="600px" src="https://i.imgur.com/CK4O1Yd.png" />
  <br><em>WordPress Scan Result</em><br>
</p>

## Opening issue:
Please make sure you have the following info attached when opening a new issue:
- Target
- Exact copy of error or screenshot of error
- Your operating system

**Issues without these informations might not be answered!**

## Disclaimer:
**Usage of CMSeeK for testing or exploiting websites without prior mutual consistency can be considered as an illegal activity. It is the final user's responsibility to obey all applicable local, state and federal laws. Authors assume no liability and are not responsible for any misuse or damage caused by this program.**

## License:
CMSeeK is licensed under [GNU General Public License v3.0](https://github.com/Tuhinshubhra/CMSeeK/blob/master/LICENSE)

## Follow Me @r3dhax0r:
[Twitter](https://twitter.com/r3dhax0r)    ||    [Facebook](https://fb.com/r3dhax0r)    ||    [Instagram](https://instagram.com/r3dhax0r)   

## Team:
[Team : Virtually Unvoid Defensive (VUD)](https://twitter.com/virtuallyunvoid)
