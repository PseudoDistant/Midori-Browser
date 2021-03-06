# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [9.0] - 2019-07-27
- Use OpenGraph images for Speed Dial shortcuts
- Better support for Javascript popups
- (Re)store pinned tabs in the session
- Re-introduce the Trust (certificate) button
- Avoid key input recursion causing high CPU
- Close Tab/ Other context menu items
- Paste and Proceed option in the urlbar
- Better urlbar suggestion escaping
- Web extensions: Support for a sidebar action (experimental)
- Merge app and page menu into one
- Better focus handling of re-opened and background tabs
- Show volume icon for tabs playing music

## [8.0] - 2019-02-28
- Javascript changes confirmation and prompts use dialogs again
- Bug fixes in Urlbar completion and focus handling as well as Adblock filtering
- Headerbar enabled by default only under Budgie, GNOME and Patreon
- Re-introduced support for `--inactivity-reset`, `-e Fullscreen` and `-e ZoomIn`
- Initial support for cross-browser web extensions (not exposed in the GUI yet)
- Builds deps: Glib lowered to 2.46.2, Json-Glib and libarchive are now required
- Link to the bug tracker from the About dialog
- Correct handling of external URIs such as apt:
- Fixed installation path for appdata and plugins
- Support for building Midori on Android with Gradle
- Better internal distinction of errors from visiting pages
- Zoom indicators in the page menu and statusbar features extension

## [7] - 2018-11-30
- Fixed YouTube rendering issue due to custom user agent
- Fixed invisible cursor in text fields
- Restored behavior of " " and "." in urlbar completion
- Download/ web notifications for background window/ tab
- Highlight in toolbar for finished downloads
- Re-introduced proxy server UX
- Multiple processes for indivdual tabs
- Adaptive toolbar layout for smaller screens

## [6] - 2018-10-31
- Revamped Vala-only core based on GTK+3 and WebKit2
- App based on Gtk.Application, supporting global/ window app menu
- Tabs on top with a custom stack switcher and Gtk.Stack
- Url completion with GLib.ListModel and Gtk.ListBox
- Peas-based extensions, also available in Private Browsing
- New fullscreen mode with auto-revealing toolbar

## v0.5.11
- Add fake theme for built-in icons
- Don't truncate long speed dial titles if there's room to display them
- Fix warnings for `-Wformat-security`
- Ensure vala knows the prototypes of functions it calls, fixing pointer truncation in tests
- Add unit test to check appmenu/menubar visibility
- Fix last known GTK2 entry placeholder text bugs
- Make sure that only one of appmenu and menubar are visible *initially* as well as when changed
- Move adblock icons to hicolor
- Limit bookmarks panel callbacks to the lifetime of the panel to fix a crash
- Fix fallout (broken bookmarks and history panel search) from tweaks to GTK2 entry placeholder
- fix property binding to ensure that exactly one of appmenu button and menubar is always visible
- Skip open-with codepath with abp links, they are internal
- Use `find_file` to locate execinfo.h
- Fix middle/ctrl/normal clicking bookmarks (not folders) in the bookmarkbar.
- Add copright header to `sanitize_bar.sh`
- Adblock fixup: Escape . in filter with \
- Don't shadow variable uri in `midori_browser_save_uri`
- Switch Adblock icons to 24px color
- Always include app menu in toolbar
- Fix various mis[sing ]annotations and style issues in GIR
- Compile typelib from gir
- Fix assert when resetting webapp state after inactivity reset
- clean up handling of double-valued db column in Tabby
- Add a comment to explain MidoriBrowser popup callback
- fix warnings printed when right-clicking resize grip between location and search entries
- Win32: Use Dr. MinGW if present to preserve crash info
- Fix menubar warning caused by direct cast instead of `as`
- Helper script for setting up bzr with some usefull plugins and settings
- Stop using `Gtk.Entry.max_width_chars`
- avoid deprecated SoupServer API with libsoup 2.48
- Use unowned in foreach loops in Midori.Window
- Use unowned in foreach loops in Midori.Completion
- Use unowned with Adblock.Subscription and Element in foreach loops
- Use unowned strings in foreach loops
- Enable openWith in app mode and make it work with view-new
- Implement Midori.Window class with toolbar/ headerbar
- Drop support for libsoup-gnome-2.4 < 2.37.1
- Make search icons for engines work correctly
- Move to WebKit2 4.0 which broke ABI
- Port to zeitgeist-2.0
- win32: Bump shipped GrayBird theme version to fix some rendering issues
- avoid deprecated GtkDialog API with GTK+2 >= 2.22
- Title case for "Export Certificate" button
- fix incorrect type of MAX(sorting) in Tabby

## v0.5.10
- use exit instead of return in license script
- Fix `HAVE_GCR` guards after GtkPopover port
- Remove example app and .desktop before creating it in the unit test
- Fix cache dir path in Adblock and always mkdir tmp
- Port location action from Granite.PopOver to Gtk.Popover
- Match https site when user-style is using domain syntax
- Always disable developer tools on Win32
- Reimplement Midori.URI.unescape and add various tests
- Make the inspector resizable with GTK3 by packing into a GtkScrolledWindow
- Don't build tabs2one in release builds
- Don't assume GNotification works on Win32
- update copyright date in About dialog
- Don't entity-escape history and bookmark results in location completion
- Only set tabs' error state if errors come from the main frame
- Implement Paste and Proceed as an action
- No Gcr on Win for the moment
- Yet another Speed Dial CSS update:
- Port bookmark popover from Granite to Gtk.Popover
- Make application choosers resizable with a sane default size
- Use GNotification >= 2.40 and use Midori.App API in webmedia
- Rework mouse button handling in KatzeArrayAction
- Don't bind :day in HistoryDatabase.query
- Make GCR mandatory for all builds
- Update coub support in mediaHerald
- history-list: Fix gtk+3 build caused by dropping `using Gtk;`
- Drop all remaining usages of `using *;`
- Don't open search engines menu when clearing search action
- Only remove apps in the sidepanel when left-clicking the delete icon
- Improve robustness of GTK3-compatibility placeholder text fallback
- Clean up vapi dependency
- `tls_flags` from `webkit_web_view_get_tls_info` need to be 0
- Don't add failed pages to history
- Throw error for wrong paramter in Statement.bind
- Replace NoJS "allow all pages" setting with "allow local pages"
- Avoid bugs due to race condition in addons delete dialog
- Calculate transfer progress at regular intervals to fix 0B/s bug and recalcitrant progess bars
- Fix warnings occurring with `EXTRA_WARNINGS`
- Escape parentheses in `adblock_fixup_regexp()`
- Use `File.query_exist()` on win32 when checking for db to attach
- Handle `NEW_WINDOW_ACTION` explicitly to make `_blank` targets work
- Fix undefined behavior uint in mouse gestures
- fix JavaScript keyup event by calling inherited `key-release-event` handler in MidoriBrowser
- Inline renaming of speed dials
- Handle `current_size` and `last_size` of Download being equal
- Add proper copyright headers to `element_hider` and autosuggestcontrol
- Add `X-GNOME-UsesNotifications` to indicate the use of notifications
- Fix typo in Bookmarks menu UI definition

## v0.5.9
- Remove dead code from browser and preferences
- Build-fix: Make PanedAction's Child.widget public
- fixes tab history undo
- Set a placeholder text on the URL entry
- Add "Add Bookmark" to menu
- Show search menu upon left icon click in location bar
- Fix crash when saving with associated resources
- Fix webkit2 downloads based on older branch
- don't hide window decorations for Midori-Granite
- Connect bookmarks-db singleton correctly to fix menus
- Fix some symbol names and transfer annotations in doc comments
- Use correct signature for window-state-event handler
- Do not overescape page titles in view completion
- Make adblock skip non-standard last update metadata strings
- Drop deprecated Granite LightWindow used for the Clear Private Data dialog
- Keep storing the last web media tab played.
- Allocate CookiePermissionManagerModalInfobar correctly
- Make middle clicking reload button duplicate the current tab, similar to other browsers
- Use network-changed of GNetworkMonitor to reload all tabs if network becomes available
- Show different messages based on network connectivity.
- Fix crash when activating the edit menu
- Fix "open all in tabs" for bookmarks
- Fix a few simple leaks
- Don't focus the locationaction when leaving blank pages
- Fix leaks of two references to the MidoriApp in Tabby
- Compile with valac 0.16 again
- Never display about:new in the urlbar
- fix crash right-clicking forms on local pages
- Share 'youtube, vimeo, dailymotion' that you are playing in Midori using org.midori.mediaHerald
- Give the SoupURI a path when checking cookie relevance
- Resolve ellipsis and title stripping in completion
- Add `www.` and `.com/.country_domain` and proceed with `^Enter/Shift+Enter`
- Clean up browser tab/ uri/ title notify
- Drop pseudo Granite distinction in completion layout
- Fix visibility of SpeedDial, Toolbar, Bookmarkbar context menu items
- Distinguish between desc file missing and other parsing issues
- Use dependencies to clear test folders before execution
- win32: Drop dropbox usage from win release script, rename resulting output files

## v0.5.8
- Use png icon instead of svg in `set_status`
- We must not pass a Cancellable to `FaviconDatabase.get_favicon_pixbuf`
- Retain spelling suggestion menu items from WebKit
- Properly guard usage of gtk3 `get_style_context`
- Mimic the look of Granite.DynamicNotebook when compiled with --enable-granite.
- Fix X11 lib underlink in midori-core
- Fix bookmarkbar bookmark click not opening links
- Use sanitized app URI as `wm_classname/ StartupWMClass`
- Make trunk build with WebKit2 again
- Fix for incorrect tstamp for background tabs
- Don't declare sorting doubles are nullable and print values when database tracing is enabled
- Correctly apply saved entry state and treat urlbar as a regular editable item
- Add missing conditional includes for granite flavoured build
- Open URIs dragged on tab label or new tab button
- Small adblock bugfixes
- Work around GTK3's hard-coded minimum stackswitcher button width
- Fix building with mingw packages from fedora 18
- Set page title as basis for print filename
- Rename notes inline
- Use `EXTRA_WARNINGS` option when building for windows
- Drop forgotten clutter init and obsolete header declarations
- Rework history-step handling and make it work again
- Port Tabby to DatabaseStatement API
- Replace bookmark stracing with generic profiling in Midori.Database
- Port autocompleter test to async job
- Finishing touches for Adblock
- Add filters and defaults
- Implement and use ContextAction.escaped
- printf URI in `show_message_dialog` for download error
- Improve docs and GIR annotations for KatzeItem, KatzeArray, and MidoriWebSettings
- Drop redundant TabNew from compact menu and put button in Tab Panel
- Fix loading file:// pages
- Implement Send Page Link by Email
- Use GtkStackSwitcher with GTK+ >= 3.10
- Implements context popup menu on menu entries of bookmark bar and bookmark menu.
- Fix building with newer mingw versions
- Display locationbar suggestions in the correct order
- Don't bother adblocking internal pages and favicons
- Don't use trailing comma on last list element in Adblock tests
- Rewrite Adblock more modularly, add Whitelist support
- Add support of DragonFlyBSD
- Change tooltips of Reload and ReloadStop actions while shift modifier is pressed
- Implement Midori.Database.attach method
- Allow :memory: as folder to make schema detection work
- More robust app/ profile creation
- Add helper callbacks to modify bookmark's tree store with unneded access to bookmarks db
- Implement more flexible fallback behavior for Cookie Permissions

## v0.5.7
- Modify actions and internal items in browser without changing settings
- Delay tab loading after Midori crashed
- Uncomment failing assertions about `view_source` in tab test
- Fallback to about:home if startup is anything but blank
- Don't try to create formhistory database if `config_dir` is NULL
- Handle url arguments for blank sessions
- Execute commands given at start time
- Introduce high-level prepare/ DatabaseStatement API
- Drop unused GraniteClutter-based animation support
- Drop uncommented contractor support
- Drop deprecated StaticNotebook used in KatzePreferences
- Introduce notebook class converging separate implementations
- Work around symbol relocation issue old version of gcc present on Ubuntu LTS
- NULL-check treeview in `midori_search_action_get_editor`
- Adjust CMakeList .ico check to not skip nojs icons
- Enable sidepanel in private mode
- Move Preferences menu entry above About
- Set minimum value of 0 on spin button for maximum cache size
- Give NextForward its own label for toolbar editor
- Correctly disable favicon database in app and private mode
- Change preferences to refer to proxy address as a "URI" (not "hostname")
- Add close tabs to right feature
- Allow printing without confirmation dialog on kiosk setups

## v0.5.6
- instead of creating devpet status icon on extension load, create it only to show new messages
- Open speed dial or homepage according to preference
- handle tab duplication
- Add copyright note to appdata file
- Tweak searching for resources when running from build folder
- Swap NULL-check with main frame check
- Use correct signal when clearing the trash
- Hide WEbGL preference if it is unavailable
- Remove stored popup sessions from the database
- Check all browsers for opened sessions and whether they're popups
- removed unused preference dialog and related code
- Fix check for found valac and mention VALAC variable
- Fix autoscrolling if page contains a frame with our custom error page
- Don't use context-menu signal in WebKitGTK+ < 1.10.0
- Fix building on Ubuntu 12.04
- Reset item ids when re-importing bookmarks
- Check path being NULL in export before trying to inspect it
- restore the last closed sessions if no session is opened
- Cast WebKitDOMHtmlElement for getting source content
- Use font-set signal and font family for GTK+ 3.2 font chooser
- add function to view dom source
- remove unused variable
- Resolve compiler warnings in current trunk
- Update win32-release script for cmake, move unused docs/scripts to old folder
- Try to handle previous runs of cmake in configure wrapper
- Correct view source assertions in tab unit test
- Build fix: found undeclared in `midori_bookmarks_db_remove_item_recursive`
- Cache bookmark items to avoid their recreation on database reads
- allow "view source" on about pages
- Enable old target policy on cmake < 2.8.8
- Re-arrange data file installing to be more explicit
- option to modify the number of tabs which will be restored in each idle callback
- Implement MidoriBookmarksDatabase class by inheritence from MidoriDatabase
- Ensure tab spinners update as often as the menubar spinner to avoid desync
- Use tabby sorting increment when importing session.xbel tabs
- Only install config files to /etc if prefix equals /usr
- handle urls as argument when starting midori
- Make tabby compile with Webkit2
- Drop waf build system and provide cmake-based "configure" script
- `midori_panel_action_activate_cb` forgot to update the action group
- Fixes bug where certificate Security overlay failed to close
- handle tab movement
- add tab sorting
- Untangle implicit GTK+3 for Granite and WebKit2
- Allow running test under debug tools with cmake
- Install config files to /etc when install prefix is /usr
- Add missing `PO_FILES` argument to `GETTEXT_PROCESS_PO_FILES`
- Add `USE_APIDOCS` to build API docs with CMake
- Rasterize SVG to PNG with rsvg-convert
- fix bookmarks test regression after fix-1179200-4
- Add CMakeLists.txt for config directory
- Install mo files in locale dir
- don't change uri/title if the tab isn't loaded
- use a separate signal to store the tab title
- Check if execinfo.h header exists on BSD
- fix endless loop in Midori.Database.init
- Use destructive-action style class in ClearPrivateData
- Initialize `priv->element` to avoid crash when freeing
- Introduces KatzeArray::update-item to handle metadata changes
- Refactor excuting schema from file into a function
- Use stock as string in liststore
- Drop needless (and wrong) `HAVE_LIBNOTIFY` in preferences
- Flip horizontal position of the overlay when hit by the mouse
- Add `Midori.URI.get_base_domain` and use it in NoJS
- Introduce Midori.Database and use for history and tabby
- ctrl+shift+w should trigger a delete-event
- Implement dialog windows opened via javascript
- Make `get_res_filename` work with different hierarchies
- fix check for new database
- Speed up session import
- Import tab title from old sessions
- Separate CFLAGS for C and add missing HAVE_
- Install top-level text files and FAQ html/ css to doc dir
- Provide and install .appdata.xml file for app stores
- Move bookmarks db handling to midori-bookmarks-db
- Add XSS to OPTS_LIBRARIES
- Update condition for `UBUNTU_MENUPROXY` to work on Saucy
- Introduce tabby, the new session manager
- Fix typo in `katze_item_set_meta_integer` call
- Allow bookmark bar update on additions resulting from imports
- Re-work `midori_array_query_recursive` to not include folder items twice
- Fix syntax of icon sizes passed to foreach
- Add bzr revision number to version if available
- Unify nojs and cookie policy dialogs, make policy changeable within the list
- Drop all `G_ENABLE_DEBUG` guards
- Add -g to CFLAGS to enable debugging symbols
- Adjust cmake build for Win32
- Implement CMake build setup
- Port MidoriApp from Unique/ sockets to GApplication
- New signal about-content to provide content for about uris
- Check if browser is NULL in `midori_view_get_tab_menu` to prevent a crash. Fixes bug #1215652.
- Ensure proxy setting widgets callbacks don't outlive the widgets themselves
- Fix webkit2 build error
- Show the bookmarks import location combobox.
- Rename internal completion URLs to avoid confusion

## v0.5.5
- Fix name and text fields inversion in XBEL folder import
- Correct packing of cookie and nojs permission dialog.
- Don't set tab title/special when a non-main frame displays an error
- Revise "cookies" debug output, merge expiry check and disallow revival of old cookies
- Drop now unused cgit module.xml file
- Use SoupProxyResolverGnome unconditionally and disable prefetching if proxy is active
- win32: Hide gui for profiles in webapp manager, as they are currently broken on Windows
- win32: support additional mouse buttons for going back/forward in history
- Enrich app error messages with filenames
- Fix segfault if url contains " %00"
- Replace 'Run as app' in bookmark dialog with 'Create launcher'
- Split config files and install from folders recursively
- Implement GTK+ theme switching via Preferences (Win32)
- Enable `set_disk_cache_directory` with WebKit2
- Introduce Midori.ContextAction and refactor page menu from scratch
- Define large dialog icon size relative to dialog icon size
- Extension Devpet which shows error messages and backtraces in systray
- WebKit2 cookie support
- Check the hit test result for editable to see if , should search
- Use SoupCookieJarSqlite and drop KatzeHttpCookies(Sqlite)
- Show folder tree when editing bookmarks
- Handle double value in `_midori_browser_activate_action`
- Add privacy preferences in web app mode
- Escape parentheses in `adblock_fixup_regexp`
- Introduce object oriented API for access to History Database
- Allow rss feeds with version 0.92
- Rename History completion to Bookmarks and History
- Don't show rss feed icon on twitter, underlying API was retired
- Read apps/ profiles from folder, leave launchers separate
- Fill in bookmark folder attributes in bookmarkbar populate

## v0.5.4
- Refactor history step and allow multiple title updates
- Call `midori_browser_connect_tab` with correct type
- Don't add HistoryCompletion if there's no history
- Restore reload button icon in error pages
- Don't insert folders into the log
- If an url is specified the fallback url should not be loaded
- Fixed crashes when closing a loading tab- granite's tab moving
- Test if plugins are redundant instead of skipping them all
- Avoid selecting bookmark uris that begin by 'javascript:' for completion
- Set `FOREIGN_KEYS` pragma on db initialization
- Implement a default zoom level preference
- Fix tautological use of `G_MAXINT` with enum
- Take current selection into account for bookmark folders when adding/editing bookmark
- Improve error page visuals, show suggestions on network errors
- Bump vala to 0.16.0
- Downgrade glib requirement to 2.32.3 to re-enable building under Ubuntu 12.04 (LTS)
- Bump glib2 version to 2.32.4
- Improve and unify thumbnail generation
- Omit speed dial and blank pages from view completion
- Makes the elements of the speed dial non-selectable
- Use NULL-safe comparison in `katze_item_icon_loaded_cb`
- Drop non-DOM style sheet injection code path
- Clean small leftovers from GTK and WebKit version bumps
- Bump GTK+ requirement to 2.24 and drop support for earlier versions
- Check for app mode to set browser icon instead of readonly
- Escape square brackets in `adblock_fixup_regexp`
- Fix showing (sub)folders in bookmarkbar
- Bump WebKit requirement to 1.8.3 and drop support for earlier versions
- Set menu on dynamic notebook tab
- Do not run toolbar editor's GtkDialog in its own main loop by prevent calling `gtk_dialog_run()`. Instead just set the GtkDialog modal and show it.
- Remove unnecesary harmful code from `tab_switched_cb`
- Fix segfault when deleteing tabs with history list
- Specify int64 id item as a string in bookmark remove/update queries
- Distinguish between box and event box in the tab label when colouring tabs
- Show visual feedback when hovering over items in bookmark panel
- Replace INSTALL/ HACKING with exported Contribute wiki page
- Delete tabs from history list with Del
- Check brightness of backgroung color when deciding foreground color of given tab
- Clean launcher filenames, double-click to open and delete button
- Avoid declaring browser twice within the same function
- Add ./waf --update-pot
- Fix memory leak introduced in r6184
- Use old function name `g_dbus_generate_guid` for old valac
- Move Import and Export into menu Bookmarks
- Collect multiple download notifications within a minute
- Fix segfault when right clicking on a web view.
- Make libnotify mandatory except on Windows
- Remove the rather unnecessary ./waf --run feature
- Send a notification after creating a launcher
- Ambiguous 'Open as App' context menu item was removed
- Apply label color to label rather than event box
- Store data of app mode based on URL in ~/.local/share/midori/apps
- Split colorful tabs code into helper functions and add unit tests
- Fix History List memory leak  when closing Midori window.
- Replace .gitignore with a .bzrignore
- Always define `GCR_VERSION` in GTK+2 build
- Fix bookmarks dialog rename regression introduced in r6167.
- Drop check for gcr-3-gtk2 which isn't being maintained.
- Scrap unneeded background variables in location renderer callbacks
- Title case and proper packing in bookmark dialog
- Delete PO files Launchpad spewed into root directory when it couldn't find `po/*.pot` file.
- Issue a warning when trying to use `MIDORI_DEBUG` while running
- Update dates to 2013 to fix bug #1167075.

## v0.5.2
- Re-release with a proper version number and changelog

## v0.5.1
- Fix mouse gesture regression breaking context menu
- Fix --run command line switch by `midori_paths_init`
- Fix bug in size calculation for the history list popup
- Handle diagnostic dialog argument in running instance
- Fix feed panel default value crash
- Ensure existence of the applications directory
- Fix download tooltip crash and extend test case
- Integrate user interaction exploit demo in about:
- Don't convey loading or progress on special pages
- Address missing NULL checks and dead code found by clang
- No security window for blank pages, but a search icon
- Introduce UI for created apps/ launchers: Web App Manager
- Add custom-title setting to override browser title
- Add a Gtk.Entry to --plain mode for entering URLs
- Deprecate `middle_click_opens_selection` in favour of `gtk-enable-primary-paste`

### Webkit2
- Require 1.11.91 aka 2.0.0 for WebKit2
- Delayed load, clear favicons, clear HTTP cache, tab favicons
- Navigation policy, mouse buttons, security details
- basic cookies, download dialog, res://, stock://, print
- Zoom, default-charset, view-source, spell-check, prefetch
- Back/ forward, enable-java, plugin listing, web inspector

## v0.5.0
- Store --execute arguments in string array
- Prevent overlay frame from being caught by `show_all`
- Unconditionally show Toolbar Style preference
- Duplicate current URI when reloading Midori.View
- Update tabs being closable on setting change in Granite
- Check `default_search` before setting SearchAction default
- Populate application chooser button in idle
- Bail out of completion resizing if cell height is 0
- Pass proxy to bookmark dialog when editing via menu
- Tweak bookmark dialog, button to buttons, toggles side by side
- Move 'Flash windows' option into History List
- Use light window for Clear Private Data with Granite
- Use GtkFontButton with filter func with GTK+ 3.2
- Implement 'Run in debugger' button in diagnostic dialog
- Add Win32 work-around to History List for modifiers
- Make toolbar drag/ drop work in GTK+3
- Check if active form element is input before getting search text
- Implement direction-based mouse gesture configuration
- Implement mouse movement, load-failed, crashed, search in WebKit2
- Add 'Show last crash log' button to diagnostic dialog
- Make invalid actions fail; exit on error in new process only
- Accept setting=value and extension=true/ false in --execute
- Merged cookie permissions as of 2013-03-08
- Gray out webGL preference if context is unavailable
- Use browser API to Close Other in view menu item
- Fix periods to ellipsis in Custom/ Customize Shortcuts
- Support Colorful Tabs in History List
- Add `Midori.Tab.fg/ bg_color` and `Midori.View.set_colors`
- Fix word-wrap, #decription and #message in about.css
- Set view scroll policy to Never to avoid flickering
- Use `XDG_RUNTIME_DIR` for temporary files
- Build Vala and C parts of core separately
- Don't provide default value for enable-scripts
- Respect Open new pages: window for Web Search and Open Image
- enable-javascript in WebKit1/ 2, macro for (Web)Settings
- Fix MIDORI_*_VERSION to be integers
- Fix .desktop file validation unit test and fix errors
- 'New tab behavior' preference: about:dial/ new/ search/ home alias URLs
- Use stripped down XBEL variant for session and trash
- Allow any proxies supported by libproxy; list supported types in preferences

## v0.4.9
- Let non-Granite security window behave like a window
- Disable Contractor support in Granite for now
- Use `cache_dir_for_reading` in about:paths
- Strip LRE to prevent it from begin saved to disk
- Enable stripping 'referer' by default
- Fix crash on closing Adlock preferences dialog
- Bail on unset title in completion, fixing strchr urlbar crash
- Manage cookies accept policy per domain - not installed by default
- Don't store/ load stock:// icons for special pages
- Drop KatzeScrolled in favour of GTK+ 3.4 touchscreen support
- Write XBEL safely to prevent loss on eg. full disk
- Omit nspluginwrapper Netscape plugins from extensions
- Add --debug/ -g switch to run Midori in gdb
- List versions from about:version in --version
- Work in progress --enable-webkit2 option enabling WebKit2/ GTK+3
- Rename menu _Window to _Tabs
- Update Easylist subscription URL for Adblock
- Stop redundant tab numbering when adding
- Allow feed panel webview widget to shrink.
- Don't search for place holder text on cookie list rebuild
- Add 'Google Translate (gt)' as a search engine
- Default external Download Manager to "fetch" on FreeBSD
- Drop GCC-version specific -Wno-unused-but-set-variable
- Change X-Ayatana-Desktop-Shortcuts to Actions

## v0.4.8
- Fix un-delaying of tabs
- Support downloads with FlashGet on Win32
- Fix compilation with GLib 2.30
- Fix error handling in extensions
- Retain selection in urlbar when switching tabs
- Fix missing right-click menu on NextForward button
- Hide error page button if buttons have no images
- Rework URL completion: suggest open tabs
- Always highlight matches in inline search
- Pantheon: Only show private launcher in search
- Granite: Fix notebook, require 0.2, drop `_about_dialog_new`
- Don't include http(s), file or www. in page title
- Autodetect Twitter RSS feeds
- Adblock: Improve date parsing
- Unit test rework: backtraces, regardless of debugging, wine
- More accurate version numbers in about:version
- Drop obsolete --log-file command line switch
- Emit inspector attach-window with correct signature
- Fix Netscape plugins opening download dialogs
- Rework path handling and setup in different modes (fix segfaults)
- Manage Netscape plugins are individual extensions
- Address `gtk_icon_set_render_icon_pixbuf` assertions
- Fix renaming in speed dial with spaces in title
- Render completion title/ URL side by side with Granite
- Transparently use Favicon-/ IconDatabase/ file store per WebKit
- Add TabMoveFirst/ Last hotkeys (without defaults)
- Drop Hildon support
- Show URI in 'not responding' dialog
- Query search engine icons when loading, rather than stupid guesses

## v0.4.7
- Unify download behavior: link fingerprints, space check, clearing, tooltips
- GIO-based check for enough space and permissions, GIO-based themed icons
- Show opener/ tab domain in download dialog
  - http://lcamtuf.coredump.cx/fldl/ http://lcamtuf.coredump.cx/switch/
- Extension to download with a specific command line
- Size in download dialog and fallback filename heuristic
- Windows
  - GTK+3, Faenza icons, gdb helper, Netscape plugins
  - ship CA bundle, fix View source, --portable/ -P
- Granite (Beta)
  - about dialog, static notebook, no "New Tab" in toolbar, Print ??? Share
- Support building with Wayland-enabled GTK+3
- Theming: content view, secondary toolbar class, drop old icon names, bigger error icon
- Introduce --plain mode equivalent to GtkLauncher, lazy URLs for --snapshot/ -s
- Log bookmarks, history and downloads to zeitgeist
- Show security details and export certificates with GCR, error out instead of colored urlbar
- Only allow data: URLs in urlbar for images
- Recognize and cache HSTS, system-wide /etc/xdg/midori/hsts
- Strip HTTP Host to outsmart some filter proxies
- Completion
  - Fix `PageUp/Down`, `Shift+Tab` and wrap: This is consistent with GTK+ (excluding Tab) and Firefox
- Change Focus Current Tab to `^Alt+Home`
- Fix Shift+Space for scrolling upwards
- `^Alt+R`: Readable mode
- Handle access key in link hints
- Drop speed dial keyboard access in favour of "." link hints
- No Open, Bookmark bar, Customize toolbar, Inspect page in app menu; split panel menu
- Use ellipsises instead of period thresomes
- Hinted text in bookmarks, history and cookie manager
- Ellipsize panels (except for Transfers)
- Add icon to bookmark dialog and remove labels
- Validate proxy server IP and render invalid URLs in GTK+3
- Rename "Toplevel" folder to "Bookmarks"
- Chrome identification option; "Automatic" user agent is Chrome-based
- Search: Create engines from search forms, remove "icon" field
- Copy Image s/Address// always copy both URL and data
- Rework debugging by introducing `MIDORI_DEBUG`; about:paths
- Adblock: Refresh filters based on file time and meta data, abp: links
- Optionally save website including resources
- Merged NextForward akin to StopReload
- PanedAction, Viewable, SpeedDial, (most of) Settings, Paths in Vala
- Improved database: requires sqlite 3.6.19 and 0.2.6 in import dialog
- Confirm Caret Browsing before enabling it
- Support for custom items in Statusbar Features (see FAQ)
- Draggable favicon as URL or text, URL icon for URL entries
- Remember if inspector was attached
- Open tabs in the background by default
- RTL support in special/ error pages
- Fix progressbar text with GTK+3
- Build fix: More robust GTK+2 version check
- Ensure progress in urlbar and tab match
- Zoom text and images by default
- Don't mixup tokens starting with the same letters
- Seemless running out of build folder
- No speed dial in --app/ --private, fix layout with many tiles
- Add X-GNOME-Fullname to .desktop and translate desktop shortcuts
- Delayed Load extension

## v0.4.6
- Fix crasher in geolocation infobar
- Fix crasher in about:version on some systems
- Fix crasher opening bookmarks from Unity global menu
- Use WebKitFaviconDatabase as of WebKit 1.8.0
- Use midori-prefixed temp folder in `midori_view_save_source`
- Fix cancelling downloads with SteadyFlow or Aria2
- Fix crash dialog instead of opening tab in a running window
- Fix page icons in multi-frame sites (gmail, tumbler)
- Distinguish Simplified and Traditional Chinese
- Support go-jump-symbolic
- Handle empty tabs due to download links with a target
- Handle frame load interrupted in the unholy trinity
- Fix libsoup version check and wrong SSL status in location

## v0.4.5
- Work around black border around widgets on Win32
- Whitelist direct/ re-directed navigation requests in adblock
- Require Vala 0.14
- Provide geolocation diagnostics in about:geolocation
- List available about: URLs and app instance name in about:version
- Replace illegal characters in download filenames
- Tweak app options on Win32 and use ShellExecuteEx in `sokoke_show_uri`
- Use `sokoke_show_uri` in `midori_browser_download_status_cb`
- External Download manager Steadyflow and Aria2 (with cookies)
- Ensure adblock config folder when blocking images
- Use sqlite WAL mode for history if available
- Allow relative -c/ --config path
- Context menus on Back and Forward toolbar items
- Always show the tabbar by default
- Use ubuntu-bug if it exists
- Show inline find while typing and statusbar text in overlay with GTK+ 3.2
- Esc/ closing "downloads still active" should cancel, not continue
- Optional Granite support for notebook and bookmark dialog as pop-over
- `^j` to toggle statusbar aka downloads
- Show at most 3 search engines in completion
- Don't replace existing onclick/ blur with autosuggest
- Implement `low_memory_profile` for FreeBSD and Win32
- Use var in internal javascript, to fix Google apps
- Handle download requests in frames

## v0.4.4
- Disable page cache with < 352 MB RAM
- Display filename in download dialog
- Fix box packing in GTK+3 (in most cases)
- Enable experimental HTML5 fullscreen API
- Harden IPv6 address recognition in location
- Experimental site data policy support (see FAQ)
- Close tabs by middle clicking close button
- Merge cookies and other data in Clear Private Data
- Improve KatzeArrayAction for Unity menuproxy compatibility
- Use GDateTime for history to avoid broken C runtimes
- Add Midori tag to DuckDuckGo default URI
- Rewrite completion popup resizing
- Streamline page icon loading stages and fallbacks
- Disable clipboard work-around for WebKit >= 1.4.3
- Re-word .desktop entry as an action
- Display informative text in private browsing
- Consistent clear icons in entries
- Revised download filename generation
- Add 'Open in Image Viewer' menu item
- Formhistory 2.0 with GDOM support
- Handle javascript: and mailto: links better
- Handle = key in Ukrainian layout better
- Fix bookmark export and deletion of bookmark folders
- Speed dial shortcut re-reordering by DND

## v0.4.3
- Implement about:widgets to test rendering
- Fix resizing of inspector by applying a minimum size
- Use dark theme with GTK+ 3 in private browsing
- Use channel-(in)secure-symbolic icons if available
- Use .security-(un)trusted classes with GTK+
- Improve notebook resizing peformance
- Fix tab icons in GTK+3 and don't look for GTK+ jscore
- Use system-wide CA file with libSoup 2.37.1
- Improve cookie manager performance
- Action and tab creation for faster startup
- Fix number of items in trash in private browsing
- Add Cairo version to about:version
- Add X-GNOME-Keywords and X-AppInstall-Keywords to .desktop
- Add easy privacy list to default Adblock filters
- Fully implement speed dial for GTK+3
- Disable box shadows with WebKitGTK+ 1.2.7
- Fine-grained monospace font overriding
- Implement resizing of Location and Search in toolbar
- Don't show empty speed dial shortcuts in-between
- Use Midori's name in midori-private.desktop
- Hide all bars in fullscreen and a menu to Unfullscreen

## v0.4.2
- Improve -moz-document parsing in user stylesheets
- Render verified secure sites in green, not yellow
- Version details for extensions built against a different release
- More detailed and more condensed about:version output
- Refresh missing speed dial thumbnails automatically
- Use faster global CSS mechanism for adblock and addons
- Show crash dialog only if there's a session
- Don't complete on a leading space or search token
- Support user stylesheets on about: and file:// locations
- Implement 'Always use my font choices' preferences
- Allow smaller tabs when close buttons are disabled
- Merge 'Closed Tabs' with 'History' in Clear Private Data
- Correctly use user-home and bookmark-new icon names
- Use versioned file speeddial-head-0.4.2.html
- Split proxy server preference into host and port
- Support localized 'next' and 'previous' links
- Implement 'Only accept cookies cookies from sites you visit'
- Fix crash in Add/ Import Bookmark feature
- Fix size of tabs with GTK+ 3
- Detect existing Firefox profiles for bookmark import
- Work-around "omg!" in local directory browsing
- Rework '--run' feature to allow window.open() and console.info()
- Automatically clear finnished downloads from the transferbar
- Add 'Create desktop shortcut' to the app menu
- Require GLib 2.22 and libSoup 2.27.90
- Don't register recent files in private browsing mode
- Findbar and speed dial honor close button position
- Use sqlite3-based backend for cookie storage
- Make '--snapshot' create png images with GTK+ 2.20
- Automatically resizing, embossed speed dial, close on hover

## v0.4.1
- Experimental, unfinnished GTK+ 3 support
- 'Automatic' identification with quirks
- Build fix for WebKitGTK+ >= 1.4.3
- Register downloaded files as recent files
- Fix Flash window on background tabs
- Fix regression with clearing cookies on quit
- Fix opening tabs from toolbar buttons
- Use symbolic find and clear icons
- Drop usage of mootools
- Install separate Private Browsing shortcut
- Support dragging tabs out of the window
- Use feed: to support Thunderbird news reader
- Re-open closed tabs in private browsing
- Compare link-fingerprints caselessly

## v0.4.0
- Provide buttons to choose how to startup after crash
- Fix crash on corrupted datbase
- Never delay URIs given as command line arguments
- Space at the bottom of the page: Go to next page
- Initialize session in app/ private before adding URIs
- Add 'Last open tabs' option to Clear Private Data
- Show kinetic scrolling option regardless of Hildon
- Interpret Shift+Backspace as going forward
- Advertise SVG images as a supported MIME type
- Zoom in steps of 10% and support `^=`
- Fix a crasher on invalid geo: links
- Integrate Adblock and History List options in list
- Skip empty lines, ignore subdocument rules in Adblock
- Respect VALAC at configuration time
- URL cache, faster JS generator, inline parsing in Adblock
- Reuse source of webview instead of redownloading
- Remove the description field from bookmark dialog
- Add --log-file/ -l switch to log to a file
- Pass through javascript: URIS from the command line
- Tab and Window items in Unity Quicklist
- Adjust the preferences dialog
- Require WebKitGTK+ 1.1.17 and Vala 0.10

## v0.3.6
- Track selected search engine per window
- Improve preference dialogue size and alignments
- Validate URIs in Adblock, homepage and bookmarks
- Fix loading of Adblock lists from https
- Support Backspace as Go Back and F5 as Reload
- Show 'Private Browsing' in Unity Quicklist
- Ignore Network Cancelled errors
- Reduce allocations when preparing speed dial
- Fix icon sie of scalable stock icons
- Implement geo URI support as per RFC 5870
- Fix crash after clearing cookies
- Faster javascript-based JSON import
- Improve speed dial markup, without scripts
- Allow Escape to cancel History List
- Fix crashes in completion

## v0.3.5
- Remove frame titles from preference dialogue
- Show search engine icons in completion
- Add Liferea news aggregator workaround
- Support libSoup cache- size with WebKitGTK+ 1.3.11
- No language, no encryption but Mozilla in user agent
- Support `F6`, `F7`, `^(Shift)+Tab` and `Tab` to complete
- Strip scheme and `www.` in completion
- Render filename as title of patch files
- Turn location into a plain entry
- Fix tab panel foreground colours
- Mask timezone, language and plugins in private mode
- Add 'Strip referrer details' preference
- Embed extension list in preferences
- Remove the Page Holder and Download Manager option
- Disable prefetching and HTML5 storage in private mode
- Handle 'Plugin will handle load' error
- Show access keys next to numbers in link search
- Introduce --private/ -p command line switch
- Don't show toolbar preferences if running a DE
- Show script alerts as infobars
- Improve URI handling with addon installer
- Change `^Q` for Quit to `^Shift+Q`
- Make speed dial faster and mandatory
- Load speed dial in private browsing mode
- Show video formats in about:(version)
- Move speed dial to key file instead of JSON
- Add Offline Application Cache to Clear Private Data

## v0.3.3
- Use 60 connections and 6 per host
- Allow re-ordering of search engines
- Resurrect right-click button on the panel
- Page Next finds a and link tags again
- Always save state when quitting
- Support MD5 and SHA1 Link Fingerprints
- Use lock-secure and lock-insecure icons
- Replace unmaintained docs with FAQ
- Work around copying bug in WebKitGTK+
- In doubt always focus page on key press
- Show transfer speed in tooltips
- Support x-scheme-handler for GLib < 2.28
- Improve link search, always require Return
- Re-order tabs with `^Shift-PageUp/Down`
- Improve fragment (#) handling
- Show Netscape plugins in about:version
- Add Zoom Level combobox to Statusbar Features
- Improve handling of cookie updates
- Always show a minimum visible progress
- Don't limit search engines in completion popup

## v0.3.2
- Fix opening address with Go button
- Fix automigration of existing bookmarks
- Fix crash on opening autocompletion
- Fix adblock handling of frames
- Reflect tab order in the saved session
- Don't show multiple user addon infobars
- Provide distribution setting for close on left
- Export to Netscape HTML format
- Avoid config update on state changes
- Always show progress and search engines in location
- Default to app menu and no menubar
- Fix GTK+ 2.14 build problems
- Show 'Private Browsing' in window title
- Uncached reload with `^Shift+R`

## v0.3.0
- Support libnotify 0.7
- Copy-friendly URIs with %20
- No blocking of typed URLs with adblock
- Import from Netscape HTML
- Bookmark im- and export fixes
- Unit tests cleaned up and updated
- Correct bookmark and search icon names
- Better link menu handling
- Certificate location on FreeBSD
- Fix Russian keyboard issues
- Stylesheet parsing improvements
- Simplify language and panel options
- Default to DuckDuckGo search
- No Netscape plugins in extension panel
- Easy user addon install infobar

## v0.2.9
- Add 'Identify As' to Statusbar Features
- Don't restrict length of HTTP login passwords
- Implement Find Links by number with '.'
- Reflect security in icon tooltip
- Use GIO to determine special URI schemes
- Upgrade waf (addresses threading issues)
- Allow clearing HTML5 databases and form history
- Add --help-execute command line switch
- Improve private mode, with search and hotkeys
- Support no-desktop-files and internal Open With
- Support x-scheme-handler spec
- Infobar for location and HTML5 database
- Optimise cookie storing, reduce wakeups
- Avoid deprecated GTK+ interfaces
- Remove console in favour of Inspector
- Simplify and explain cookie preferences
- Fix Google Reader incompatibility

## v0.2.8
- Re-implement Bookmarks menu and toolbar button
- Show transferbar even if statusbar is hidden
- Smart case for inline search while typing
- Use Alt+Shift+Right instead of `^Right` for Next Page
- Adding, edit and delete buttons for user scripts/ styles
- Rename 'Minimize Tab' to 'Show Tab Icon Only'
- Delete key in completion deletes items
- Don't show homepage in bookmarkbar
- Fix crash when using location arrow button

## v0.2.7
- Multiple word completion in location
- Database backed bookmarks
- Search bookmark panel and drag bookmarks
- Bookmarks in address completion
- Removed bookmarks and history from menubar
- Add 'Minimize New Tabs' and 'Copy Addresses of Tabs'
- Refactorings and optimisations in the core
- Adblock compatibility improvements and speedup
- Changeable speed dial size
- Delayed pages at startup, or after a crash

## v0.2.6
- Show a dialogue when quitting while downloading
- Render icons in errors/ speed dial properly
- Fix a build error with API documentation
- Fix error pages in frames, and a related crash
- Allow more shortcuts or columns in speed dial
- Add 'Copy All' button to Console panel

## v0.2.5
- Keyboard access in speed dial
- Panels adapt to system icon style
- Revamp tab focus handling
- Use new GTK+ 2.20 spinner (throbber) widget
- Userscripts and -styles can be (de)activated
- Warn if trying to download with few space
- Support right button in Mouse Gestures
- Add (unfinished) 'External Applications' extension
- Vala support for extensions and tests
- Yellow location for valid SSL, red for invalid
- Render XML as source code
- Provide tools/midori-dev and check-style scripts
- Implement `MIDORI_ADBLOCK` for Adblock testing
- Fix https URI support in Adblock
- Change 'Autodetect proxy' into 'Proxy type'
- Update use of deprecated GTK+ API
- Implement --blocked-uris for kiosk usage
- Implement --inactivity-reset for kiosk usage
- Fix typing with dead keys and NumLock
- Improve parsing in the Feed Panel
- Add preference 'Allow scripts to open popups'
- Spawn web apps and private mode with same executable
- Base Colourful Tabs on icon colours
- Add Status Clock extension
- Resolve hosts before trying a search
- Allow page icons for https
- Improve handling of special pages
- Protect against recursive external URI handlers

## v0.2.4
- Prevent completion from overlapping
- Fix tab order when restoring session
- Ignore accidentally middle click search
- Implement bookmark export to XBEL
- Provide scroll hotkeys, default to Vim
- Store and complete search in location
- Fix opening externally with multiple windows
- Only use icons in panel buttons
- Fix build with different GTK+ versions
- Omit micro version and arch from ident string

## v0.2.3
- Improve relocatability for Win32
- Implement 'Close other tabs' menu item
- Use new GTK+ accessors where available
- Allow searching freely in History panel
- Re-implement completion based on sqlite
- Re-implement completion suggestion popup
- Simplify sqlite use towards efficient calls
- Move panel icons to the bottom
- Merge Netscape Plugins and Extensions panels
- Implement `about:version` special page
- Implement 'Preferred languages' preference
- Improve window raising behaviour
- Allow `^Right-click` to suppress javascript menu
- Add 'Open link as web app' in context menu
- Add 'Block image' menu item to Adblock
- Location progress and compat code refactored
- Implement 'Paste and proceed' in location
- Move DNS prefetching into the core
- Allow selecting and deleting multiple cookies
- Support attaching/ detaching web inspector
- Always enable web inspector
- --diagnostic-dialog command line switch
- Faster file existence checks
- Simplified, faster adblock implementation

## v0.2.2
- Turn libnotify into a proper build-time dependency
- Use `^Return` to open tabs from the location entry
- Support right-click on bookmark menu items
- Support -e in midori -a and with multiple commands
- Make Middle click open selection search if needed
- Make `^C` work as expected again
- Fix order of History, Trash and Recently opened pages
- Revise Shortcuts dialogue to fix oddities
- Perform Form history completion case insensitive
- Add 'Web Cache' to Delete Private data dialogue
- Load accels from /etc/xdg if present
- Improve XBEL format compatibility and performance
- Fix inline find by correcting key handling
- Add option to open panels in separate windows
- Support Portrait orientation in Fremantle
- Support Hildon MIME and URI handling
- Check status before caching in Web Cache
- Show popup menu on news feed icon if needed
- Support Colourful Tabs with Tab Panel
- Tweak sqlite and dbus handling for Win32
- 'Run as web app' and 'Show in toolbar' for bookmarks
- Add 'Small icons' toolbar style
- Fix build with Glib < 2.20 and GTK+ < 2.12
- Add Import bookmarks for XBEL, Opera and RDF
- Add Open Link in Foreground/ Background Tab menu
- Allow closing all tabs
- Hildon file chooser support

## v0.2.1
- Fix Mouse Gestures to work after activation
- Explicitly link to X11 to support gold
- Implement various Hildon specific features
- Hide the navigationbar in fullscreen
- Implement permanent storage of form history
- Support keyboard shortcuts like `^Tab` or `a`
- Handle SIGHUP, SIGINT, SIGTERM and SIGQUIT
- Make creation of new windows fast
- Introduce the Tab History List extension
- Load icons laziy at startup to speed up startup
- Introduce a Web Cache extension
- Refactor and tweak the Preferences dialogue
- Implement combos to choose external applications

## v0.2.0
- (Kinetic) drag scrolling on touchscreen devices
- Workaround a speed dial crasher
- Faster Adblock with element blocking, for all WebKitGTK+ versions
- Stripped menu, toolbar and tap on hold on Maemo, and 5.0 menu support
- Add a DNS prefetching extension
- Better IDN handling
- Add a form history extension
- Restore scrolling positions from the session
- Keep typed address when switching tabs
- Avoid storing duplicate history items per day
- Fix multiple duplicate HTTP authentication dialogs
- Pass mailto: links to the email client
- Improve context menu with WebKitGTK+ 1.1.15
- Checkbox "Remember password" in HTTP authentication
- Fix a crasher when modifying bookmarks
- Support page icons other than favicon.ico
- iPhone identity in Network preferences

## v0.1.10
- Fix freezing when opening multiple windows
- Revamp Adblock with WebKitGTK+ 1.1.14 API
- Greatly improve the address completion
- Always show news feed icon
- Better handling of feeds in the feed panel
- Add Gtk+ and WebKit version to the About dialog
- Improve tab panel and support minimized tabs
- Implement disabling of extensions in crahs dialog
- Don't make the web inspector transient
- Tidy up the Preferences a bit
- Load default bookmarks and config from /etc
- Do not use xprop at runtime
- Use GNOME proxy server if libsoup-gnome is installed
- Integrate Save As with transfers
- Save HTTP logins in a text file
- Support Undo and Redo with WebKitGTK+ 1.1.14

## v0.1.9
- Preserve navigation history with new tabs
- Implement clearing private data when quitting
- Ellipsize and show close icons in the tab panel
- Allow hiding panel operating controls
- Integrate Tools with the compact menu
- Fix User scripts, User styles and Plugins panel
- Remove the bookmarkbar popup
- Add New Tab to the tab context menu
- Implement minimizing tabs

## v0.1.8
- Initial support for extension unit tests
- Set a "browser" role on browser windows
- Support typing search tokens to open websites
- Fix focus loss when switching search engines
- Rewrite Netscape Plugins panel backed by javascript
- Implement a compact menu if menubar is hidden
- Provide a context menu for tab labels
- Implement Tab Panel as a tabbar replacement
- Remember the last active tab
- Read and write XBEL metadata internally
- Implement -e, --execute to perform commands
- Support socket based single instance
- Move Go button inside the location entry
- Fix the ident string after Midori updates
- Bind Alt- n to switching to the n-th tab
- Revisit conflicting mnemonics
- Add a Toolbar Editor extension
- Add a Shortcut Editor extension
- Implement context menu in the Transfers panel
- Simplified Extensions and Addons panels with tick marks
- Fix Mouse Gestures often ignoreing gestures
- Use one cookie manager model in all windows
- Support building Midori for Win32
- Add an entry to specify Fixed-Width font size
- Implement Save As in the download dialog
- Use one history model in all windows

## v0.1.7
- Save the activation status of extensions
- Catch and ignore mouse buttons meant for horizontal scrolling
- Improve panel detaching and how panels handle it
- Add a Feed Panel extension
- Add a Fixed-width Font Family preference
- Support spell checking
- Implement (optional) Speed dial feature
- Support nicer error pages with WebKitGTK+ 1.1.6
- Implement middle click to open menu items in tabs
- Implement -s, --snapshot command line switch
- Use libnotify (runtime dependency) for finished transfers
- Add a Go button to the address entry
- Always append tabs opened via middle/ double click on the tab bar
- Implement Open new pages in: New window preference
- Implement inline find with direct '.' and '/' hotkeys
- Add basic support for @-moz-document in user styles

## v0.1.6
- Add Delete All to transferbar
- Show search in context menu
- Implement 'Default' search engine
- Show only icons in Statusbar Features
- Implement Clear private data
- Support News Feed icon and external aggregator
- Fix reloading of Not found pages
- Fixup spaces when middle click opening
- Fix possibly wrong identificaton string
- Optionally search engines in completion
- Optionally Gtk 2.16 entry progress and icon
- Experimental panel detaching
- Support external download manager again
- Implement '-a', '--app' argument
- Implement '-c', '--config' argument
- Fix a bookmark saving issue
- Support data: URIs in the address entry
- Several performance and memory leak fixes
- Load cookies idle to accelerate startup
- Support mailto: links
- Save tab reordering in the session
- Add a Cookie Manager extension
- Fix crashers in Colourful Tabs

## v0.1.5
- Add a Colorful Tabs extension
- Support downloading with WebKitGTK+ 1.1.3
- Load and save settings of extensions
- Drop internal source view
- Require WebKitGTK+ 1.1.1, Glib 2.16 and libsoup 2.25.2

## v0.1.4
- Automatic inline find can be disabled
- Implement an Encoding menu
- Add Open all in Tabs for bookmarks and history
- Bookmarks can be moved to other folders
- Fix blank page 'loading' and HTTP authentication
- Display history dates in the local format
- Allow editing of completion items

## v0.1.3
- Sidepanel can be aligned on the right
- Bookmarks can be organized in folders
- Support find as you type
- Support international domain names
- Tweak location completion
- Provide default search engines
- Integrate with Maemo if available
- Implement Mouse Gestures extension
- Implement a Plugins panel
- Editing the toolbar via a context menu
- Introduce Zoom Text and Images preference

## v0.1.2
- Open new tabs by clicking on the tabbar
- Refactor and speed up location completion
- Show a Crash dialog after crashes
- Dynamically save files when needed
- Support Back/ Forward mouse buttons
- Support javascript: bookmarklets
- Implement Proxy and Identification string
- Implement cookie storage on disk
- Remove autotooled build system
- Add a new Extensions panel
- Implement opening of new windows
- Display tooltips in Preferences

## v0.1.1
- Reimplement page holder as an extension
- Introduce a C extension interface
- Introduce unit tests for automated testing
- Implement history based location completion
- Support the Web Inspector in new WebKit versions
- Bookmarkbar properly reflects changes
- Improve overall OS X integration
- Add a Text Editor Preference
- Add a Compat sidebar Preference
- Add an Open external pages in Preference
- Implement source view and cached favicons with libsoup

## v0.1.0
- Allow for hiding the menubar
- Make the navigationbar customizable
- Implement a History panel
- Remove the HTTP Proxy hack
- Add an Always Show Tabbar Preference
- Implement 404 error pages
- Remove the Primary Clipboard hack
- Provide user documentation
- Display Not found errors when possible
- Remove Stylesheet and Zoom Stepping preferences
- Make dialogs more compact
- Ellipsize extremely long menu items
- Save the trash again when quitting
- Implement enabling/ disabling addons

## v0.0.21
- Update some translations
- Show progress in location when statusbar is hidden
- Alt- Enter in location should issue a new tab
- Warn at configure time if GVfs is not installed
- Remove GVfs code that could caused huge problems
- Update wad to 1.4.4 to fix building on some systems

## v0.0.20
- Single instance support using Unique
- Make it clear that WAF is preferred
- Provide an `extension` icon
- Load user styles from `~/.local/share/midori/styles`
- Use `^Shift+T` for Undo Close Tab
- Add `open-tabs-next-to-current` preference
- Use rsvg-convert instead of imagemagick's convert
- @name in the meta data of userscripts is recognized
- Remove `small-toolbar` preference

## v0.0.19
- Improved Greasemonkey compatibility
- Improve multiple window support
- Use WAF buildscripts, still keeping autotools
- Install and use Midori logo
- Support zooming and printing
- Enhance Gjs functionality
- Refactor in some places, particularly Web Search
- Implement favicons and source view with GIO
- Introduce new fancy location entry
- Detect and show news feeds on web sites
- Save the session as needed, not only on quit
- Reintroduce Download Manager preference

## v0.0.18
- First attempt at userscripts and extensions.
- Show hidden location/ web search temporarily when needed.
- Turn prefs into MidoriPreferences
- Fix background tabs, strings and new tab focus.
- Switch configuration to MidoriWebSettings.
- Remove 'External programs' logic
- Append the closed tabs items as a proper submenu.
- The location is empty and focused by default
- Implement proper menu positioning.
- Implement the Console panel for script messages.
- Implement localization via Gettext.
- Initial refactoring work, regressions expected
- Build fix: Webkit's header and pkgconfig name have changed.
- Implement Fullscreen mode

## v0.0.17
- Add a preference to choose a user stylesheet.
- Implement a few preferences with new settings API in WebKit
- Implement Add Bookmark and a small panel toolbar
- Escape search engine name and description.
- Cleanup and WebKit API update
- Make sure selection actions have a widget.
- Allow Find Next and Find Previous when the findbox is hidden.
- Fixed the header of the KatzeThrobber
- Move XBEL implementation to katze.
- Implement a throbber widget.
- Always enable Select All if an editable widget is focussed.
- Previous/ next tab menu items should be disabled when not needed.
- Handle the context menu on button press, not release.
- Open the default page only if there is no session and no uri on the cli.

## v0.0.16
- Implement editing menu items for the web view.
- Implement the bookmarks panel with editing capabilities.
- Prevent repeated checks for the desktop environment.
- Fix coding style in sokoke.c/ sokoke.h, particularly variable names.
- Don't update the remembered window size when maximized.
- Don't remember the window position but the size only.
- Command line uris should replace the default page.
- More effective status updates and less entry flickering
- Enable inline find for websites
- Make the progressbar work properly again
- Build fix: Adapt WebKit api changes
- Add Tab Size to preferences dialog

## v0.0.15
- Build fix: Remove search api

## v0.0.14
- FIX Reopening a tab from the trash causes a crash
- FIX An untitled website keeps the previous title
- FIX When switching tabs the location/ title isn't updated correctly
- FIX Issues with the preferences dialog
- Disable location completion for now
- Save tabtrash to file
- Restructure some code
- Remove color picker and throbber
- Change the license to LGPL

## v0.0.13
- Adapt WebKit api change, remove engine wrappers, remove dialog hack
- Improve XBEL loading and saving
- Show dialog and backup files on startup errors
- Rearranged and removed some menus

## v0.0.12
- FIX Improve flawed window creation
- Build with and eliminate all compiler warnings
- Implement clipboard handling menus
- Allow editing of search engines
- Update search engines properly
- Implement bookmarks saving
- Implement session saving and loading
- Cleaned up and revised most code
- Remove legacy webi code

## v0.0.11
- FIX Back/ forward and initial check menu item states
- Remove rather useless debugging helpers
- Improvements on the preferences
- First attempt at websearch
- Preserve typed uri on tab switch
- First attempt at bookmarks, readonly for now
- Add an animated throbber

## v0.0.10
- FIX Can crash on context menu or new protocol
- FIX Location isn't updated on tab switch
- Remember last window position and size
- Implement Open menu item
- Allow using location and web search if hidden

## v0.0.9
- FIX Close tab not insensitive for only one tab
- FIX Debug output is broken
- Display uri when hovering a link
- Implement link uri related part of context menu
- Implement alt/ middle/ shift click link
- First attempt at external protocol handlers
- Initial download manager integration
- Adapt WebKit api prefix change
- More code reorganization and cleanup

## v0.0.8
- FIX Crash when invoking document context menu via keyboard
- FIX Can't build with debug = yes on GTK+2.12
- Changes related to icons in the gui
- Reorganize code by splitting into several files
- Switch from WebkitGdk to WebkitGtk

## v0.0.7
- FIX Make settings finally work flawlessly
- FIX Can crash when settings are opened
- Handle all panels in a general way
- Install xdg compliant desktop file
- Implement location and web search menu items
- Display a loading icon on tabs again
- Changed the settings dialog again

## 0.0.6
- FIX Closing an individual tab doesn't work correctly.
- FIX Doesn't build with gtkwebcore.
- Reimplement menus and and navibar with GtkUIManager.
- Improve document handling in general.
- Finished tab trash menu.
- Implement searchbox default text.
- Remove some gtkwebcore code.
- Use Xfce style dialog in Xfce.
- Implement a few settings.
- Change the panel's look.
- Implement a 'pageholder' panel.

## v0.0.5
- Implement a few more signals for WebkitGdk.
- Add tooltips to navigation toolbar buttons.
- First attempt on a settings dialog.
- Reimplemented color picker.
- Autocompletion for location and searchbox.
- Changed menu items and incremental findbar.
- Implement tab switching via keyboard.

## v0.0.4
- FIX Midori segfaults when quitting.
- FIX Config loading and saving is broken.
- Switch WebkitGdk to gtk api and make it the build default.
- Register custom stock icons instead of icon theme magic.
- Implement dynamic window menu.
- First attempt on resizable panels.
- Add about dialog.

## v0.0.3
- FIX Refresh via menu or shortcut crashes the browser.
- FIX Assertions with and visibility of the progressbar.
- FIX Tabs are not reorderable.
- Package versions in ./configure result and --version output.
- Improve view menu and add tools menu.
- Replace deprecated functions and macros.
- Implement settings saving and loading.
- Fill the common context menu with items
- Allow multiple homepages, seperated by '|'.
- Make code typesafe and C++ friendly.
- Initially support WebkitGdk directly.
- Urlify location inputs automatically.

## v0.0.2
- Dynamic tab trash menu.
- Update UI when page is changed.
- Enhanced WebkitGtk support.
- New function `sokoke_dialog_run_modeless`.
- Finished `on_document_request_script_prompt`.
- One name and version, visible in the user agent.
- Changed some accelerators and menu items.
- Create and destroy color picker properly.
- `^Wheel` resets the zoom level.
- Escape in the location entry resets the uri.
- Use gtk-webcore prefix instead of osb now.
- Save keybindings on quit.
- Fancy autotools build setup.

## v0.0.1
- Initial release
