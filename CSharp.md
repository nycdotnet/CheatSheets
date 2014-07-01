C#
==

**Declare and initialize array of specific primitive types (explicit)**

    var a = new object[] {"xyz",123,true, new DateTime(2012,01,15,2,59,01)};
    var b = new string[] {"xyz","123","true", new DateTime(2012,01,15,2,59,01).ToString()};


General .NET
------------



**string to memory stream back to string**

    //Thanks to http://stackoverflow.com/users/320/brian
    //http://stackoverflow.com/questions/78181/how-do-you-get-a-string-from-a-memorystream
    
    using (var ms = new MemoryStream()) {
        var sw = new StreamWriter(ms);
        sw.WriteLine("Hello World");
        sw.Flush();
        ms.Position = 0;
        var sr = new StreamReader(ms);
        var myStr = sr.ReadToEnd();
        Console.WriteLine(myStr);
    }
    


**simple memory stream to string using encoding**

    MemoryStream ms;
    //
    var s = Encoding.ASCII.GetString(ms.ToArray());