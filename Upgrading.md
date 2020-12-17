Upgrading
=========

Upgrading to the latest minor or patch version is (almost) as simple as running:

    composer update

If there are `schema` changes in the changelog, you will also need to run the migration scripts to update your database. This is all handled for you.

    vendor/bin/doctrine-migrations migrate

You can safely run this command whether there are migrations or not, so if you are not sure what version you are currently running, it may be best to run it every time you upgrade anything beyond a patch.
