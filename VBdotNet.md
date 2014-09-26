VB.Net
======

**Declare and initialize array of specific primitive types**

    Dim arrayOfCoercedStrings = {"xyz",123,true, new DateTime(2012,01,15,2,59,01)}
    'TypeName(arrayOfCoercedStrings(1)) = "String"

    Dim arrayOfPrimitiveObjects as Object() = {"xyz",123,true, new DateTime(2012,01,15,2,59,01)}
    'TypeName(arrayOfPrimitiveObjects(1)) = "Integer"

**Find out what type something is**

    'see http://msdn.microsoft.com/en-us/library/s4zz68xc.aspx
    Dim a As String
    TypeName(a) 'returns "String"
    (TypeOf a Is String) 'evaluates to true

**Simple asynchrony with isolated tasks**

    'This assumes there are two functions that return some value
    'They can even be simple Booleans that always return true
    'You don't have to mark anything as Async with this method.
    
    Dim task1 = Task.Run(Function() DoTask1())
    Dim task2 = Task.Run(Function() DoTask2())
    Task.WaitAll({task1,task2})
    
    Debug.Print("This will only output once BOTH tasks are done.")
    Debug.Print("Task1 Result: " & task1.Result.ToString())
    Debug.Print("Task2 Result: " & task2.Result.ToString())
    
    