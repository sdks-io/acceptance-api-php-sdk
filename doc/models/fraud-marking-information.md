
# Fraud Marking Information

*This model accepts additional fields of type array.*

## Structure

`FraudMarkingInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | Reason for adding the transaction to the negative list. This field can contain one of the following values:<br><br>- fraud_chargeback: You have received a fraudrelated chargeback for the transaction.<br>- non_fraud_chargeback: You have received a non-fraudulent chargeback for the transaction.<br>- suspected: You believe that you will probably receive a chargeback for the transaction.<br>- creditback: You issued a refund to the customer to avoid a chargeback for the transaction. | getReason(): ?string | setReason(?string reason): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\FraudMarkingInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$fraudMarkingInformation = FraudMarkingInformationBuilder::init()
    ->reason('reason0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

