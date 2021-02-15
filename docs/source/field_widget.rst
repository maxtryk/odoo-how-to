Field Widget
============

#. :doc:`js_assets`
#. define a new JS module in the added asset file:

    .. code-block:: javascript

        odoo.define('custom_date_format_widget', function (require) {
        "use strict";

        let AbstractField = require('web.AbstractField');
        let fieldRegistry = require('web.field_registry');

        let field = AbstractField.extend({
            // CSS class to be used for wrapping element
            className: 'o_custom_date_format',
            tagName: 'span',
            supportedFieldTypes: ['date'],
            init: function () {
                this._super.apply(this, arguments);
            },
            // customize read-only view of the field here
            _renderReadonly: function () {
                let value = this._formatValue(this.value);
                this.$el.html($(`<span>${value}</span>`));
            },
        });

        fieldRegistry.add('custom_date_format', field);

        });

#. set the widget as field attribute

    .. code-block:: XML

        <field name="created_at" widget="custom_date_format"/>