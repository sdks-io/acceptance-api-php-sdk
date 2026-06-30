
# Embedded Actions 1

*This model accepts additional fields of type array.*

## Structure

`EmbeddedActions1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `apCapture` | [`?ApCapture`](../../doc/models/ap-capture.md) | Optional | - | getApCapture(): ?ApCapture | setApCapture(?ApCapture apCapture): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EmbeddedActions1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ApCaptureBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$embeddedActions1 = EmbeddedActions1Builder::init()
    ->apCapture(
        ApCaptureBuilder::init()
            ->reason('reason2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

