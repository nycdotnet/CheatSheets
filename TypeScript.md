TypeScript
==========

//Declare variable of type any (implicit)

	var a;

//Declare variable of type any (explicit)

	var a: any;

	//or

	var a: any = "some value";

//Declare and initialize variables of specific primitive types

  var a: string = "test";
  var b: number = 1;
  var c: boolean = false;

//Declare and initialize array of specific primitive types (explicit)

  var a: any[] = ["a",1,false];
  var b: string[] = ["a","b","c"];
  var c: number[] = [1,2,3];
  var d: boolean[] = [true,false,true];
  
 
//Declare variable that explicitly implements an interface

	interface IMyInterface {
	    name: string;
	    length: number;
	}
	
	var a: IMyInterface = { name: "test", length: 5 };

//Declare variable of oneshot complex anonymous type (if you don't want to bother creating an interface)

  var a: { name: string; length: number; } = { name: "test", length: 5 };
