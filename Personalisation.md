Personalisation
===============

Favicon
-------

You can add a favicon by dropping a `favicon.ico` into the `public` directory. Or, if you want to specify a different location, you can use the `FAVICON` config variable to specify the path.

You can do the same thing for `apple-touch-icon.png`; there is no support for custom paths.

Themes
------

Create a custom theme:

    $theme = new Kuusamo\Vle\Entity\Theme\Theme;
    $theme->setLogo('/logo.png', true);
    $theme->setFooterText('Copyright My Organisation. All rights reserved.');
    $theme->setColour('primary', '#A71212');

    Kuusamo\Vle\Service\Templating\TemplatingFactory::setTheme($theme);

Choose something dark for the primary colour as it will be used for links and buttons. Kuusamo automatically generates a lighter version for use elsewhere.
