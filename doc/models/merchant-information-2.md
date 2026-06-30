
# Merchant Information 2

*This model accepts additional fields of type array.*

## Structure

`MerchantInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionLocalDateTime` | `?string` | Optional | Date and time at your physical location.<br><br>Format: `YYYYMMDDhhmmss`, where:<br><br>- `YYYY` = year<br>- `MM` = month<br>- `DD` = day<br>- `hh` = hour<br>- `mm` = minutes<br>- `ss` = seconds<br><br>#### Used by<br><br>**Authorization**<br>Required for these processors:<br><br>- American Express Direct                                                                                                                                                                                                                                                                                                                         - American Express Direct<br>- Credit Mutuel-CIC<br>- FDC Nashville Global<br>- SIX<br><br>Optional for all other processors.<br><br>**Constraints**: *Maximum Length*: `14` | getTransactionLocalDateTime(): ?string | setTransactionLocalDateTime(?string transactionLocalDateTime): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInformation2 = MerchantInformation2Builder::init()
    ->transactionLocalDateTime('transactionLocalDateTime4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

