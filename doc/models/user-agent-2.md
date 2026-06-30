
# User Agent 2

*This model accepts additional fields of type array.*

## Structure

`UserAgent2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `url` | `?string` | Optional | Url for the image<br><br>**Constraints**: *Maximum Length*: `255` | getUrl(): ?string | setUrl(?string url): void |
| `width` | `?int` | Optional | Width of the image | getWidth(): ?int | setWidth(?int width): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\UserAgent2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$userAgent2 = UserAgent2Builder::init()
    ->url('url0')
    ->width(130)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

