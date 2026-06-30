
# Payment Type 13

*This model accepts additional fields of type array.*

## Structure

`PaymentType13`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `method` | [`?Method13`](../../doc/models/method-13.md) | Optional | - | getMethod(): ?Method13 | setMethod(?Method13 method): void |
| `name` | `?string` | Optional | A Payment Type is an agreed means for a payee to receive legal tender from a payer. The way one pays for a commercial financial transaction. Examples: Card, Bank Transfer, Digital, Direct Debit.<br>Possible values:<br><br>- `EWALLET`<br>- `directDebitSepa`<br>- `directDebitBacs`<br><br>#### SEPA/BACS<br><br>Required for mandates services<br><br>#### Paypal<br><br>Required for billing agreements | getName(): ?string | setName(?string name): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType13Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentType13 = PaymentType13Builder::init()
    ->method(
        Method13Builder::init()
            ->name('name6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->name('name0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

