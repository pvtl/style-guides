Pivotal Agency PHP Style Guide
=====================

We use the [PSR-1 Basic Coding Standard](PSR-1-basic-coding-standard.md) and the [PSR-2 Coding Style Guide](PSR-2-coding-style-guide.md) (including [errata](PSR-2-coding-style-guide-meta.md#errata)).


Naming Conventions
-----------

We use the "camelCase" format for all variable/property and function/method names.

As per PSR-2 (section 4.2 and 4.3) do not use leading underscores to indicate private or protected visibility (eg. $_badPrivateVariable).

    $firstName = 'Joe';

    function printName($firstName)
    {
      echo $firstName;
    }

Commenting
-----------

Comment as much as possible, to help the reader understand what you're doing, as quick as possible. They say it’s better to have too many comments than too few.

Although, keep in mind:

 - It's better to focus on creating readable code, than having to explain every line
 - It’s fair to assume that the reader has a basic understanding of syntax (eg. how a for-loop works); so there’s no need to add a comment such as `// iterate over the customer array`

### Main sections

Use the [DocComment](https://phpdoc.org/docs/latest/guides/docblocks.html) format for function, methods and even main sections of code.  
This helps other developers understand what this function does, what each parameter should do (if necessary) and what the function should return (if necessary).

This format also helps to separate functionality and blocks of code in a file, to make it easier when skimming through the document.

eg.

```
/**
  * Title of this method/function/section
  *
  * This is a more detailed description of this functionality if needed
  *
  * @param string $argument1 This is the description.
  * @return array The list of products
  */
```

### Helper comments

There are other points where you just need to explain what something is doing, within a section of code. For these cases, use the single line comment format, eg.

```php
    // Get this customer's orders
    $orders = $objectManager
        ->create('Magento\Sales\Model\Order')
        ->getCollection()
        ->addFieldToFilter('customer_id', $customerId);
```

Control structure syntax ({} vs : endif)
-----------

PSR doesn't recommend which control structure syntax to use.  
It's best to be consistent with the framework you're using.

As a general rule (for consistency's sake):

 - Always use the standard syntax (curly braces)
 - If you've got a deep nest of curly braces, consider refactoring, or use comments to monitor what each closing brace is for (eg. `} // end if - VIPs`)
 - When mixing HTML and PHP, use the alternative syntax

Examples:

```php
// Deep nesting
foreach ($myArray as $customerId => $customer) {
    if ($customer['admin'] !== 1) {
        if ($customer['vip'] === 1) {
            // Do something
        } // end if - VIPs
    } // end if - standard users
} // end foreach

// Mixing PHP and HTML
<?php if ($customer['vip'] === 1) : ?>
    <span class="vip_customer"></span>
<?php endif; ?>
```


Editor Configuration
-----------
Ensure your editor is setup to use *.editorconfig* files, and use the *.editorconfig* file in the repo root in all new PHP projects.

This will automatically apply settings like indent spacing (4 spaces), line endings (LF), trim trailing whitespace etc, to ensure code written by various developers is consistent.


### PhpStorm

Make sure that the "EditorConfig" plugin is enabled. The plugin is bundled with WebStorm and is activated by default. If the plugin is not activated, enable it on the Plugins page of the Settings / Preferences Dialog as described in [Enabling and Disabling Plugins](https://www.jetbrains.com/help/webstorm/2016.3/enabling-and-disabling-plugins.html).

Next, make sure your [code style is set to PSR-1 / PSR-2](https://www.jetbrains.com/help/phpstorm/2016.3/code-style-php.html).


### Atom
Install these packages:

  * [editorconfig](https://atom.io/packages/editorconfig)
  * [linter](https://atom.io/packages/linter)
  * [linter-phpcs](https://atom.io/packages/linter-phpcs) (requires [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) PEAR package)
  * [php-cs-fixer](https://atom.io/packages/php-cs-fixer) (optional - automatically fixes linting errors)

You may need to restart Atom for these packages to take effect.

### Sublime Text 3
Install these packages:

  * [editorconfig](https://github.com/sindresorhus/editorconfig-sublime)
  * [SublimeLinter](http://www.sublimelinter.com/en/latest/)
  * [SublimeLinter-phpcs](https://github.com/SublimeLinter/SublimeLinter-phpcs) (requires [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) PEAR package)
