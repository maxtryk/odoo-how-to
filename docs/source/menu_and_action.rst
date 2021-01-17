Menu and Action
===============

#. add to manifest:

    .. code-block:: python

        'data': [
            'views/menu.xml',
        ],

#. have `views/menu.xml`:

.. code-block:: XML

    <!-- root menu -->
    <menuitem id="library_menu"
              name="Library"/>

    <!-- action for the model -->
    <act_window id="action_library_book"
                name="Library Books"
                res_model="library_app.book"
                view_mode="tree,form"
                domain="[('customer', '=', True)]"
                context="{'default_customer': True}"
                limit="10"/>

* `name` - top-left corner title for views opened by the action
* `res_model` - target model
* `view_mode` - ordered list of enabled views
* `domain` - to filter records
* `context` - context to set
* `limit` - limit of records for the tree view

.. code-block:: XML

    <!-- top-menu -->
    <menuitem id="menu_library_book"
              name="Books"
              parent="library_menu"/>

    <!-- sub-menu -->
    <menuitem id="sub_menu_library_book"
          name="Books Sub-menu"
          parent="menu_library_book"
          sequence="1"
          action="action_library_book"/>

    <menuitem id="another_sub_menu_library_book"
          name="Another Books Sub-menu"
          parent="menu_library_book"
          sequence="0"
          action="action_library_book"/>

* `name` - title
* `parent` references parent menu's `id` to create a sub-menu
* `action` references the action to all
* `sequence` - for ordering menus of the same level
* `groups` - list of user groups that can access the menu
