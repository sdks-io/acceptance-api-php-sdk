
# Initiator 1

*This model accepts additional fields of type array.*

## Structure

`Initiator1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `storedCredentialUsed` | `?bool` | Optional | Indicates to an issuing bank whether a merchant-initiated transaction came from a card that was already stored on file.<br><br>Possible values:<br><br>- **true** means the merchant-initiated transaction came from a card that was already stored on file.<br>- **false**  means the merchant-initiated transaction came from a card that was not stored on file. | getStoredCredentialUsed(): ?bool | setStoredCredentialUsed(?bool storedCredentialUsed): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Initiator1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$initiator1 = Initiator1Builder::init()
    ->storedCredentialUsed(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

