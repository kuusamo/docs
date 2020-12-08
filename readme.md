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

**Step 3**. Point your web server at the `public` directory.

**Step 4**. Open it up in your web browser and go to `/setup` to install your admin user.
