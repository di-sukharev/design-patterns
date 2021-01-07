# Encapsulation

Encapsulation doesn't allow to change object values externally like `object.field = -1`.
Violating the encapsulation principle leads to behaviours when one object does the work for the other. This couples classes and makes code maintaining difficult.

Encapsulation principle provides getter and setter methods for field values if any is expected.

Encapsulated values can be validated in setters before assigning to a variable.
