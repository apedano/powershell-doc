# powershell-doc

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




