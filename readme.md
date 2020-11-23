Kuusamo Docs
============

Installation
------------

**Step 1**. Create your project using `composer`. This will install the basic set of dependencies and files.

    composer create-project kuusamo/project

**Step 2**. Configure your environmental variables. This can be done by copying `config-example.php` to `config.php` and adding your own details.

    cp config-example.php config.php
    vim config.php

You can also use environmental variables in Apache, Heroku, or on the command line.

    SetEnv DB_NAME "kuusamo_db"

**Step 3**. Use the Kuusamo CLI to copy the latest static assets into your project.

    vendor/bin/kuusamo assets

**Step 4**. Point your web server at the `public` directory.
