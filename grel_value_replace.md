## GREL *value.replace* cheatsheet

|	Task description |	Task starting from |	GREL Expression syntax |	Example | Explanation |
| ------------- |:-------------:| :-------------:|:-------------:| :-------------:|
Replace one character with another, where *x* is the existing value and *y* is the value being substituted |	Edit cells -> Transform	| value.replace("x", "y") |	value.replace("&", ":") |  Substituting a colon for an ampersand |
Replace several characters (*abcde*) with several others (*vwxyz*) |	Edit cells -> Transform	| value.replace("chars ", "newchars") |	value.replace("abcde", "vwxyz ") |  Replacing one string of characters with another |
|	Replace a single character (*x*) with several other characters (*vwxyz*) |	Edit cells -> Transform	| value.replace("char ", "newchars") |	value.replace("&", " and ") |  Replacing one character with a string and adding spaces around it |
|	Replace a string of characters with nothing, i.e. remove data |	Edit cells -> Transform	| value.replace("x ", "") |	value.replace("00:00 AEST", "")   | This removes time from a time and date statement |
|	Replace one character with nothing, i.e. remove a character |		Edit cells -> Transform	|	value.replace("x", "") |	 |	x is now gone |
| Remove empty space | 		Edit cells -> Transform	 | value.replace(" ", "") |  |  Removes a single space |
| Remove empty spaces | 		Edit cells -> Transform	 | value.replace("   ", "") |  |  Removes more than one space |
| Remove punctuation | 		Edit cells -> Transform	 | value.replace("-", "") |  |  Removes a hyphen |
|	 Replace content of one column with content of another |		Edit cells -> Transform	|	 cells["desired_column"].value  |  Enter this in the column you want to transform.  | You might need to filter the rows you want to transform FIRST if there is a mix of different data in the column and you only want to replace **some** of the data.  |	
|	Replace a range of values with a single value using a regular expression |		Edit cells -> Transform	|	 value.replace(/\d{4}/,"state_name") |	value.replace(/\d{4}/,"QLD") |  Replacing a range of postcodes in a column with the name of a state|	
|	Replace a specific value at the start of a string with another value using a regular expression	|	 Edit column -> Add column based on this column |		value.replace(/^04/,"+614")	|	 value.replace(/^04/,"+614") |  Adding a column to create an international version of a local mobile phone number  |	
