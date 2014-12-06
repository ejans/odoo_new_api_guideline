Compatibility
=============
There are some patterns worth knowing during the transition period to keep the code
base compatible with both the old and the new API.

Access old API
--------------

By default, using the new API your are going to work on ``self`` that is a new RecordSet class instance.
But the old context and model are still available using: ::

    self.pool
    self._model


How to be polite with old code base
-----------------------------------
If your code must be used by the old API code base,
it should be decorated by:

 * ``@api.returns`` to ensure adapted returned values
 * ``@api.model`` to ensure that the new signature support old API calls
