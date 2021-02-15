Add a Javascript Asset
=============================

#. have `static/src/js/another_mod.js`
#. have `views/assets.xml`:

    .. code-block:: XML

        <odoo>
            <template id="another_mod" name="another mod" inherit_id="web.assets_backend">
                <!-- <xpath expr="//script[last()]" position="after"> -->
                <xpath expr="." position="inside">
                    <script type="text/javascript" src="/another_mod/static/src/js/another_mod.js"></script>
                </xpath>
            </template>
        </odoo>

#. add to manifest:

    .. code-block:: python

        'data': [
            'views/assets.xml',
        ],

#. `debug=assets` and `--dev=xml` may come in handy
