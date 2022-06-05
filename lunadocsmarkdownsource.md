# Luna | Documentation
###### *By Sectly_playz, and Q_uezy*

------------

Luna is a fast and powerful mock-up language written by Sectly_playz and Q_uezy, 
in order to make fast operations and a organized script within **Roblox Studio**
This is the only documentation available on the internet about that.

###### *If you need help in anything, make sure to contact us. You can find our contact later on.*  If you are a Package-Developer and you want to make your package public, make sure to contact us too. We will help you with this!

#### DOCUMENTATION SECTIONS

###### SYMBOLS
* &times; = **DEPRECATED/REMOVED,**
* &deg; = **EXPLAINED LATER**

###### SECTIONS

* Packages
 * Lists
 * Multitasks (Co-routines/Side routines)
* Build-In Functions
 * User Interfaces&deg;
* Datacaches
* User Interfaces
* Package Programming


> 

## Packages

Packages are addons that are published to the PackagesFolder within the Luna System.
They add more features to Luna, or just bring new system to them.

Here are a few listed, already done and published by Package Creators (officially)

### **.Sys(package_name)**

Returns the **package** with the name.

**EXAMPLE**
```lua
local package = luna.sys("package_name")

package.print = "manage_this_package"
print(package.print)
```
**OUTPUT**
```console
"manage_this_package"
```

> 

### Build-In Packages

<!-- tabs:start -->

#### **CONSOLE**

Manages the **console**. 

###### .Out(out, name)

Print something to the **console**. (Adds it to a log list)

**EXAMPLE**
```lua
local console = luna.Sys("console")

console.out("This is a test.", "log")
```

**OUTPUT**
```console
"This is a test."
```

##### .Warn(warn, name)

Warns in the **console**.

**EXAMPLE**
```lua
local console = luna.Sys("console")

console.warn("This is a warning", "log")
```

**OUTPUT**
```Console
<!WARNING> "This is a warning."
```

##### .Error(error, name)

Shows a red colored error text in the roblox console.

```lua
local console = luna.Sys("console")

console.Error("Hello", "log")
```

```console
<!ERROR> Hello
```

##### .Log(logName)

**returns** the log with the given log name.

##### .Logs()

**returns** all logs.

#####  .ClearLog(logName)

**clears** the log with the given log name.

##### .ClearLogs()

**clears** all logs.

### **LIST**

Returns a **list** of the required **list-name**

**EXAMPLE**
```lua
local list = luna.Sys("List") --// Gets the list 
local abc = list.Get("abc") --// returns the abc (A to Z)

print(abc)
```

**OUTPUT**
```Console
{"A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U",
"V", "W", "X", "Y", "Z"} --// if open. OR
{ARRAY} --// if closed.
```

<!-- tabs:end -->

## Build-In Functions

### ./:Times(number, callback)

Repeats the function **callback** as many times as the **number** variable was set.

**EXAMPLE**
```lua
luna.Times(12, function()
--// do_what_you_want 
end)
--// This will run the function 12 times.
```

### ./:Bucket(callback)

Bucket **catches** the error. It returns a **BucketId** which can be used to **CheckBucket** it,
and see what error occured.

**EXAMPLE**
```lua
local LunaModule = require(script.Parent.LunaLoader):Luna() -- // Create new luna instance for the script

LunaModule:Bucket(function(BucketId) --// Bucket is a function to help handle errors | (bucket can "catch" the error just like JavaScript's :catch() function, Its lua's pcall but better)
	--// Run script if it errors you can get the error message with the BucketId

    print("CoolScript.lua") --//Script to run if it errors bucket can be used so the script won't stop working

    if BucketId and BucketId ~= nil then
        warn(LunaModule:CheckBucket(BucketId).Error) --// Get error message

        warn(LunaModule:CheckBucket(BucketId).Successful) --// Get successful message

        LunaModule:RemoveBucket(BucketId) --// Delete the bucket error and successful message

        LunaModule:EmptyBucket() --// Delete all bucket error and successful message(s) saved on the luna instance
    end
end)
```

### ./:Call(callback)

**Calls** a function and returns the output.

### ./:RandomAr(Min, Max)

Returns a random value between **Min** and **Max**

**EXAMPLE**
```lua
local randomBetween0And12 = luna.randomAr(0, 12)
print("Random: "..randomBetween0And12)
```

**OUTPUT**
```console
Random: RANDOM_NUMBER_RETURNED
```
