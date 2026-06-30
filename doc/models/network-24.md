
# Network 24

*This model accepts additional fields of type array.*

## Structure

`Network24`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | This field contains a code that identifies the network.<br>Please refer [Network ID and Sharing Group Code](<br><br>**Constraints**: *Maximum Length*: `5` | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Network24Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$network24 = Network24Builder::init()
    ->id('id8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

