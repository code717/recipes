# Hipchat recipe

## Installing

Install with composer

```bash
composer require deployer/recipes --dev
```

Add to your _deploy.php_

```php
require 'recipe/hipchat.php';
```

## Configuration

- `hipchat_token` – Hipchat V1 auth token
- `hipchat_room_id` – Room ID or name
- `hipchat_message` –  Deploy message, default is `_{{user}}_ deploying `{{branch}}` to *{{target}}*`
- `hipchat_from` – Default to target
- `hipchat_color` – Message color, default is **green**

## Tasks

- `hipchat:notify` – send message to hipchat

## Usage

Since you should only notify Hipchat room of a successfull deployment, the `deploy:hipchat` task should be executed right at the end.

```php
after('deploy', 'deploy:hipchat');
```
