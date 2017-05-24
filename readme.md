# .NET 101
## By Morten la Cour


## Getting started

1. Locate the *csc.exe* compiler on your machine
typically something like
```
C:\Windows\Microsoft.NET\Framework64\v4.0.30319\csc.exe
```

2. Make sure the compiler is either added to the _windows environment path_ or otherwise, so it can be executed whenever needed

Everything (almost!) is a class in .NET!!

- Even the smallest program needs to be executed inside a class
- All Assemblies (.exe) contains a _Main Method_
- Libraries (.dll) do not, and cannot execute by themself

3. Create a small text file _first.cs_

```charp
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

Compile the Assembly
```
csc.exe first.cs
```

- This should result in an output file _first.exe_ 
- Run it!

# Assemblies NEEDS a Main method

- Now try renaming your **Main** method to **Main2**
- Try to recompile
- You should receive an error with something like _does not contain a static 'Main' method_
- This is because ALL Assemblies in .NET (and what we are building here is an assembly) needs a single entry-point, which, by convention, MUST be named **Main** NO EXCEPTIONS!

# The Using statement
- Get your stuff back and working from last exercise
- Remove the **using statement** at the top of the _first.cs_ file
- Try to recompile, you should receive the following error messagge: **_The name 'Console' does not exist in the current context_**
- Why??? And how do you fix this, if you are not allowed to use any _using statements_? (Hint: _take a look at the documentation for the Console Class [MSDN on Console Class](https://msdn.microsoft.com/en-us/library/system.console(v=vs.110).aspx) and examine what namespace the class resides under_)

