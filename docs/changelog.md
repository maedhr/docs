---
id: changelog
title: Changelog
sidebar_label: Changelog
---


We fix lots of bugs at Dark each week! Here is a brief list of the fixes and updates.

## Week of 2/14/2020

- Added a Welcome to Dark modal for new users

    ![assets/changelog/Feb14/Screen_Shot_2020-02-14_at_4.59.31_PM.png](assets/changelog/Feb14/Screen_Shot_2020-02-14_at_4.59.31_PM.png)

- You can now click on the Command Palette
- Function arguments can now be reordered

![Changelog%20Draft/2020-02-14_13.04.03.gif](assets/changelog/Feb14/2020-02-14_13.04.03.gif)

- You can now delete recursive functions
- We now show you when a value was not executed in this trace

![Changelog%20Draft/Screen_Shot_2020-02-14_at_1.06.20_PM.png](assets/changelog/Feb14/Screen_Shot_2020-02-14_at_1.06.20_PM.png)

- Live values are now shown in unexecuted `match` branches
- Fixed a bunch of redirection bugs after log-in
- Support pasting more JS objects into records
- Fixed the documentation for `Date::parse` (it returns a `Result`)
- Fixed a few bugs around autocomplete appearing too little or too much
- Fixed a carat placement bug in pipes
- Loaded our font (FiraMono) even if you don't have it installed locally
- Fixed some issues causing the editor to freeze:
    - Dragging up to select text
    - Repeated clicking in a variable
- Fixed some issues around copying `match`es
- Added a [Getting Started](getting-started-tutorial.md) tutorial to the documentation

## Week of 2/07/2020

- You can now reset your password (thanks to a switch to Auth0)
- Released a new version of the Dark CLI (0.5). This is a required upgrade to upload static assets.
    - [https://dark-cli.storage.googleapis.com/0.5.0/dark-cli-apple](https://dark-cli.storage.googleapis.com/0.5.0/dark-cli-apple)
    - [https://dark-cli.storage.googleapis.com/0.5.0/dark-cli.exe](https://dark-cli.storage.googleapis.com/0.5.0/dark-cli.exe)
    - [https://dark-cli.storage.googleapis.com/0.5.0/dark-cli-linux](https://dark-cli.storage.googleapis.com/0.5.0/dark-cli-linux)
    - Going forward, the Dark CLI will tell you when your CLI is out of date.
- Added `wrap-in-match` to the command palette

    ![assets/changelog/2020-02-07_15.27.43.gif](assets/changelog/2020-02-07_15.27.43.gif)

- Added new functions:
    - `List::sortByComparator`

    ![assets/changelog/Screen_Shot_2020-02-07_at_12.28.47_PM.png](assets/changelog/Screen_Shot_2020-02-07_at_12.28.47_PM.png)

    - `Bytes::length`

    ![assets/changelog/Screen_Shot_2020-02-07_at_12.33.46_PM.png](assets/changelog/Screen_Shot_2020-02-07_at_12.33.46_PM.png)

- Changing functions now keeps the old function's error rail setting
- Significant improvement in cursor position
- Moved our documentation to a [new, more readable format](https://darklang.github.io/docs/)
- Documented [how to set CORS in Dark](https://darklang.github.io/docs/docs/getting-started.html#additional-informationadvanced-topics)

## Week of 1/31/2020

- You can now see a list of all of your canvases by mousing over your avatar.

    ![assets/changelog/Screen_Shot_2020-01-31_at_12.18.35_PM.png](assets/changelog/Screen_Shot_2020-01-31_at_12.18.35_PM.png)

- Typing when text is highlighted now causes text to be replaced instead of inserted

    ![assets/changelog/2020-01-31_12.23.30.gif](assets/changelog/2020-01-31_12.23.30.gif)

- Many function improvements, including:
    - We now create functions without a default parameter. Apparently that was annoying.
    - Functions now have a menu, and you can delete functions from there if they are unused)
    - Sometimes the Add New Parameter action didn't work - fixed it.

    ![assets/changelog/2020-01-31_12.30.30.gif](assets/changelog/2020-01-31_12.30.30.gif)

- User-created functions now show parameters in blanks

    ![assets/changelog/Screen_Shot_2020-01-31_at_12.33.38_PM.png](assets/changelog/Screen_Shot_2020-01-31_at_12.33.38_PM.png)

- Improved load time of canvases with many traces
- The cursor now stays in the right place when we reflow/reformat code dynamically, in almost every case.
- Prevented you from creating two datastores with identical names
- Added `HTTP::setCookie_v1` - v0 incorrectly URL encoded some fields and is now deprecated
- Fixed an issue where text was sometimes not being properly displayed in the sidebar
- Added a warning when trying to access Dark from a non-desktop or non-Chrome browser

### Documentation

- Created a [Sharing Dark Projects](https://www.notion.so/darklang/Sharing-your-Dark-Projects-26d5b14d6b41457daad6bc44ac849b1a) guide
- Improved the steps at the beginning of the [Guide to Building a Backend for a React SPA in Dark](https://www.notion.so/darklang/A-Guide-to-Building-a-Backend-for-a-React-SPA-in-Dark-29ccf25d75bd48daa32b92e4bd555669)

## Week of 1/24/2020

### Major changes

- Errors/Incompletes now point to the cause of the error

    ![assets/changelog/image3.png](assets/changelog/image3.png)

- We substantially improved keyboard entry:
    - Special characters on international keyboards now appear correctly
    - Infix functions as parameters to other functions work
    - We believe backspace should now always work perfectly
    - We've greatly improved how often the cursor appears in the right place
- Performance and loading improvements for all programs
    - The editor loads program data from the server much faster
    - Workers run with much less overhead (and so higher throughput)
    - CRONs should be running more reliably
    - HTTP requests are much much faster
    - Programs with lots of functions or traces are especially improved
    - Several issues with deleted functions and databases are now resolved
- Copy/paste is way improved
    - you can paste code from Dark into other programs
    - you can paste code into many parts of Dark (varnames, strings, records, etc)
    - most copy-paste issues should be solved

    ![assets/changelog/2020-01-24_15.16.12.gif](assets/changelog/2020-01-24_15.16.12.gif)

### Library changes

- Added `JSON::parse_v1` which uses a Result in case of error (deprecated JSON::parse_v0)
- Added `Float::sum`

    ![assets/changelog/Screen_Shot_2020-01-24_at_3.19.59_PM.png](assets/changelog/Screen_Shot_2020-01-24_at_3.19.59_PM.png)

- More improvements to `DB::query` and friends
    - previews now work for all `DB::query` functions (`DB::queryOne`, `DB::queryOneWithKeys`, `DB::queryWithKeys`)

### Bug fixes

- Fixed up/down arrow on fields
- Single entry autocompletes now work
- Cmd-arrow with shift now maintains selection
- Fixed renaming function parameters
- Fixed deleted text persisting when pressing delete
- Large traces are now properly displayed
- Commands (Alt-x/Option-x) now work more reliably when selecting code
- We now allow you to use arbitrary field names
    - You can now use a field even if you don't have a trace or the field does not exist in that trace
- We've automatically disabled Grammarly, as it was messing with our DOM
- The dark-cli now prints errors on failure

### Documentation

- A [list of sample canvases](https://www.notion.so/darklang/Sample-Canvases-a5fa5479ffbb442d9f180d83e4bf3588) and descriptions has been added

## Week of 1/17/2020

- We added DB::query_v4, which allows you use arbitrary queries on your Dark datastores
    - We also published a [related blog post](https://medium.com/darklang/compiling-dark-to-sql-bb8918d1acdd)!
- You can now remove a `let` with the backspace/delete key

![assets/changelog/image1.gif](assets/changelog/image1.gif)

- Improved [documentation around the Error Rail](https://www.notion.so/darklang/Error-Handling-in-Dark-255f7989a63b4dd49da63cca17ee107e)
- GitHub API! See our [sample canvas](https://darklang.com/a/sample-github) demonstrating how to call the Github API
- Fixed an issue where deleted from the middle of a concatenated string would cause text to the right of the deletion point to be removed.

![assets/changelog/image2.gif](assets/changelog/image2.gif)

- We asked y'all to not make HTTPClient calls to your Dark canvas from REPLs. We've made some infrastructural changes that fix the issue on our end, so you should feel free to do that now. This is useful if you want to create a HTTP trace without leaving Dark. (Note: please don't make HTTPClient calls ***to Dark*** from HTTP handlers)

## Week of 1/10/2020

- Fixed a bunch of issues around entering non ASCII characters, especially from non-US keyboards:
    - accented 'o' and 'a' characters were not being recognized from Swedish keyboard layouts.
    - € or £ weren't working
    - shift + 2 was not being recognized.
- Fixed an issue where pressing delete in a match expression was causing the cursor to be placed incorrectly.
- Stopped errorring when functions are being renamed.
- Fixed an issue where the Omnibox was not clickable.
- Fixed an issue where the minimap was hiding the Dismiss Error button.
- Fixed a short regression where lambda parameters were not shadowing variables of the same name.
- Deprecated the `Date::sub` function and replaced it with `Date::subtract`.
- Changed the behavior of new handler placement - they no longer appear directly on top of one another.
- Changed the behavior of partials - they are now abandoned when clicking away from a handler.
- Added the `copy-request-as-curl` command for `HttpClient::` functions - use Alt-x/Option-x to activate
- Add `Twitter::urlencode` and `Crypto::sha1mac` to support talking to the Twitter API
