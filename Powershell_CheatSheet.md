# Powershell Commands 
---

PowerShell is Command Prompt on steroids.

Rather than collating information about hundreds of different servers and services manually (which would take a long time), you can simply run a script on PowerShell to automatically feed information back to you.

# Basic Commands

- **Get-Help** Used to get help with any powershell command
- **Get-ExecutionPolicy** see which policy is active on the server before running a new script.
- **Set-ExecutionPolicy** 
- **ConvertTp-HTML** allows you to build reports with tables and data 
- **Export-CSV (andGetService)** creates a CSV file compiling all of the objects you've selected
- **Select-Object** Send Specific properties to an object
- **Get-Process** view all processes currently running on the system 
- **Stop-Process** used to stop a process
- **Get-EventLog** acces your computers event logs

**Parameters you can use to search event logs** 
- **After** User specifies a date and time and the cmdlet will locate events that occurred after
- **AsBaseObject** Provides a System.Diagnostics.EventLogEntry for each event
- **AsString** Returns the output as strings
- **Before** User specifies a date and time and the cmdlet will locate events that occurred before
- **ComputerName** Used to refer to a remote computer
- **EntryType** Specifies the entry type of events (Error, Failure Audit, Success Audit, Information, Warning)
- **Index** Specifies index values the cmdlet finds events from
- **List** Provides a list of event logs
- **UserName** Specifies usernames associated with a given event

- **Get-ChildItem**	dir, ls, gci 	Lists all files and folders in the current working directory
- **Get-Location**	pwd, gl	Get the current working directory
- **Set-Location**	cd, chdir, sl	Sets the current working location to a specified location.
- **Get-Content**	cat, gc, type	Gets the content of the item at the specified location.
- **Add-Content**	ac	Adds content to the specified items, such as adding words to a file.
- **Set-Content**	sc	Writes or replaces the content in an item with new content.
- **Copy-Item**	copy, cp, cpi	Copies an item from one location to another.
- **Remove-Item**	del, erase, rd, ri, rm, rmdir	Deletes the specified items.
- **Move-Item**	mi, move, mv	Moves an item from one location to another.
- **Set-Item**	si	Changes the value of an item to the value specified in the command.
- **New-Item**	ni	Creates a new item.
- **Start-Job**	sajb	Starts a Windows PowerShell background job.
- **Compare-Object**	compare, dif	Compares two sets of objects.
- **Group-Object**	group	Groups objects that contain the same value for specified properties.
- **Invoke-WebRequest**	curl, iwr, wget	Gets content from a web page on the Internet.
- **Measure-Object**	measure	Calculates the numeric properties of objects, and the characters, words, and lines in string objects, such as files …
- **Resolve-Path**	rvpa	Resolves the wildcard characters in a path, and displays the path contents.
- **Resume-Job**	rujb	Restarts a suspended job
- **Set-Variable**	set, sv	Sets the value of a variable. Creates the variable if one with the requested name does not exist.
- **Show-Command**	shcm	Creates Windows PowerShell commands in a graphical command window.
- **Sort-Object**	sort	Sorts objects by property values.
- **Get-Service** list of all service installed on the system 
- **Start-Service**	sasv	Starts one or more stopped services.
- **Start-Process**	saps, start	Starts one or more processes on the local computer.
- **Suspend-Job**	sujb	Temporarily stops workflow jobs.
- **Wait-Job**	wjb	Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are …
- **Where-Object**	?, where	Selects objects from a collection based on their property values.
- **Write-Output**	echo, write	Sends the specified objects to the next command in the pipeline. If the command is the last command in the pipeline,…
- **Out-File**	>, >>	Send output to a file.
When you wish to specify parameters, stick to Out-File.
- **Invoke-WebRequest**	curl, iwr, wget	Get content from a web page on the Internet
- **Clear-Host** cls, clear	Clear console

**How to run PowerShell commands?**
You can run PowerShell commands from a Command Prompt window by using the format: powershell -command ” <PowerShellCode> “ but put your PowerShell command inside the quotes instead of <PowerShellCode>. If your PowerShell command requires a value in quotes, use single quotes in there instead of double-quotes. The surrounding quotes in the execution example here should remain as double-quotes.

**Parameters**
Parameters are command arguments that enable developers to build reusable PowerShell scripts. For a command with two parameters (here, Parameter1 takes a value, but Parameter2 doesn’t), the syntax is:

- Do-Something -Parameter1 value1 -Parameter2

To find all commands with, say, the “ComputerName” parameter, use:

- Get-Help * -Parameter ComputerName

*The following are risk mitigation parameters that apply to all PowerShell commands:*

RISK MITIGATION PARAMETERS
- **Confirm** Prompt whether to take action. Creating a new item called test.txt:
ni test.txt -Confirm
- **WhatIf** Displays what a certain command would do. Removal of an item called test.txt:
del test.txt -WhatIf

**Pipes**
PowerShell uses the pipe character “|” to pass the output of a series of commands to subsequent commands as pipeline input, analogous to scripting in Bash and Splunk. For a sequence containing three commands, the PowerShell pipeline syntax is:

- Command1 | Command2 | Command3

*Here is an example involving four commands:*

Get-Service | Where-Object -Property Status -EQ Running | Select-Object Name, DisplayName, StartType | Sort-Object -Property StartType, Name

**Objects**
An object is a data type that consists of object properties and methods, either of which you can reference directly with a period (.) followed by the property/method name. PowerShell contains .NET Framework objects like other OOP languages such as C#, Java, and Python.

*In the example below, we explore a Fax application .NET Framework object:*

Get-Service -Name Fax | Get-Member

**Variables**
These are the basic commands for defining and calling PowerShell variables.

- **New-Variable var1**	Create a new variable var1 without defining its value
- **Get-Variable my***	Lists all variables in use beginning with “my*”
- **Remove-Variable bad_variable** Delete the variable called “bad_variable” 
- **$var = "string"** Assign the value "string" to a variable $var
- **$a,$/b = 0** Assign the value 0 to the variables $a, $b
- **$a,$b,$c = 'a','b','c'** Assign the characters 'a', 'b', 'c' to respectively-named variables
- **$a,$b = $b,$a**	Swap the values of the variables $a and $b
- **$var = [int]5**	Force the variable $var to be strongly typed and only admit integer values

**Special Variables**

**$HOME** Path to user's home directory
**$NULL** Empty/null value
**$TRUE** Boolean value TRUE
**$FALSE** Boolean value FALSE
**$PID**Process identifier (PID) of the process hosting the current session of PowerShell

**Regular Expressions**
A regular expression (regex) is a character-matching pattern. It can comprise literal characters, operators, and other constructs.

Here are the rules for constructing regexes:

REGEX SYNTAX	DESCRIPTION
- [ ]	Allowable characters, e.g., [abcd] means 'a'/'b'/'c'/'d'
- [aeiou]	Single vowel character in English
- ^	1.Use it with square brackets [ ] to denote exclusion
    2.For matching the beginning of a string
- [^aeiou]	Single consonant character in English
- $	For matching the end of a string
- -	Use with square brackets [ ] to denote character ranges
- [A-Z]	Uppercase alphabetic characters
- [a-z]	Lowercase alphabetic characters
- [0-9]	Numeric characters
- [ -~]	All ASCII-based (hence printable) characters
- \t	Tab
- \n	Newline
- \r	Carriage return
- .	Any character except a newline (\n) character; wildcard
- *	Match the regex prefixed to it zero or more times.
- +	Match the regex prefixed to it one or more times.
- ?	Match the regex prefixed to it zero or one time.
- {n}	A regex symbol must match exactly n times. 
- {n,}	A regex symbol must match at least n times. 
- {n,m}	A regex symbol must match between n and m times inclusive.
- \	Escape; interpret the following regex-reserved characters as the corresponding literal characters: []().\^$|?*+{}
- \d	Decimal digit
- \D	Non-decimal digit, such as hexadecimal
- \w	Alphanumeric character and underscore (“word character”)
- \W	Non-word character
- \s	Space character
- \S	Non-space character

**The following syntax is for checking strings (enclosed with quotes such as 'str' or "ing") against regexes:**

CHECK FOR -MATCH	CHECK FOR -NOTMATCH
<string> -Match <regex>	<string> -NotMatch <regex>

**Operators**
PowerShell has many operators. Here we present the most commonly used ones.

In the examples below, the variables $a and $b hold the values 10 and 20, respectively. The symbol → denotes the resulting value, and ⇔ denotes equivalence.

**Arithmetic operators:**

- +	Addition. Adds values on either side of the operator.	$a + $b → 30
- -	Subtraction. Subtracts right-hand operand from the left-hand operand.	$a - $b → -10
- *	Multiplication. Multiplies values on either side of the operator.	$a * $b → 200
- /	Division. Divides left-hand operand by right-hand operand.	$b / $a → 2
- %	Modulus. Divides left-hand operand by right-hand operand and returns the remainder.	$b % $a → 0

**Comparison operators:**

OPERATOR	MATH SYMBOL (NOT POWERSHELL)	DESCRIPTION	EXAMPLE
- eq	=	Equal	$a -eq $b → $false
- ne	≠	Unequal	$a -ne $b → $true
- gt	>	Greater than	$b -gt $a → $true
- ge	≥	Greater than or equal to	$b -ge $a → $true
- lt	<	Less than	$b -lt $a → $false
- le	≤	Less than or equal to	$b -le $a → $false

**Assignment operators:**

OPERATOR	DESCRIPTION	EXAMPLE
- =	Assign values from the right-side operands to the left-hand operand.	Assign the sum of variables $a and $b to a new variable $c:
- $c = $a + $b
- +=	Add the right side operand to the left operand and assign the result to the left-hand operand.	$c += $a ⇔ $c = $c + $a
- -=	Subtract the right side operand from the left operand and assign the result to the left-hand operand.	$c -= $a ⇔ $c = $c - $a

**Logical operators:**

OPERATOR	DESCRIPTION	EXAMPLE
- -and	Logical AND. If both operands are true/non-zero, then the condition becomes true.	($a -and $b) → $true
- -or	Logical OR. If any of the two operands are true/non-zero, then the condition becomes true.	($a -or 0) → $true
- -not, !	Logical NOT. Negation of a given Boolean expression.	!($b -eq 20) → $false
- -xor	Logical exclusive OR. If only one of the two operands is true/non-zero, then the condition becomes true.	($a -xor $b) → $false
Redirection operators:

**Redirection Operators**
OPERATOR	DESCRIPTION
- >	Send output to the specified file or output device.
- >>	Append output to the specified file or output device.
- >&1	Redirects the specified stream to the standard output stream.

By adding a numerical prefix to PowerShell’s redirection operators, the redirection operators enable you to send specific types of command output to various destinations:

**REDIRECTION PREFIX	OUTPUT STREAM	EXAMPLE**
- *	All output	Redirect all streams to out.txt:
Do-Something *> out.txt
- 1	Standard output (This is the default stream if you omit the redirection prefix.)	Append standard output to success.txt:
Do-Something 1>> success.txt
- 2	Standard error	Redirect standard error to standard output, which gets sent to a file called dir.log:
dir 'C:\', 'fakepath' 2>&1 > .\dir.log
- 3	Warning messages	Send warning output to warning.txt:
Do-Something 3> warning.txt 
- 4	Verbose output	Append verbose.txt with the verbose output:
Do-Something 4>> verbose.txt 
- 5	Debug messages	Send debugging output to standard error:
Do-Something 5>&1 
- 6	Information (PowerShell 5.0+)	Suppress all informational output: 
Do-Something 6>$null

**Matching and regular expression (regex) operators:**

OPERATOR	DESCRIPTION	EXAMPLE
-Replace	Replace strings matching a regex pattern	Output “i like ! !”:

$toy = "i like this toy";
$work = $toy -Replace "toy|this","!";
$work
-Like, -NotLike	Check if a string matches a wildcard pattern (or not)	Output all *.bat files in the current working directory:
Get-ChildItem | Where-Object {$_.name  -Like "*.bat"}

Output all other files:
Get-ChildItem | Where-Object {$_.name  -NotLike "*.bat"}
-Match, -NotMatch	Check if a string matches a regex pattern (or not)	The following examples evaluate to TRUE:
'blog' -Match 'b[^aeiou][aeiuo]g'
'blog' -NotMatch 'b\d\wg'
-Contains, -NotContains	Check if a collection contains a value (or not)	The following examples evaluate to TRUE:
@("Apple","Banana","Orange") -Contains "Banana"
@("Au","Ag","Cu") -NotContains "Gold"
-In, -NotIn	Check if a value is (not) in a collection	The following examples evaluate to TRUE:
"blue" -In @("red", "green", "blue")
"blue" -NotIn @("magenta", "cyan", yellow")

**Miscellaneous operators:**

COMMAND	DESCRIPTION	EXAMPLE
()	Grouping; override operator precedence in expressions	Computing this expression gives you the value 4:
(1+1)*2
$()	Get the result of one or more statements	Get today’s date and time:
"Today is $(Get-Date)"
@()	Get the results of one or more statements in the form of arrays	Get only file names in the current working directory:
@(Get-ChildItem | Select-Object Name)
[]	Converts objects to the specific type	Check that there are 31 days between January 20 and February 20, 1988:
[DateTime] '2/20/88' - [DateTime] '1/20/88' -eq [TimeSpan] '31'# True
&	Run a command/pipeline as a Windows Powershell background job (PowerShell 6.0+)	Get-Process -Name pwsh &

**Hash Tables**
A hash table (alternative names: dictionary, associative array) stores data as key-value pairs.

SYNTAX	DESCRIPTION	EXAMPLE
@{<key> = <value>; [<key> = <value>] ...}	Hash table (empty: @{})	@{Number = 1; Shape = "Square"; Color = "Blue"}
[ordered]@{<key> = <value>; [<key> = <value>] ...}	Hash table with ordering.

Comparing unordered and ordered hash tables	[ordered]@{Number = 1; Shape = "Square"; Color = "Blue"}
$hash.<key> = <value>	Assign a value to a key in the hash table $hash 	$hash.id = 100
$hash["<key>"] = "<value>"$hash.Add("<key>", "<value>")	Add a key-value pair to $hash	$hash["Name"] = "Alice"$hash.Add("Time", "Now")
$hash.Remove(<key>)	Remove a key-value pair from $hash	$hash.Remove("Time")
$hash.<key>	Get the value of <key>	$hash.id # 100
Comments
Comments help you organize the components and flow of your PowerShell script.

SYMBOL	DESCRIPTION	EXAMPLE
#	One-line comment	# Comment
<#...#>	Multiline comment	<# Blockcomment #>
`"	Escaped quotation marks	"`"Hello`""
`t	Tab	"'hello `t world'"
`n	New line	"'hello `n world'"
`	Line continuation	ni test.txt `
-WhatIf
Flow Control
In the given examples, $a is a variable defined earlier in the PowerShell instance.

COMMAND SYNTAX	DESCRIPTION	EXAMPLE
For (<Init>; <Condition>; <Repeat>){<Statement list>}	For-loop.	Print the value of $i, initialized with the value 1 and incremented by one in each iteration, until it exceeds 10:
for($i=1; $i -le 10; $i++){Write-Host $i}
ForEach ($<Item> in $<Collection>){<Statement list>}	ForEach-Object loop; enumeration over Items in a Collection.
The alias for “ForEach” is “%”. The alias  “$_” represents the current object.	Display the file size of each file in the current working directory:
Get-ChildItem | % {Write-Host $_.length $_.name -separator "`t`t"}
While (<Condition>){<Statement list>}	While-loop.	In each iteration, increment $a by one and print its value unless/until this value becomes 3:
while($a -ne 3){
    $a++
    Write-Host $a
}
If (<Test1>) {<Statement list 1>} [ElseIf (<Test2>) {<Statement list 2>}] [Else {<Statement list 3>}]	Conditional statement.	Compares the value of $a against 2:
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
} elseif ($a -eq 2) {
    Write-Host "The value $a is equal to 2."
} else {
    Write-Host ("The value $a is less than 2 or" + " was not created or initialized.")}

**PowerShell For Administrators**

New-PSDrive –Name "L" –PSProvider FileSystem –Root "\\path\to\data" –Persist	Set up network drives. 
Specify an unused capital letter (not C:) as the “-Name” of a drive, and point the “-Root” parameter to a valid network path.
Enable-PSRemoting	Enable PowerShell remoting on a computer.
If you want to push software updates across a network, you need to enable PowerShell remoting on each computer in the network.
Invoke-Command -ComputerName pc01, pc02, pc03 -ScriptBlock{cmd /c c:\path\to\setup.exe /config C:\path\to\config.xml}	Push software updates across a network of three computers pc01, pc02, and pc03.
Here, /c refers to the C: drive, and the rest of the cmd command is the Windows Batch script for software installation on cmd.exe.
Get-Hotfix	Check for software patches/updates
$Password = Read-Host -AsSecureString
New-LocalUser "User03" -Password $Password -FullName "Third User" -Description "Description of this account."	Adding users.
The first command prompts you for a password by using the Read-Host cmdlet. The command stores the password as a secure string in the $Password variable.
The second command creates a local user account by using the password stored in $Password. The command specifies a user name, full name, and description for the user account.
While(1) { $p = get-counter '\Process(*)\% Processor Time'; cls; $p.CounterSamples | sort -des CookedValue | select -f 15 | ft -a}	Monitor running processes, refreshing at some given interval and showing CPU usage like Linux top command.
Get-ChildItem c:\data -r | % {Copy-Item -Path $_.FullName -Destination \\path\to\backup}	Creating a remote backup of the directory c:\data. To back up only modified files, sandwich the following command between the dir and Copy-Item commands as part of this pipeline:
? {!($_.PsIsContainer) -AND $_.LastWriteTime -gt (Get-Date).date} 
Get-Service	Display the running and stopped services of the computer. See a working example in Pipes.
Get-Command *-Service	List all commands with the suffix “-Service”:

Get-Process	List processes on a local computer:

Start-Sleep 10	Sleep for ten seconds
Start-Job	Start a Windows Powershell background job locally
Receive-Job	Get the results of the Windows Powershell background job
New-PSSession	Create a persistent connection to a local or remote computer
Get-PSSession	Get the Windows PowerShell sessions on local and remote computers
Enable-NetFirewallRule	Enable a previously disabled firewall rule
ConvertTo-Html	Convert Microsoft .NET Framework objects into HTML web pages
Invoke-RestMethod	Send an HTTP or HTTPS request to a RESTful web service

