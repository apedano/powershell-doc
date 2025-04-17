# powershell-doc

## Boolean operations
```
$condition1 = $true
$condition2 = $false

$condition1 -and $condition2 # -> $false
$condition1 -or $condition2 # -> $false
$condition1 -xor $condition2 # -> $true (TRUE if exactly only one is TRUE, otherwise is FALSE)

! $condition2 # -> $true 
-not $condition2 # -> $true 
```



## Comparisons
https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7.5
### Equality

* `-eq`, `-ieq`, `-ceq` - equals
* `-ne`, `-ine`, `-cne` - not equals
* `-gt`, `-igt`, `-cgt` - greater than
* `-ge`, `-ige`, `-cge` - greater than or equal
* `-lt`, `-ilt`, `-clt` - less than
* `-le`, `-ile`, `-cle` - less than or equal

### Matching

* `-like`, `-ilike`, `-clike` - string matches wildcard pattern
* `-notlike`, `-inotlike`, `-cnotlike` - string doesn't match wildcard pattern
* `-match`, `-imatch`, `-cmatch` - string matches regex pattern
* `-notmatch`, `-inotmatch`, `-cnotmatch` - string doesn't match regex pattern
```
$contentType -like "*application/json"
```

### Replacement

* `-replace`, `-ireplace`, `-creplace` - replaces strings matching a regex pattern

```
"book" -ireplace "B", "C" # Case insensitive
"book" -creplace "B", "C" # Case-sensitive; hence, nothing to replace
```

### Containment

* `-contains`, `-icontains`, `-ccontains` - collection contains a value
* `-notcontains`, `-inotcontains`, `-cnotcontains` - collection doesn't contain a value
* `-in`, `-iin`, `-cin` - value is in a collection
* `-notin`, `-inotin`, `-cnotin` - value isn't in a collection

### Type

* `-is` - both objects are the same type
* `-isnot` - the objects aren't the same type

## Flow control

### IF
```
if(<condition>) {
  ...
} else {
  ...
}
```

### FOREACH

```
$myArray@("one", "two", "three")
foreach($el in $myArray) {
  Write-Host $el
}
```

#### Filter an array with `where`
```
$validTagsArray = $tagsArray | where{$_.name -like "$harborRepositoryName*" }
```








## Collections

### List
Initialization
```
$list = New-Object Collections.Generic.List[String]

$list.add("Value")
```

### Hashtables

Equivalent of a key value map or a dictionary

Initialization
```
#Method 1 with semicolon
$myMap = @{ Name = "Alice"; Age=4; City="Nuenen" }

#Method 2 with newlines
$myMap = @{
  Name = "Alice"
  Age=4
  City="Nuenen"
}

#Empty hashtable
$myMap = @{}
```
Operations 
```
#Accessing values
$($myMap.Name)
$($myMap["Age"])
$myKey = "City"
$myMap[$myKey]

Write-Host "Keys of the map: $($myMap.Keys -Join ', ')"
Write-Host "Values of the map: $($myMap.Values -Join ', ')"

foreach($entry in $myMap.GetEnumerator()) {
  Write-Host "Key: $($entry.Key) Value: $($entry.Value)"
}

#Adding/modifying
$myMap.Occupation = "Student"
$myMap.Age = 5 # update

#Remove
$myMap.Remove("Name")

#Existence check
$myMap.ContainsKey("Name")



```





## Print to console

## Type of output

```
Write-Host ... [ -ForegroundColor "Yellow"]
Write-Warning ...
Write-Error ... 
```

### Print all object properties

```
Write-Host ($obj | Format-Table | Out-String)
```

```
Write-Host ($obj | Format-List | Out-String)
```




