
# Payment Type 22

*This model accepts additional fields of type array.*

## Structure

`PaymentType22`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | A Payment Type is an agreed means for a payee to receive legal tender from a payer. The way one pays for a commercial financial transaction. Examples: Card, Bank Transfer, Digital, Direct Debit.<br>Possible values:<br><br>- `CARD` (use this for a PIN debit transaction)<br>- `CHECK` (use this for all eCheck payment transactions - ECP Debit, ECP Follow-on Credit, ECP StandAlone Credit)<br>- `bankTransfer` (use for Online Bank Transafer for methods such as P24, iDeal, Estonia Bank, KCP)<br>- `localCard` (KCP Local card via Altpay)<br>- `carrierBilling` (KCP Carrier Billing via Altpay) | getName(): ?string | setName(?string name): void |
| `type` | `?string` | Optional | Indicates the payment type used in this payment transaction. Example: credit card, check | getType(): ?string | setType(?string type): void |
| `method` | `?string` | Optional | Indicates the payment method used in this payment transaction. | getMethod(): ?string | setMethod(?string method): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType22Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentType22 = PaymentType22Builder::init()
    ->name('name2')
    ->type('type8')
    ->method('method4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

