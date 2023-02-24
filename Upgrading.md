Upgrading
=========

Upgrading to the latest minor or patch version is (almost) as simple as running:

    composer update

If there are `schema` changes in the changelog, you will also need to run the migration scripts to update your database. This is all handled for you.

    vendor/bin/doctrine-migrations migrate

You can safely run this command whether there are migrations or not, so if you are not sure what version you are currently running, it may be best to run it every time you upgrade anything beyond a patch.

Upgrading to 2.0
----------------

Version 2.0 adds an `exists` method to the `StorageInterface` so if you are using the AWS plugin you will need to upgrade to 2.0 on both.

Upgrading to 1.9
----------------

Version 1.9 deprecated `footerText` in the `Theme` entity. This is now set in the admin so you should remove this function call if you have set a custom theme.

Upgrading to 1.14
-----------------

Version 1.14 contains enhancements to the `.htaccess` file that you may want to copy into youe local project.
