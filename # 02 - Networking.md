# 02 - Networking

## Convert call response to JSON

```
$url="https://cir-cn-devops.chp.belastingdienst.nl/api/v2.0/projects/olo-kor/repositories/$harborRepositoryName/artifacts?page=1&page_size=100&with_tag=true&with_label=false&with_scan_overview=false&with_sbom_overview=false&with_signature=false&with_immutable_status=false&with_accessory=false"
    
$responseJson = Invoke-WebRequest -Uri $url -Method Get | ConvertFrom-Json

$tagsArray = $responseJson.tags

foreach($tagObj in $tagsArray) {
  $tagName = $tagObj.name
}

```
