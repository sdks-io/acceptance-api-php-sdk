
# Instrument Identifier 3

*This model accepts additional fields of type array.*

## Structure

`InstrumentIdentifier3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier for the Instrument Identifier token that was created as part of a bundled TOKEN_CREATE action.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` | getId(): ?string | setId(?string id): void |
| `state` | `?string` | Optional | Issuers state for the card number.<br>Valid values:<br><br>- ACTIVE<br>- CLOSED : The account has been closed. | getState(): ?string | setState(?string state): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InstrumentIdentifier3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$instrumentIdentifier3 = InstrumentIdentifier3Builder::init()
    ->id('id8')
    ->state('state4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

