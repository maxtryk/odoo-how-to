XPath
=====

Traverse up through parents
---------------------------

    .. code-block:: html

            <group string="Contract">
                <label for="salary_expected"/>
                <div>
                    <field name="salary_expected" class="oe_inline"/>

    .. code-block:: xml

        <xpath expr="//field[@name='salary_expected']/parent::div/parent::group" position="after">
            <group string="After Contract">
                ...
            </group>
        </xpath>
