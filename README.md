php_standardized_template
=========================

Vim plugin for inserting php code using customizable coding standards

Provided Templates
------------------

| Mapping       | Callable function             | Description                                                    |
|:------------- |:----------------------------- |:-------------------------------------------------------------- |
| `<leader>fi`  | `InsertFile()`                | Blank file, with docblock header if applicable                 |
| `<leader>fu`  | `InsertFunction()`            | Function (outside of class)                                    |
| `<leader>cl`  | `InsertClass()`               | Class file, with docblock header if applicable                 |
| `<leader>sc`  | `InsertSubclass()`            | Class without any file headers                                 |
| `<leader>ec`  | `InsertExtendedClass()`       | Class file using `extends`, with docblock header if applicable |
| `<leader>me`  | `InsertMethod()`              | Method within class                                            |
| `<leader>gs`  | `InsertGetSet()`              | Get and set methods within class                               |
| `<leader>gac` | `InsertGetAddClear()`         | Get, add, and clear methods within class                       |
| `<leader>pgs` | `InsertPropertyGetSet()`      | Property + get and set methods within class                    |
| `<leader>pac` | `InsertPropertyGetAddClear()` | Property + get, add, and clear methods within class            |
| `<leader>wh`  | `InsertWhether()`             | 'Whether' method within class                                  |
| `<leader>pr`  | `InsertProperty()`            | Property within class                                          |
| `<leader>cn`  | `InsertConstant()`            | Constant within class                                          |
| `<leader>tf`  | `InsertTestFile()`            | Test file (PHPUnit)                                            |
| `<leader>tm`  | `InsertTestMethod()`          | Test method (PHPUnit)                                          |

Options
-------

Set the variable `php_template_config` to set options. `php_template_config`
should be a directory with following keys:

| Option Name        | Type       | Description                                                                     |
|:------------------ |:---------- |:------------------------------------------------------------------------------- |
| `category`         | string     | Default text to use for @category tag, if there isn't one in the file already   |
| `package`          | string     | Default text to use for @package tag, if there isn't one in the file already    |
| `subpackage`       | string     | Default text to use for @subpackage tag, if there isn't one in the file already |
| `namespace`        | string     | Namespace to use when creating new class files                                  |
| `copyright`        | string     | Text to use for @copyright tag                                                  |
| `versionnum`       | string     | The current global version, used for the @since tag                             |
| `author`           | string     | Text to use for @author tag                                                     |
| `license`          | string     | Text to use for @license tag                                                    |
| `link`             | string     | Text to use for @link tag                                                       |
| `coding_standards` | dictionary | Coding standards (see below)                                                    |

You can set this variable at the global level (in your vimrc), or at the buffer
level, if you want different settings in one buffer.

Coding Standard Options
-----------------------

The element `coding_standards` should be a dictionary with the following keys:

| Option Name          | Type    | Description                                                                                                                         |
|:-------------------- |:------- |:----------------------------------------------------------------------------------------------------------- |
| `underscore_prefix`  | 'y'/'n' | Whether to make sure that private/protected varibales start with an underscore                              |
| `docblocks`          | 'y'/'n' | Whether to include docblocks at all                                                                         |
| `tabs`               | 'y'/'n' | Whether to use tabs rather than spaces                                                                      |
| `methodauthorline`   | 'y'/'n' | Whether to add an @author tag on methods                                                                    |
| `methodsinceline`    | 'y'/'n' | Whether to add a @since tag on methods                                                                      |
| `zendloadclass`      | 'y'/'n' | Whether to use `Zend_Loader` to load the parent of an extended class                                        |
| `requireclass`       | 'y'/'n' | Whether to use `require_once` to load the parent of an extended class                                       |
| `classbracebelow`    | 'y'/'n' | Whether to put the brace below the declaration on classes                                                   |
| `methodbracebelow`   | 'y'/'n' | Whether to put the brace below the declaration on methods                                                   |
| `filedocblockorder`  | 'y'/'n' | An array of the order of doc tags for files                                                                 |
| `classdocblockorder` | 'y'/'n' | An array of the order of doc tags for classes                                                               |
| `parenspacing`       | 'y'/'n' | Whether to insert spaces within parens                                                                      |
| `doxygenworkaround`  | 'y'/'n' | Doxygen has a bug that makes @param type $varname description fail; use @param $varname description instead |

Notes
-----

This plugin is based on a script called `php_template.vim` that once appeared
in the VIM Scripts listing and follows a similar structure.  I can no longer
find a copy of it, but if you happen to know who the author was, please let me
know.  I would love to be able to credit them.

