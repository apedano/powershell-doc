# 01 - Console help

## Command output
Pipe with 

```powershell
<command> | Select-String <search_string> -Context 2
```
If the search is from a file content:

```powershell
Get-Content <file> | Select-String <search_string> -Context 2
```
or
```powershell
gc <file> | Select-String <search_string> -Context 2
```


### GREP - `Select-String`

The `Context` is the number of lines wrapping the `search_string` 

```powershell
<command> | Select-String <search_string> -Context 2
```


### HEAD - `select`

```powershell
<command> | select -First <#_lines>
```

### TAIL - `select`

```powershell
<command> | select -Last <#_lines>
```
