PowerShell
==========
**Escape character in string**

````powershell
$myVar = "Hello, `"Steve`"";
````


**Shortcuts**

````
% = for each, roughly = see http://bsonposh.com/archives/327
? = Filter
````

**Run a command-line EXE with complicated switches and wait for finish**
    
````powershell
$theCommand = "c:\path\MyProgram.exe"
$theSwitches = "/param1 /param2=x"
start-process -FilePath $theCommand -ArgumentList $theSwitches -Wait
#Thanks: http://stackoverflow.com/questions/651223/powershell-start-process-and-cmdline-switches
#http://technet.microsoft.com/en-us/library/hh849848.aspx
````

**Make PowerShell wait until an external command is done executing, but ignore the result.**

````powershell
| Out-Null
````

**Uninstall anything that has the text *Java* on the Add/Remove Programs list**

````powershell
Get-WmiObject -Class win32_product | ? {$_.Name -like "*Java*"} | % {msiexec /x "$($_.IdentifyingNumber)" /qn | Out-Null}
#Thanks: http://stackoverflow.com/questions/15372140/uninstalling-java-6-and-reinstalling-java-7-using-powershell
````
    
**Enumerate the property names of an object**

````powershell
$someObject | Get-Member | Out-String
````
   
**Enumerate the property values of an object**

````powershell
$someObject | Format-List *
#see http://stackoverflow.com/questions/7259142/how-to-see-all-properties for more info.
````

**Get PowerShell version (works on PS 2 and higher)**

````powershell
$PSVersionTable.PSVersion
#Thanks http://stackoverflow.com/questions/1825585/how-to-determine-what-version-of-powershell-is-installed
````

**Pass DateTime to function**

````powershell
function Get-Ticks([DateTime] $myDateTimeParam) {
  $myDateTimeParam.Ticks
}

Get-Ticks ([DateTime]"2014-01-01");
````
     
**Filter a collection**

````powershell
# returns only the items where the OS property equals "Windows"
Get-AzureVMImage | ? {$_.OS -eq "Windows"}
````

**Format a nice wide table**

````powershell
dir | select lastaccesstime, name | Format-Table -AutoSize | Out-String -Width 4096
````

**Determine type of a variable**

````powershell
($variable).GetType().FullName
# thanks: http://techibee.com/powershell/tip-how-to-find-variable-type-in-powershell/702
````
