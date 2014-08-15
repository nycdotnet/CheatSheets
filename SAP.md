SAP
===

**Transactions**

* pa20: employee details
* se16: table query utility
* sa38: program runner
* se38: program editor
* sm37: Simple Job Selection (job history)
* smx: Job Overview (own jobs)
* pp01_disp: data explorer


**Documenting the variant used by a historical job**
  * Select a job and click "Step" button you can see the program name and the parameters field has the variant name in it.
  * On that screen Goto... Variant will show a table of the variant properties.
  * You can select the fields and use CTRL+C to copy and then paste into Excel.  If you get "Not all data has been copied to the clipboard" - just scroll down to the bottom and that will buffer all the data and then copy it.

**Tips**
* Simple Job Selection you can use * as a wildcard.
* /n ends the current session and starts a new transaction.  Such as /npa20 will kill whatever you're working on and load pa20.
* hold down control to select multiple columns before clicking sort.