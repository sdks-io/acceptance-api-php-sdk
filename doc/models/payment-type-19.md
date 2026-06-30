
# Payment Type 19

*This model accepts additional fields of type array.*

## Structure

`PaymentType19`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | A Payment Type is an agreed means for a payee to receive legal tender from a payer. The way one pays for a commercial financial transaction. Examples: Card, Bank Transfer, Digital, Direct Debit.<br>Possible values:<br><br>- `CARD` (use this for a PIN debit transaction)<br>- `CHECK` (use this for all eCheck payment transactions - ECP Debit, ECP Follow-on Credit, ECP StandAlone Credit)<br>- `bankTransfer` (use for Online Bank Transafer for methods such as P24, iDeal, Estonia Bank, KCP)<br>- `localCard` (KCP Local card via Altpay)<br>- `carrierBilling` (KCP Carrier Billing via Altpay) | getName(): ?string | setName(?string name): void |
| `method` | [`?Method19`](../../doc/models/method-19.md) | Optional | - | getMethod(): ?Method19 | setMethod(?Method19 method): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType19Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method19Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentType19 = PaymentType19Builder::init()
    ->name('name6')
    ->method(
        Method19Builder::init()
            ->name('name6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

