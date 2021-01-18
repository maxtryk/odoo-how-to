Button to Open View
===================

#. have a button (e.g. in form `header`, list field):

    .. code-block:: xml

        <button name="open_book"
                type="object"
                string="Open Book"
                context="{'book_id': 2}"/>

#. have a method in model named after the button's `name`:

    .. code-block:: python

        def open_book(self):
            return {
                'name': 'Book',
                'view_mode': 'form',
                'view_id': self.env.ref('library.view_form_book').id,
                'res_model': 'library.book',
                'type': 'ir.actions.act_window',
                'target': 'current',
                'res_id': self.env.context['book_id'],
            }
