
# User Agent

The images to be used as background on Klarna’s payment page (the
image best matching the resolution will be used). This is a pass-through
field. Check Klarna’s documentation for more information about the correct
format. This value can also be set in the merchant configuration.

*This model accepts additional fields of type array.*

## Structure

`UserAgent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `url` | `?string` | Optional | Url for the image<br><br>**Constraints**: *Maximum Length*: `255` | getUrl(): ?string | setUrl(?string url): void |
| `width` | `?int` | Optional | Width of the image | getWidth(): ?int | setWidth(?int width): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\UserAgentBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$userAgent = UserAgentBuilder::init()
    ->url('url0')
    ->width(200)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

