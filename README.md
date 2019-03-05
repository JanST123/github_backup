# Simple Github Backup

This is a simple PHP script for backing up all your Github Repositories and issues with comments.

It simple clones all your repositories (even private ) and their branches via git. Changes will be fetched with git pulls instead of full clones.

## Setup
### Prerequisites
You need the following Software installed:
* PHP >= 7.0
* Git client
* Composer (https://getcomposer.org)
* For private repos have your GitHub SSH private key configured in your SSH config

### Install dependencies
Once you have composer installed, install the dependencies by executing `composer install` in this scripts root directory

### Create GitHub API Token
Create an Github API Access Token at *Github -> Settings -> Developer Settings -> Personal access tokens*. Grant all "Repository" permissions to the token.
then create a file **API_TOKEN** in this scripts root directory and paste the token in there.

## Usage
Run the script with `php -f backup.php` - it will fetch all your repositories via GitHub API and then clones them all into a subdirectory called *"backup"*. At the next run it will only pull changes and clones only complete new repositories. So you may run this script periodically via a cronjob or something else.

## Credits
This script is build on the PHP GitHub API client from [KnpLabs](https://github.com/KnpLabs/php-github-api)
