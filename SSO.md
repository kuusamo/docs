SSO
===

Kuusamo supports single sign-on, allowing users to authenticate against an external service such as your main website.

To enable SSO, use the following config variables:

    define('SSO_LOGIN_URL', 'https://www.mywebsite.com/login');
    define('SSO_LOGOUT_URL', 'https://www.mywebsite.com/logout');
    define('SSO_ACCOUNT_URL', 'https://www.mywebsite.com/account');

You also need to integrate it on your own website as documented below.

SSO does not manage the users within Kuusamo: you need to already have an account in Kuusamo and know the ID. Existing API functionality already exists to do all of this.

Login
-----

When a user tries to access the system, they will be redirected to the URL specified in `SSO_LOGIN_URL`. This login page (the login system on your main website) is then responsible for authenticating the user and logging them into the VLE.

How is this done?

Make a POST request to the Kuusamo API, `/api/sso` with the user's `ID` in the payload. The API will return an SSO token. You can then redirect the user to `/login?sso_token=<TOKEN>` and Kuusamo will do the rest. SSO tokens are valid for 30 seconds.

Logout
------

When a user logs out on the VLE, their session is deleted. If the `SSO_LOGOUT_URL` variable is set, they will then be redirected to the logout page specified.

Account
-------

The `SSO_ACCOUNT_URL` is used for the "manage account" link.
