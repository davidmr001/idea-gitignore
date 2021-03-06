.ignore v1.7.5
==================

[![Gitter][badge-gitter-img]][badge-gitter] [![Build Status][badge-travis-img]][badge-travis] [![Donate][badge-paypal-img]][badge-paypal] [![Donate][badge-bitcoin-img]][badge-bitcoin]

[![Version](http://phpstorm.espend.de/badge/7495/version)](https://plugins.jetbrains.com/plugin/7495)
[![Downloads](http://phpstorm.espend.de/badge/7495/downloads)](https://plugins.jetbrains.com/plugin/7495)
[![Downloads last month](http://phpstorm.espend.de/badge/7495/last-month)](https://plugins.jetbrains.com/plugin/7495)

Introduction
------------

**.ignore** is a plugin for:
 
- `.gitignore` (GIT),
- `.hgignore` (Mercurial),
- `.npmignore` (NPM),
- `.dockerignore` (Docker)
- `.chefignore` (Chef)
- `.cvsignore` (CVS)
- `.bzrignore` (Bazaar)
- `.boringignore` (Darcs)
- `.mtn-ignore` (Monotone)
- `ignore-glob` (Fossil)
- `.jshintignore` (JSHint)
- `.tfignore` (Team Foundation)
- `.p4ignore` (Perforce)
- `.flooignore` (Floobits)
- `.eslintignore` (ESLint)
- `.cfignore` (Cloud Foundry)
- `.jpmignore` (Jetpack)
- `.stylelintignore` (StyleLint)
- `.stylintignore` (Stylint)

files in your project. It supports following JetBrains IDEs:

- Android Studio
- AppCode
- CLion
- IntelliJ IDEA
- PhpStorm
- PyCharm
- RubyMine
- WebStorm
- DataGrip

*Compiled with Java 1.6*


Features
--------

- Files syntax highlight
- Coloring ignored files in the Project View
- Gitignore templates filtering and selecting in rules generator by name and content
- User custom templates
- Show ignored files by specified Gitignore file (right click on `.gitignore` file)
- Create file in currently selected directory
- Generate Gitignore rules basing on [GitHub's templates collection][github-gitignore]
- Add selected file/directory to Gitignore rules from popup menu
- Suggesting `.gitignore` file creation for new project
- Entries inspection (duplicated, covered, unused, incorrect syntax, relative entries) with fix actions
- Comments and brackets support
- Navigation to entries in Project view
- Renaming entries from ignore file
- Close opened ignored files action
- Custom user templates with import/export features

Installation
------------

- Using IDE built-in plugin system:
  - <kbd>Preferences</kbd> > <kbd>Plugins</kbd> > <kbd>Browse repositories...</kbd> > <kbd>Search for ".ignore"</kbd> > <kbd>Install Plugin</kbd>
- Manually:
  - Download the [latest release][latest-release] and install it manually using <kbd>Preferences</kbd> > <kbd>Plugins</kbd> > <kbd>Install plugin from disk...</kbd>
  
Restart IDE.


Usage
-----

1. Generate new file and templates usage

   To generate new ignore file, just click on <kbd>File</kbd> > <kbd>New</kbd> or use <kbd>Alt</kbd> + <kbd>Insert</kbd> shortcut and select `.ignore file` element.

   ![Generate new file](http://gitignore.hsz.mobi/usage-1.gif)

2. Support for typing new rules, linking rules with matched files

   ![Support for typing new rules](http://gitignore.hsz.mobi/usage-2.gif)

3. Code inspections

   Code inspections covers few cases:

   - duplicated entries (checks if entry is defined more than once)
   - covered entries - entry is covered by more general one
   - unused entries
   - incorrect syntax (regexp rules)
   - relative entries

   ![Code inspections](http://gitignore.hsz.mobi/usage-3.gif)


Changelog
---------

## [v1.7.5](https://github.com/hsz/idea-gitignore/tree/v1.7.5) (2017-02-14)

[Full Changelog](https://github.com/hsz/idea-gitignore/compare/v1.6...v1.7.5)

**Implemented enhancements:**

- *Hide ignored files and directories in the project tree view*
- *Indicate that parent contains extra elements if children are hidden*
- Dialog box that allows to untrack ignored files (performs git rm --cached command)
- Untrack files dialog invoked automatically + from Project view context menu
- Stylint (.stylintignore) support [\#279](https://github.com/hsz/idea-gitignore/issues/279)
- Project Tree View coloring refactoring (performance)

**Fixed bugs:**

- *Fixed colors for tracked and ignored files, additional info label is implemented* [\#296](https://github.com/hsz/idea-gitignore/issues/296) [\#295](https://github.com/hsz/idea-gitignore/issues/295) [\#284](https://github.com/hsz/idea-gitignore/issues/284)
- *IllegalArgumentException on IDEA startup* [\#302](https://github.com/hsz/idea-gitignore/issues/302)
- File of UntrackFilesDialog.createDirectoryNodes must not be null [\#307](https://github.com/hsz/idea-gitignore/issues/307) [\#309](https://github.com/hsz/idea-gitignore/issues/309)
- NoSuchFieldError: GRAYED_SMALL_ATTRIBUTES [\#305](https://github.com/hsz/idea-gitignore/issues/305)
- Ignored entries coloring [\#304](https://github.com/hsz/idea-gitignore/issues/304) [\#301](https://github.com/hsz/idea-gitignore/issues/301)
- ClassNotFoundException: mobi.hsz.idea.gitignore.FilesIndexCacheProjectComponent [\#297](https://github.com/hsz/idea-gitignore/issues/297)
- Assertion failed: Registering post-startup activity that will never be run [\#290](https://github.com/hsz/idea-gitignore/issues/290)
- Component name collision: UpdateComponent [\#289](https://github.com/hsz/idea-gitignore/issues/289)
- Ignore Files Support pane scrollbar issue [\#286](https://github.com/hsz/idea-gitignore/issues/286)
- Outer ignore file panel now has max height rule [\#257](https://github.com/hsz/idea-gitignore/issues/257)
- Properly coloring of subdirectories [\#255](https://github.com/hsz/idea-gitignore/issues/255)
- Setting "Enable ignoring" does not really work [\#298](https://github.com/hsz/idea-gitignore/issues/238)

[Full Changelog History](./CHANGELOG.md)


Contribution
------------

Check [`CONTRIBUTING.md`](./CONTRIBUTING.md) file.

### Compiling the source code

Since the project has been migrated to the Gradle and [Gradle IntelliJ plugin][gradle-intellij-plugin],
the build process is much simpler. The only thing to build the plugin is to run:

    gradle build
    
All required dependencies like Grammar-Kit, JFlex are downloaded in the background and triggered properly
during the build process. You can also test the plugin easily with running:

    gradle runIdea
    
All of the gradle tasks can be connected to the IntelliJ debugger, so the development process is very easy.


Developed By
------------

[**@hsz** Jakub Chrzanowski][hsz]


**Contributors**

- [**@zolotov** Alexander Zolotov](https://github.com/zolotov)
- [**@76200** Bartłomiej Czyż](https://github.com/76200)
- [**@bedla** Ivo Šmíd](https://github.com/bedla)
- [**@danpfe**](https://github.com/danpfe)
- [**@maximilianonajle** Maximiliano Najle](https://github.com/maximilianonajle)


Tools
-----

I'm using Yourkit to locate and fix performance issues of BashSupport. YourKit, LLC kindly provided a
free open-source license of the [YourKit Java Profiler](https://www.yourkit.com/java/profiler/).

![YourKit Java Profiler Logo](https://www.yourkit.com/images/yklogo.png "YourKit Java Profiler Logo")


License
-------

Copyright (c) 2017 hsz Jakub Chrzanowski. See the [LICENSE](./LICENSE) file for license rights and limitations (MIT).

    
[github-gitignore]:       https://github.com/github/gitignore
[gradle-intellij-plugin]: https://github.com/JetBrains/gradle-intellij-plugin
[hsz]:                    http://hsz.mobi
[latest-release]:         https://github.com/hsz/idea-gitignore/releases/latest


[badge-gitter-img]:       https://badges.gitter.im/hsz/idea-gitignore.svg
[badge-gitter]:           https://gitter.im/hsz/idea-gitignore
[badge-travis-img]:       https://travis-ci.org/hsz/idea-gitignore.svg
[badge-travis]:           https://travis-ci.org/hsz/idea-gitignore
[badge-coveralls-img]:    https://coveralls.io/repos/github/hsz/idea-gitignore/badge.svg?branch=master
[badge-coveralls]:        https://coveralls.io/github/hsz/idea-gitignore?branch=master
[badge-paypal-img]:       https://img.shields.io/badge/donate-paypal-yellow.svg
[badge-paypal]:           https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=SJAU4XWQ584QL
[badge-bitcoin-img]:      https://img.shields.io/badge/donate-bitcoin-yellow.svg
[badge-bitcoin]:          https://blockchain.info/address/1BUbqKrUBmGGSnMybzGCsJyAWJbh4CcwE1
