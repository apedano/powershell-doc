# powershell-doc

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




