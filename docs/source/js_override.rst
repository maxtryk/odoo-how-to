Override a Javascript Component
===============================

#. :doc:`js_assets`
#. define a new JS module in the added asset file:

    .. code-block:: javascript

        odoo.define('list_controller_mod', function (require) {
            'use strict';

            // find the component needed to change and require its module
            let ListController = require('web.ListController');

            // call include to modify the needed item
            ListController.include({
                _onCreateRecord: function (event) {
                    // your version of the original _onCreateRecord function
                }
            });

        });
