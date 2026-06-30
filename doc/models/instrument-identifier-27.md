
# Instrument Identifier 27

*This model accepts additional fields of type array.*

## Structure

`InstrumentIdentifier27`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier for the Instrument Identifier token that was created as part of a bundled TOKEN_CREATE action.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InstrumentIdentifier27Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$instrumentIdentifier27 = InstrumentIdentifier27Builder::init()
    ->id('id4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

