# .NET 101
## By Morten la Cour

# Table of Contents
1. [Getting Started](#getting-started)
2. [Main Method](#main-method)
3. [The Using Statement](#the-using-statement)
4. [Multiple files](#multiple-files)

## Getting started

1. Locate the *csc.exe* compiler on your machine
typically something like
```
C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe
```

2. Make sure the compiler is either added to the _windows environment path_ or otherwise, so it can be executed whenever needed

Everything (almost!) is a class in .NET!!

- Even the smallest program needs to be executed inside a class
- All Executables (.exe) contains a _Main Method_
- Libraries (.dll) do not, and cannot execute by themself
- Both of them are _Assemblies_

3. Create a small text file _first.cs_

```cs
using System;

namespace Foo 
{
	public class Foo2
	{
		public static void Main() 
		{
			Console.WriteLine("It's working!");
		}
	}
}
```

Notice: The Main method MUST be inside a class! (Classname doesn't matter in this case, and the **namespace** is optional)

Compile the assembly
```
csc.exe first.cs
```

- This should result in an output file _first.exe_ 
- Run it!

[Back to top](#table-of-contents)

# Main method

- Now try renaming your **Main** method to **Main2**
- Try to recompile
- You should receive an error with something like _does not contain a static 'Main' method_
- This is because ALL executables in .NET (and what we are building here is an executable) needs a single entry-point, which, by convention, MUST be named **Main** NO EXCEPTIONS!

[Back to top](#table-of-contents)

# The Using statement
- Get your stuff back and working from last exercise
- Remove the **using statement** at the top of the _first.cs_ file
- Try to recompile, you should receive the following error messagge: **_The name 'Console' does not exist in the current context_**
- Why??? And how do you fix this, if you are not allowed to use any _using statements_? (Hint: _take a look at the documentation for the Console Class [MSDN on Console Class](https://msdn.microsoft.com/en-us/library/system.console(v=vs.110).aspx) and examine what namespace the class resides under_)

[Back to top](#table-of-contents)

# Multiple files

The main file..
```cs
??????


```

## The new file

```cs
	using System;
	namespace vertica.common
	{
	internal  class Person
	{
		private string _name; 
		public Person() 
		{
				_name = "Jane Doe";
		}
		public Person(string name) 
		{
			_name = name;
			
		}
		
		
		public void Speak(int count = 1)  //Default parameter, set to 1 if nothing is supplied
		{
			for(int i = 0; i < count; i++)
				Console.WriteLine("Hello my name is " + _name);
		}
		
	}
	}

```

[Back to top](#table-of-contents)




