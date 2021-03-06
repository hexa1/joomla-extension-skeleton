This is a skeleton development environment for a full Joomla 3 extension. It includes a dev stack, folder structure, and a phing build-script (from JoomExtBuild: https://github.com/jbrice/JoomExtBuild)

Source files are in: `pkg_test` directory.

Drop your joomla installation into: `joomla3-test.com` directory.

Then run Phing commands (see below) to merge files into dev directories, and build a standalone, installable package file.

### Extension types provided:

- **com_test**: Component
- **mod_admin_test**: Administrative Module
- **mod_test**: User Module
- **plg_system_test**: System Plugin
- **plg_system_testlib**: A System shared library
- **tpl_admin_test**: Administrative Template
- **tpl_test**: User Template


Setting up the Development Environment
======================================

Assuming we are on OSX with MAMP

**All**:

0. `brew install graphviz`

**No Composer** (with MAMP):

1. `sudo /Applications/MAMP/bin/php/php5.4.4/bin/pear channel-discover pear.phing.info`
2. `sudo /Applications/MAMP/bin/php/php5.4.4/bin/pear install phing/phing`
3. `sudo ln -s /Applications/MAMP/bin/php/php5.4.4/bin/phing /usr/bin/phing`

**With Composer**:

1. curl -sS https://getcomposer.org/installer | php
2. mv composer.phar /usr/local/bin/composer
3. `composer install`

**or**

1. Get homebrew and macports
2. Set up composer: https://getcomposer.org/doc/00-intro.md#globally-on-osx-via-homebrew-
```bash
$ brew update
$ brew tap homebrew/dupes
$ brew tap homebrew/php
$ brew install composer
$ composer install
```

Workflow
========

1. Edit sources files in `pkg_test`
2. `$ ./phing build_extension` -> will produce a distro in dist folder
3. `$ ./phing update_repo` -> will copy files to joomla installation folder
4. Generate docs: `$ ./phing doc`

Useful Links
============

http://docs.joomla.org/J3.x:Developing_a_MVC_Component/Developing_a_Basic_Component
http://docs.joomla.org/Using_own_library_in_your_extensions
