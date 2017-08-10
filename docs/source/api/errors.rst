.. _errors:

Errors
======

Overview
--------

Every function in the JanICE *C* API returns an error code when
executed. In the case of successful application JANICE\_SUCCESS is
returned, otherwise a code indicating the specific issue is returned.
The error codes are enumerated using the :ref:`JaniceError` type.

Enumerations
------------

.. _JaniceError:

JaniceError
~~~~~~~~~~~

The error codes defined in the JanICE *C* API

+------------------------------------+-----------------------------------------+
| Code                               | Description                             |
+====================================+=========================================+
| JANICE\_SUCCESS                    | No error                                |
+------------------------------------+-----------------------------------------+
| JANICE\_UNKNOWN\_ERROR             | Catch all error code                    |
+------------------------------------+-----------------------------------------+
| JANICE\_OUT\_OF\_MEMORY            | Out of memory error                     |
+------------------------------------+-----------------------------------------+
| JANICE\_INVALID\_SDK\_PATH         | Invalid SDK location                    |
+------------------------------------+-----------------------------------------+
| JANICE\_BAD\_SDK\_CONFIG           | Invalid SDK configuration               |
+------------------------------------+-----------------------------------------+
| JANICE\_BAD\_LICENSE               | Incorrect license file                  |
+------------------------------------+-----------------------------------------+
| JANICE\_MISSING\_DATA              | Missing SDK data                        |
+------------------------------------+-----------------------------------------+
| JANICE\_INVALID\_GPU               | The GPU is not functioning              |
+------------------------------------+-----------------------------------------+
| JANICE\_OPEN\_ERROR                | Failed to open a file                   |
+------------------------------------+-----------------------------------------+
| JANICE\_READ\_ERROR                | Failed to read from a file              |
+------------------------------------+-----------------------------------------+
| JANICE\_WRITE\_ERROR               | Failed to write to a file               |
+------------------------------------+-----------------------------------------+
| JANICE\_PARSE\_ERROR               | Failed to parse a file                  |
+------------------------------------+-----------------------------------------+
| JANICE\_INVALID\_MEDIA             | Failed to decode a media file           |
+------------------------------------+-----------------------------------------+
| JANICE\_DUPLICATE\_ID              | Template id already exists in a gallery |
+------------------------------------+-----------------------------------------+
| JANICE\_MISSING\_ID                | Template id can't be found              |
+------------------------------------+-----------------------------------------+
| JANICE\_MISSING\_FILE\_NAME        | An expected file name is not given      |
+------------------------------------+-----------------------------------------+
| JANICE\_INCORRECT\_ROLE            | Incorrect template role                 |
+------------------------------------+-----------------------------------------+
| JANICE\_FAILURE\_TO\_ENROLL        | Could not construct a template          |
+------------------------------------+-----------------------------------------+
| JANICE\_FAILURE\_TO\_SERIALIZE     | Could not serialize a data structure    |
+------------------------------------+-----------------------------------------+
| JANICE\_FAILURE\_TO\_DESERIALIZE   | Could not deserialize a data structure  |
+------------------------------------+-----------------------------------------+
| JANICE\_NOT\_IMPLEMENTED           | Optional function return                |
+------------------------------------+-----------------------------------------+
| JANICE\_NUM\_ERRORS                | Utility to iterate over all errors      |
+------------------------------------+-----------------------------------------+

Functions
---------

.. _janice_error_to_string:

janice\_error\_to\_string
~~~~~~~~~~~~~~~~~~~~~~~~~

Convert a :ref:`JaniceError` into a string for printing.

Signature
^^^^^^^^^

::

    JANICE_EXPORT const char* janice_error_to_string(JaniceError error);

Thread Safety
^^^^^^^^^^^^^

This function is thread safe.

Parameters
^^^^^^^^^^

+---------+--------------------+-----------------+
| Name    | Type               | Description     |
+=========+====================+=================+
| error   | :ref:`JaniceError` | An error code   |
+---------+--------------------+-----------------+

Return Value
^^^^^^^^^^^^

This is the only function in the API that does not return
:ref:`JaniceError`. It returns const char\* which is
a null-terminated list of characters that describe the input error.