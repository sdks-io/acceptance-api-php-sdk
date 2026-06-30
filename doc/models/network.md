
# Network

*This model accepts additional fields of type array.*

## Structure

`Network`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | This field contains a code that identifies the network.<br>[List of Network ID and Sharing Group Code]( | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\NetworkBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$network = NetworkBuilder::init()
    ->id('id4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

