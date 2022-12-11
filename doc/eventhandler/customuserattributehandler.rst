.. _customuserattributehandler:

Custom User Attribute Handler Module
------------------------------------

.. index:: Custom User Attribute Handler, Handler Modules


The custom user attribute handler module allows the administrator to set or delete
custom user attributes automatically. A specific event can thus set or delete
a custom user attribute without any further intervention of the administrator
or helpdesk. To learn more about custom user attributes please check out :ref:`user_attributes`

.. Note:: This event handler can also set attributes that can't be set or deleted manually
          by the administrator or the helpdesk users.


Possible Actions
~~~~~~~~~~~~~~~~

set_custom_user_attributes
..........................

This action sets a custom user attribute on a certain event.

The action takes the options **attrkey**, **attrvalue** and **user**.

**attrkey** and **attrvalue** can take fixed values. The custom user attribute
with the name from ``attrkey`` will then be set to the value of ``attrvalue``.

With the **user** option, the custom user attribute can either be set for the acting,
logged in user or for the user on whom the administrator is acting on.

For example if a user failed to login too many times, the eventhandler can automatically
set the custom attribute `"this user has login problems"`.

delete_custom_user_attributes
.............................

This action deletes a custom user attribute on a certain event.

This event handler action takes the options **attrkey** and **user** as described above.

For example you could set a custom user attribute on the token
enrollment process, that indicates, that this is a new user and
set a custom user attribute to `"new user"`. On the first successful login this
custom user attribute could be automatically deleted using this event handler action.
