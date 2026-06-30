
# Japan Payment Options 1

*This model accepts additional fields of type array.*

## Structure

`JapanPaymentOptions1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentMethod` | `?string` | Optional | This value is a 2-digit code indicating the payment method.<br>Use Payment Method Code value that applies to the tranasction.<br><br>- 10 (One-time payment)<br>- 21, 22, 23, 24  (Bonus(one-time)payment)<br>- 61 (Installment payment)<br>- 31, 32, 33, 34  (Integrated (Bonus + Installment)payment)<br>- 80 (Revolving payment)<br><br>**Constraints**: *Maximum Length*: `2` | getPaymentMethod(): ?string | setPaymentMethod(?string paymentMethod): void |
| `installments` | `?string` | Optional | Number of Installments. | getInstallments(): ?string | setInstallments(?string installments): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\JapanPaymentOptions1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$japanPaymentOptions1 = JapanPaymentOptions1Builder::init()
    ->paymentMethod('paymentMethod8')
    ->installments('installments0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

