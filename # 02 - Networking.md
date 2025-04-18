# 02 - Networking

## Convert call response to JSON

```
$url="https://cir-cn-devops.chp.belastingdienst.nl/api/v2.0/projects/olo-kor/repositories/$harborRepositoryName/artifacts"
    
$responseJson = Invoke-WebRequest -Uri $url -Method Get | ConvertFrom-Json

$tagsArray = $responseJson.tags

foreach($tagObj in $tagsArray) {
  $tagName = $tagObj.name
  $tagPushTime = $(Get-Date $tagObj.push_time)
}
```
