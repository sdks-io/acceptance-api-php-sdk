
# Instrument Identifier 2

*This model accepts additional fields of type array.*

## Structure

`InstrumentIdentifier2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier for the Instrument Identifier token used in the transaction.<br>When you include this value in your request, many of the fields that can be supplied for an authorization or credit<br>become optional.<br><br>**Constraints**: *Minimum Length*: `12`, *Maximum Length*: `32` | getId(): ?string | setId(?string id): void |
| `state` | `?string` | Optional | Issuers state for the card number.<br>Valid values:<br><br>- ACTIVE<br>- CLOSED : The account has been closed. | getState(): ?string | setState(?string state): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InstrumentIdentifier2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$instrumentIdentifier2 = InstrumentIdentifier2Builder::init()
    ->id('id8')
    ->state('state4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

