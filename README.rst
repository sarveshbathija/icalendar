==========================================================
Internet Calendaring and Scheduling (iCalendar) for Python
==========================================================

The `icalendar`_ package is a parser/generator of iCalendar files for use
with Python.

----

    :Homepage: http://icalendar.readthedocs.org
    :Code: http://github.com/collective/icalendar
    :Mailing list: http://github.com/collective/icalendar/issues
    :Dependencies: `setuptools`_ and since version 3.0 we depend on `pytz`_.
    :Tested with: Python 2.4 - 2.7
    :License: `BSD`_

----


Changes in version 3.0
======================

API Change
----------

Since version we unified to icalendar de/serialization API to use only to_ical
(for writing an ical string from the internal representation) and from_ical
(for parsing an ical string into the internal representation).

to_ical is now used instead of the methods ical, string, as_string and instead
of string casting via __str__ and str.

from_ical is now used instead of from_string.

This change is a requirement for future Python 3 compatibility. Please update
your code to reflect to the new API.

Timezone support
----------------

Timezones are now fully supported in icalendar for serialization and
deserialization. We use the pytz library for timezone components of datetime
instances. The timezone identifiers must be valid pytz respectively Olson
database timezone identifiers. This can be a problem for 'GMT' identifiers,
which are not defined in the Olson database.

Instead of the own UTC tzinfo implementation we use pytz UTC tzinfo object now.


About this fork which is not a fork anymore
===========================================

Aim of this fork (not fork anymore, read further) was to bring this package up
to date with latest icalendar `RFC`_ specification as part of
`plone.app.event`_ project which goal is to bring recurrent evens to `Plone`_.

After some thoughts we (Plone developers involved with `plone.app.event`_) send
a suggestion to icalendar-dev@codespeak.net to take over mainaining of
`icalendar`_. Nobody object and since version 2.2 we are back to development.

.. _`icalendar`: http://pypi.python.org/pypi/icalendar
.. _`plone.app.event`: http://github.com/collective/plone.app.event
.. _`Plone`: http://plone.org
.. _`pytz`: http://pypi.python.org/pypi/pytz
.. _`setuptools`: http://pypi.python.org/pypi/setuptools
.. _`RFC`: http://www.ietf.org/rfc/rfc5545.txt
.. _`BSD`: https://github.com/collective/icalendar/issues/2


Test Coverage Report
====================

Output from coverage test::

    lines   cov%   module   (path)
       13   100%   icalendar.__init__
      227    91%   icalendar.cal
       48    91%   icalendar.caselessdict
      166    92%   icalendar.parser
      667    90%   icalendar.prop
       16   100%   icalendar.tests.test_cases
       25    96%   icalendar.tests.test_doctests
       47   100%   icalendar.tests.test_encoding
       44    34%   icalendar.tests.test_icalendar
       13   100%   icalendar.tests.test_property_params
       51   100%   icalendar.tests.test_timezoned
       53    30%   icalendar.tools

