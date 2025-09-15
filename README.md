# Lead Test

This repo hold stuff and code for test project

> All code in `www` directory. All another files and folders used for accelerating development process and deployment

## Table of Contents

- [Lead Test](#lead-test)
  - [Table of Contents](#table-of-contents)
  - [Deployment](#deployment)
    - [Prerequisites](#prerequisites)
    - [Dependencies](#dependencies)
      - [Nginx](#nginx)
      - [PHP](#php)
      - [Move Files](#move-files)
    - [VSCode Extensions](#vscode-extensions)
    - [Secure Backup of .env Files](#secure-backup-of-env-files)
    - [Config SFTP Extention](#config-sftp-extention)

## Deployment

Install the following dependencies on your server (Ubuntu 20.04+)

### Prerequisites

> Work from root user is bad practice

Create user:

```bash
sudo adduser username
```

Add sudo:

```bash
apt install sudo
sudo adduser username sudo
```

> SSH key authentication is skipped for this project

### Dependencies

#### Nginx

Install Nginx:

```bash
sudo apt install nginx
```

Move the Nginx configuration file from nginx folder in repo.

Enable Nginx configuration:

```bash
sudo ln -s /etc/nginx/sites-available/lead-test /etc/nginx/sites-enabled/lead-test
```

#### PHP

Add the PHP repository (for PHP 8.3):

> Try install without adding repository. Maybe PHP 8.3 is already in your distributive

```bash
sudo add-apt-repository ppa:ondrej/php
sudo apt update
```

Install PHP 8.3:

> This setup will install the latest versions of musthave PHP extensions

```bash
sudo apt install php8.3 php8.3-fpm php8.3-mysql php8.3-curl php8.3-gd php8.3-mbstring php8.3-xml php8.3-zip
```

#### Move Files

Move www folder from repo to /var/www/lead-test
Use [sftp extention](/docs/development/sftp.md) to automatically deploy files

### VSCode Extensions

> I recommend to use VSCode for development.
> If you use vscode you will be see recommended extensions (by .vscode/extensions.json).
> Alternatively, you can install extensions manually by links below.

- [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) - for markdown and auto TOC (I use it for this README.md)
- [Gitmoji](https://marketplace.visualstudio.com/items?itemName=seatonjiang.gitmoji-vscode) - for gitmoji commits made easy
- [SFTP](https://marketplace.visualstudio.com/items?itemName=Natizyskunk.sftp) - for easy deploy to server
- [PHP Intelephense](https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client) - advanced PHP language support (see [docs](https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client#quick-start) Quick Start)
- [Todo Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree) - for easy TODO list management (use a bootstrap staged version, not from git, because git version has a lot of TODOs from bootstrap developers)
- [Formatting Toggle](https://marketplace.visualstudio.com/items?itemName=tombonnike.vscode-status-bar-format-toggle) - for easy toggle formatter in VSCode (use when editing Bootstrap files)
- [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) - for easy editorconfig support (see `.editorconfig` file)

### Secure Backup of .env Files

Read this [file](/docs/development/secured_env.md) for more info.

### Config SFTP Extention

Read this [file](/docs/development/sftp.md) for more info.
