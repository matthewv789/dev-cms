dev-cms
=======

File-based CMS, meant to overcome problems typical of database-driven content management systems like WordPress, Drupal Joomla, etc.

Some design goals:
- Cache by default. That is, the webroot will point to a cache directory (containing static HTML files generated each time a page is built) for best performance.
- This, combined with efficient PHP coding generally not requiring database accesses (especially many db queries), and some other intermediate caching, should result in very high performance by default.
- Separate core CMS files from site-specific files for easier updating
- File-based means that not just templates but also page content can be version-controlled and easily migrated between different environments. Whole copies of the site can be checked out by other developers.
- File-based also means that good desktop text editors can be used to edit files, rather than sub-standard browser-based Javascript editors.
- Database would be used only for things like user-generated data and search indexing.
- Should support many of the latest/best trends in web development practice, such as being able to load subsequent page content as partial pages via ajax, providing RSS feeds, supporting mobile/responsive design, etc.
- Support custom content types and fields by default, as well as the equivalent of Drupal's Views.
- Should also support at least a basic publishing workflow, not just of new pages but of changes to existing content.

Some basic assumptions:
- Site can be installed within an arbitrary directory; it will not work when just put directly into default "htdocs" directory. That is, user must be able to, and know how to, modify httpd.conf or similar configuration. (Many web control panels do make this easy though.)
- Front-end which delivers and displays existing content to site visitors will be written first; thus actually managing the content will at first require some knowledge of the underlying file structure. (Until a web back-end is written for site content management, it won't really be a CMS.)
- At first, development practice will assume at least moderate front-end coding skills; won't cater mainly to non-developers and non-coders.