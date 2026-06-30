
# Merchant Initiated Transaction 1

*This model accepts additional fields of type array.*

## Structure

`MerchantInitiatedTransaction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `previousTransactionId` | `?string` | Optional | Network transaction identifier that was returned in the payment response field _processorInformation.transactionID_<br>in the reply message for either the original merchant-initiated payment in the series or the previous<br>merchant-initiated payment in the series.<br><br>**Constraints**: *Maximum Length*: `15` | getPreviousTransactionId(): ?string | setPreviousTransactionId(?string previousTransactionId): void |
| `originalAuthorizedAmount` | `?string` | Optional | Amount of the original authorization.<br><br>**Constraints**: *Maximum Length*: `15` | getOriginalAuthorizedAmount(): ?string | setOriginalAuthorizedAmount(?string originalAuthorizedAmount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInitiatedTransaction1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInitiatedTransaction1 = MerchantInitiatedTransaction1Builder::init()
    ->previousTransactionId('previousTransactionId2')
    ->originalAuthorizedAmount('originalAuthorizedAmount6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

