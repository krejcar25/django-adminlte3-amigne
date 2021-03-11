# django-adminlte3
[![pypi_badge](https://badge.fury.io/py/django-adminlte3-amigne.png)](https://pypi.org/project/django-adminlte3-amigne/)
[![licence badge](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/amigne/django-adminlte3/master/LICENSE)

django-adminlte3 provides the functionality of the AdminLTE3 theme
to developers in the form of standard base templates. Optional styling for
Django's built-in admin interface is also provided.

<!--## Installation

Installation using pip:

    pip install django-adminlte3

Add to installed apps:

    INSTALLED_APPS = [
         # General use templates & template tags (should appear first)
        'adminlte3',
         # Optional: Django admin theme (must be before django.contrib.admin)
        'adminlte3_theme',

        ...
    ]

Don't forget to collect static
    
    python manage.py collectstatic -->

## Usage
The [base template] is designed to be highly customisable. Template blocks are provided to
allow you to hook in customisations as you wish

<!--### Admin Theme Usage
Install as per the above installation instructions. The django admin UI should then change as expected.-->

<!--### Documentation
Can be found at: http://django-adminlte3.readthedocs.io-->

### Template blocks
Base templates define blocks that may be set in templates that extends them.

Here is a list of available blocks. Blocks marked as 'new' are introduced in
this forked *django-adminlte3* implementation. Blocks marked as 'deprecated'
were present in *d-demirci/django-adminlte3* and remains supported in this
implementation until v0.3.0 where they will disappear. Deprecated blocks may
have a 'new' alternative, in such a case it is recommended to upgrade your
templates to adopt it.

The following blocks are available for use:
* `HTML` element
  * `html_lang` (new) - Defines the value of the `lang` attribute in the
    `<html>` element. Defaults to `en`.
* `HEAD` element
  * `title_outer` (deprecated) - Surrounds the `<title></title>` element in the
    `<head></head>` of the document; deprecated as an empty `head_title` block
    value may be used instead.
  * `head_title` (new, replaces `title`) - Value of the `<title></title>`
    element. Defaults to `{{ site.name }}`
  * `head_meta` (new) and `meta` (deprecated) - Surrounds the default `<meta>`
    elements. Can be reset with a blank block, or completely redeclared.
  * `css` (new) and `stylesheets` (deprecated) - Surrounds the default `<link
    rel="stylesheet">` elements. Can be reset with a blank block, or completely
    redeclared.
    * `css_xtra` (new) and `style_sheets` (deprecated) - Placeholder for extra 
      CSS stylesheets set in your templates without overwriting the default CSS
      stylesheets.
  * `head_xtra` (new) and `extra_head` (deprecated) - Placeholder for extra
    elements in `<head></head>`.
* `BODY` element
  * `body_class` (new) - Surrounds the default value of the `class` attribute in
    the `<body>` element.
    * `body_class_xtra` (new) and `bodyclass` (deprecated) - Placeholder for
      extra classes in `<body>` element. *d-demirci/django-adminlte3*'s
      `body_class` has been reused in the current implementation.
  * `body_wrapper` (new) and `body` (deprecated) - Surrounds the `<div
    class="wrapper"></div>` element and all of its content.
    * `nav_header` - Surrounds the `<nav class="main-header"></nav>` element 
      that forms the top header.
      * `nav_bar` (deprecated) - Contains all the elements of the top header.
        * `navbar_link` (new) - Surrounds the `<ul class="navbar-nav"></ul>`
          element that forms the links menu.
        * `navbar_center` (new) and `nav_bar_center` (deprecated) - Surrounds
          the search form in the navbar.
        * `navbar_custom` (new) and `nav_custom_menu` (deprecated) - Surrounds
          the dropdown menus on the right-side of the navbar.
          * `header_dropdowns` (deprecated) - Content of the `<ul></ul>` element
            defined in the upper-level `navbar_custom` block.
            * `user_info` (deprecated) - Declares the item with user profile
              information.
              * `change_password_url` (deprecated) - Declares the password
                change URL.
              * `logout_url` (deprecated) - Declares the logout URL.  
    * `nav_sidebar` - Surrounds the `<aside class="main-sidebar"></aside>` 
      element that forms the menu.
      * `logo` - Defines the logo on the top left hand corner of the page.
        * `logo_text` (deprecated) - Defines the logo text
      * `sidebar` (new) - The content of `<div class="sidebar"></div>`. 
      * `sidebar_user_panel` (new) and `user_panel` (deprecated) - Defines the
        user panel in the lateral menu.
      * `sidebar_search_form` (new) and `form` (deprecated) - Placeholder for
        optional search form in the sidebar.
      * `sidebar_menu` (new) and `nav_links_ul` (deprecated) - Defines the 
        sidebar menu content.
        * `nav_links_outer` (deprecated) - Defines the list items of the menu.
          * `nav_heading` (deprecated) - Defines the content of the menu
            heading line.
          * `nav_links` (deprecated) - Defines the list items with the menu
            links.
    * `content_wrapper` - Surrounds the content wrapper.
      * `content_header` - Surrounds the 
        `<section class="content-header"></section>` element.
        * `no_heading` (deprecated) - Defines the content of the
          `content_header` section.
          * `title` (new) and `page_name` (deprecated) - Defines the title of
            the page.
            * `header_actions` (new) and `page_actions` (deprecated) -  Defines
            actions.
          * `header_description` (new) and `no_description` (deprecated) -
            Defines description in the header.
            * `page_description` (deprecated)
          * `breadcrumbs` (deprecated)
      * `content_section` (new) and `content_outer` (deprecated) - Surrounds the
        `<section class="content"></section>` element.
        * `messages` - Displays the messages returned by the applications.
        * `content` and `content_block_wrap` (deprecated) - Placeholder for the
          page content.
    * `footer_wrapper` (new) and `nav_footer` (deprecated) - Surrounds the
      `<footer class="main-footer"></footer>` element that forms the page
      footer.
      * `footer_right` - Declares the content on the right of the footer
        (typically the version).
        * `version` - Contains the version number
      * `footer_left` - Declares the content on the left of the footer
        (typically the copyright).
        * `legal` (deprecated) - The legal content

    
  * `js` (new) and `javascript` (deprecated) - Surrounds the default `<script>`
    elements. Can be reset with a blank black, or completely redeclared.
    * `js_xtra` (new) - Placeholder for extra scripts set in your templates
      without overwriting the default scripts. In *d-demirci/django-adminlte3*,
      this was named `js`, but this block name is reused in the current
      implementation.
  * `extra_js` (deprecated) - Placeholder for extra scripts. Contrary to
    `js_xtra`, this placeholder is set outside of the `js` block.
  * `body_xtra` (new) and `extra_foot` (deprecated) - Placeholder at the foot of
    the `<body></body>` element.

## Versions
* v0.2.0 (under development)
  * Templates are reworked: Included subtemplates are embedded into the main
    template, so the blocks are now correctly parsed.
  * Transition release: Block compatibility with *d-demirci/django-adminlte3* 
    v0.1.7-alpha is supported when possible. Some new blocks are introduces, 
    others are deprecated (an alternative may be proposed, or not.)
  
* v0.1.99 (March 9th, 2021)
  * Similar to release v0.1.7-alpha of `d-demirci/django-adminlte3`
    
## Credits
This project a based heavily on work by the following:
* d-demirci for [d-demirci/django-adminlte3]
* dnaextrim for [django_adminlte_x]
* beastbikes for [django-adminlte]
* adamcharnock for [django-adminlte2]


<!-- ## Screenshots
Admin Area:
* Home :![admin screenshot](https://user-images.githubusercontent.com/24219129/68544333-214e8c00-03d3-11ea-91a1-4cfb94d2b136.png)
* Model :![model screenshot](https://user-images.githubusercontent.com/24219129/68544364-77233400-03d3-11ea-97b3-350884c68f6a.png)
* Editing Model: ![model edit](https://user-images.githubusercontent.com/24219129/68544387-b6518500-03d3-11ea-9f28-27df1d996b06.png)

Site Area:
* Landing: ![site area](https://user-images.githubusercontent.com/24219129/68544298-cd43a780-03d2-11ea-8506-3abfa341a914.png) -->

[base template]: https://github.com/d-demirci/django-adminlte3/blob/master/adminlte3/templates/adminlte/base.html
[d-demirci/django-adminlte3]: https://github.com/d-demirci/django-adminlte3
[django_adminlte_x]: https://github.com/dnaextrim/django_adminlte_x
[django-adminlte]: https://github.com/beastbikes/django-adminlte/
[django-adminlte2]: https://github.com/adamcharnock/
