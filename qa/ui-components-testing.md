# [WIP] Common UI components testing

## Text fields
- empty
- space
- space at the end of the text
- space at the beginning of the text
- double spaces
- minimum length
- maximum length
- special characters
- disabled during saving
- enabled/disabled field conditions
- desired format/regex



## Email fields
* [testing examples](https://gist.github.com/cjaoude/fd9910626629b53c4d25)
* .NET: You should not use regular expressions to validate email addresses. [article](https://stackoverflow.com/questions/201323/how-to-validate-an-email-address-using-a-regular-expression/1903368#1903368)
* https://emailregex.com/ :)


## Numeric fields
- blank or space
- positive/negative values, using `+` and `-` characters, `+4`, `+-4`
- [know your separators](https://docs.oracle.com/cd/E19455-01/806-0169/overview-9/index.html) & keep the formatting consistent
- dots, spaces & commas
- multiple decimals and commas eg. `4..4` and `4,,434.4.4`
- ([Euler's Number](https://www.mathsisfun.com/numbers/e-eulers-number.html)) eg. `4e10`, `-5E-10`, `+6e+60`
- behavior on using keyboard arrows down & up
- numbers starting with 0
- boundary value analysis
- 0 & 0.0
- string input or other incorrect data types
- number with text in front or back e.g. `$5.00`, `50+`
- `.3`
- leading 0's shouldn't make the number octal (common JS bug)
- integer/hardware overflow

## Date & calendar fields
- [know your date format](https://docs.oracle.com/cd/E41183_01/DR/Date_Format_Types.html) & keep it consistent
- min/max date or period
- how long does it take to enter the date?
- mobile: maybe native operating system components can be used (like date picker)?
- integration between date field and calendar picker

## Buttons
- double clicks - is the action repeated?
- progress indicator
- enabled/disabled button conditions

## Dropdown
- possiblity to select options
- possiblity to unselect option
- single/multi selection
- default value
- mobile: maybe native operating system components can be used?

## Popups
- ability to close popup
- action buttons follows UI guidelines
- behavior on Esc, Return keyboard button
- behavior on mobile websites - should it be a popup?

## Labels
- possiblity to copy
- translations

## Links
- how are they opened: in the same or new tab? 
- is the behavior on mobile intuitive? think of older users
- tooltips available and meaningful
- opening PDFs: are they opened in browser or downloaded?
- make sure to check the behaviour on different browsers and operating systems - it might vary a lot
- mouse pointer