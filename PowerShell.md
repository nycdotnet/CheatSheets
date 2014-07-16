PowerShell
==========
**Escape character in string**

    $myVar = "Hello, `"Steve`"";

**Shortcuts**
    % = for each, roughly = see http://bsonposh.com/archives/327
    ? = Filter

**Run a command-line EXE with complicated switches and wait for finish**
    
    $theCommand = "c:\path\MyProgram.exe"
    $theSwitches = "/param1 /param2=x"
    start-process -FilePath $theCommand -ArgumentList $theSwitches -Wait
    #Thanks: http://stackoverflow.com/questions/651223/powershell-start-process-and-cmdline-switches
    #http://technet.microsoft.com/en-us/library/hh849848.aspx


**Make PowerShell wait until an external command is done executing, but ignore the result.**

    | Out-Null


**Uninstall anything that has the text *Java* on the Add/Remove Programs list**

    Get-WmiObject -Class win32_product | ? {$_.Name -like "*Java*"} | % {msiexec /x "$($_.IdentifyingNumber)" /qn | Out-Null}
    #Thanks: http://stackoverflow.com/questions/15372140/uninstalling-java-6-and-reinstalling-java-7-using-powershell
    
**Enumerate the properties of an object

    $someObject | Get-Member | Out-String
    

**Get PowerShell version (works on PS 2 and higher)

    $PSVersionTable.PSVersion
    #Thanks http://stackoverflow.com/questions/1825585/how-to-determine-what-version-of-powershell-is-installed


