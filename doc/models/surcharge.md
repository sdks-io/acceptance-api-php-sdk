
# Surcharge

*This model accepts additional fields of type array.*

## Structure

`Surcharge`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | `?string` | Optional | The surcharge amount is included in the total transaction amount but is passed in a separate field to the issuer and acquirer for tracking. The issuer can provide information about the surcharge amount to the customer.<br><br>If the amount is positive, then it is a debit for the customer.<br>If the amount is negative, then it is a credit for the customer.<br><br>**NOTE**: This field is supported only for Visa Acceptance through VisaNet (CtV) for Payouts. For CtV, the maximum string length is 8.<br><br>#### PIN debit<br><br>Surcharge amount that you are charging the customer for this transaction. If you include a surcharge amount<br>in the request, you must also include the surcharge amount in the value for `orderInformation.amountDetails.totalAmount`.<br><br>Optional field for transactions that use PIN debit credit or PIN debit purchase.<br><br>**Constraints**: *Maximum Length*: `15` | getAmount(): ?string | setAmount(?string amount): void |
| `description` | `?string` | Optional | Merchant-defined field for describing the surcharge amount. | getDescription(): ?string | setDescription(?string description): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\SurchargeBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$surcharge = SurchargeBuilder::init()
    ->amount('amount6')
    ->description('description4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

