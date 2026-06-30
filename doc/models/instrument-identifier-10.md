
# Instrument Identifier 10

*This model accepts additional fields of type array.*

## Structure

`InstrumentIdentifier10`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The Id of the Instrument Identifier linked to the Payment Instrument.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InstrumentIdentifier10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$instrumentIdentifier10 = InstrumentIdentifier10Builder::init()
    ->id('id6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

