Action and View
===============

#. Get an action window ID (`action_library_book`) from :doc:`menu_and_action`
#. Use any of the options:

* Implicitly attach view to action - via target model

    .. code-block:: xml

        <record id="view_form_book" model="ir.ui.view">
            <field name="name">Book Form</field>
            <field name="model">library.book</field>
            <field name="arch" type="xml">
                <form string="Book">
                ...


* Explicitly - via record in `ir.actions.act_window.view` referencing view ID

    .. code-block:: xml

        <record id="library_book_form"model="ir.actions.act_window.view">
            <field name="act_window_id" ref="action_library_book"/>
            <field name="view_id" ref="view_form_book" />
            <field name="view_mode">form</field>
            <field name="sequence" eval="1"/>
        </record>


* Explicitly - right in the action declaration via `context` field referencing view ID

    .. code-block:: xml

        <record id='action_all_customers'model='ir.actions.act_window'>
            <field name="name">All customers</field>
            <field name="res_model">res.partner</field>
            <field name="view_mode">tree,form</field>
            <field name="context">{'form_view_ref': 'library.view_form_book'}</field>
        </record>
