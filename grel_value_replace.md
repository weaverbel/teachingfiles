## GREL *value.replace* cheatsheet

|	Task description |	Task starting from |	GREL Expression syntax |	Example | Explanation |
| ------------- |:-------------:| :-------------:|:-------------:| :-------------:|
Replace one character with another, where *x* is the existing value and *y* is the value being substituted |	Edit cells -> Transform	| value.replace("x", "y") |	value.replace("&", ":") |  Substituting a colon for an ampersand |
Replace several characters (*abcde*) with several others (*vwxyz*) |	Edit cells -> Transform	| value.replace("chars", "newchars") |	value.replace("abcde", "vwxyz") |  Replacing one string of characters with another |
|	Replace a single character (*x*) with several other characters (*vwxyz*) |	Edit cells -> Transform	| value.replace("char", "newchars") |	value.replace("&", "and") |  Replacing one character with a string |
|	Replace a string of characters with nothing, i.e. remove data |	Edit cells -> Transform	| value.replace("*x*", "") |	value.replace("00:00 AEST", "")   | This removes time from a time and date statement |
|	Remove punctuation |		Edit cells -> Transform	|	value.replace("*x*", "") | value.replace("-", "") |  Removes a hyphen |
|	Remove space  |		Edit cells -> Transform	|	value.replace("*x*", "") | value.replace(" ", "") |  Removes a single space |
| Remove more than one space | 		Edit cells -> Transform	 | value.replace("*xxx*", "") | value.replace("&nbsp;&nbsp;&nbsp;", "")  |  Removes more than three spaces |
| Remove spaces using a regular expression | 		Edit cells -> Transform	 | value.replace(/_regular expression_/, "") | value.replace(/\s+/, "")  |  Removes any number of spaces |
|	 Replace content of one column with content of another |		Edit cells -> Transform	|	 cells["desired_column"].value  |  Enter this for the column you want to transform.  | If there is a mix of data in the column, filter rows you want to transform **FIRST** to avoid overwriting data you want to keep.  |	
|	Replace a range of values with a single value using a regular expression |		Edit cells -> Transform	|	 value.replace(/_regular expression_/,"newchars") |	value.replace(/\d{4}/,"QLD") |  Replacing a range of four-digit postcodes in a column with the abbreviation for a state |	
|	Replace a specific value at the start of a string with another value using a regular expression	|	 Edit column -> Add column based on this column |		value.replace(/_regular expression_/,"newchars")	|	 value.replace(/^04/,"+614") |  Adding a new column to create an international version of a local Australian mobile phone number  |	
