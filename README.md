# Pivotal Agency Code Standards

We endorse code standards, to:

- Improve team-wide code quality
- Enhance each product's performance
- Reduce developer decision making fatigue
- In general, code consistency and readability across team members
- Help on-board new team members

We work with various frameworks and libraries, authored by different communities. This comes with different (and sometimes conflicting) code standards. For example, Wordpress has different code standards to Laravel. Instead of enforcing a set of code standards for a language, we support being consistent with each project's framework/library/boilerplate code standards.

---

## Languages

- [HTML](html)
- [CSS](https://github.com/airbnb/css)
- [Javascript](https://github.com/airbnb/javascript)
- [PHP - Laravel](https://laravel.com/docs/master/contributions#coding-style)
- [PHP - Wordpress](https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/)
- [PHP - Default position](php)

---

## Editor Settings

### 1. EditorConfig

1. Install [EditorConfig](http://editorconfig.org/) to your editor, to recognize our [.editorconfig](.editorconfig) file per project
1. Ensure the [.editorconfig](.editorconfig) exists in the root dir of your project

### 2. PHP (PHPCS)

1. [Setup PHPCS on your machine](https://medium.com/@mcnamee/phpcs-code-linting-for-wordpress-c340199364c6#b44c)
1. [Configure your project via a phpcs.xml in your project root](https://medium.com/@mcnamee/phpcs-code-linting-for-wordpress-c340199364c6#40ad)
    - Wordpress Code Standards:
        - [Root directory phpcs.xml](https://bitbucket.org/pvtl/wordpress-theme-boilerplate-v3/src/master/phpcs-root.xml)
        - [Theme directory phpcs.xml](https://bitbucket.org/pvtl/wordpress-theme-boilerplate-v3/src/master/phpcs.xml)
    - [Laravel Code Standards](https://gist.github.com/paulund/8aacc8e8216c21136c182576fc078ec4)
1. [Setup your IDE to give you realtime feedback](https://medium.com/@mcnamee/phpcs-code-linting-for-wordpress-c340199364c6#7b57)

### 3. JS (eslint)

1. [Setup your IDE to give you realtime feedback](https://medium.com/pvtl/linting-for-react-native-bdbb586ff694#df4e)
1. [Configure your project via a .eslintrc.js in your project root](https://medium.com/@mcnamee/phpcs-code-linting-for-wordpress-c340199364c6#40ad)
    - [Wordpress Theme .eslintrc.js](https://bitbucket.org/pvtl/wordpress-theme-boilerplate-v3/src/master/.eslintrc.js)
    - [React .eslintrc.js](https://github.com/mcnamee/react-starter-kit/blob/master/.eslintrc.js)
