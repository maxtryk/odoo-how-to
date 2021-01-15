Migrations
=============

#. bump up addon version in manifest (e.g. `12.0.0.1` -> `12.0.0.2`)
#. have files under addon root `migrations/12.0.0.2/`:
    * `pre-<relevant_name>.py` for pre-upgrade actions
    * `post-<relevant_name>.py` for post-upgrade actions
#. have `migrate` function in files:

    .. code-block:: python

        from odoo import api, SUPERUSER_ID

        def migrate(cr, version):
            env = api.Environment(cr, SUPERUSER_ID, {})

#. to re-test the migration, revert `ir_module_module.latest_version` to an earlier one.


.. seealso:: page 217 of the `Odoo-12 development cookbook. Third edition.`
