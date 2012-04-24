# Userpoints Decimal

This is a supporting module for Userpoints that allows you to set global decimal settings for your userpoints:

* The number of decimal places
* The thousands separator
* The decimal separator

The values stored for userpoints are still integers, to avoid rounding error problems with floats. (See: http://php.net/manual/en/language.types.float.php) A theme function, userpoints_points, now wraps all displays of point values, and this module modifies the value displayed based on the settings above.

In the administrative points form, this module expects the decimal value and will transform it into the integer value stored in the database. If you enter "1.25", the value will be stored (assuming the default settings) as 125. Currently, the value is trimmed, not rounded, so if you entered "1.259" the value stored would still be 125, not 126.

If you make use of the Userpoints API, you shouldn't use decimals! The entire point of this approach is to avoid problems with floats, so it makes sense to always use integers internally. I agree that it's not ideal to use a different value internally than what's displayed to the user, but that's just a result of PHP lacking a decimal value. 
