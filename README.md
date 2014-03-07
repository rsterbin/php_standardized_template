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


Coding Standard Options
-----------------------

Set the buffer-scope variable `php_template_config` to set coding standards.
`php_template_config` should be a directory with following keys:

| Option Name          | Description                                                                                                                         |
|:-------------------- |:----------------------------------------------------------------------------------------------------------------------------------- |
| `underscore_prefix`  | Whether to make sure that private/protected varibales start with an underscore                                                      |
| `docblocks`          | Whether to include docblocks at all                                                                                                 |
| `tabs`               | Whether to use tabs rather than spaces                                                                                              |
| `methodauthorline`   | Whether to add an @author tag on methods                                                                                            |
| `methodsinceline`    | Whether to add a @since tag on methods                                                                                              |
| `zendloadclass`      | Whether to use `Zend_Loader` to load the parent of an extended class                                                                |
| `requireclass`       | Whether to use `require_once` to load the parent of an extended class                                                               |
| `classbracebelow`    | Whether to put the brace below the declaration on classes                                                                           |
| `methodbracebelow`   | Whether to put the brace below the declaration on methods                                                                           |
| `filedocblockorder`  | An array of the order of doc tags for files                                                                                         |
| `classdocblockorder` | An array of the order of doc tags for classes                                                                                       |
| `parenspacing`       | Whether to insert spaces within parens: n is for method($param) and control($test); y is for method( $param ) and control ( $test ) |
| `doxygenworkaround`  | Doxygen has a bug that makes @param type $varname description fail; use @param $varname description instead                         |

Valid values are `y` and `n`.

Notes
-----

This plugin is based on a script called `php_template.vim` that once appeared
in the VIM Scripts listing and follows a similar structure.  I can no longer
find a copy of it, but if you happen to know who the author was, please let me
know.  I would love to be able to credit them.

