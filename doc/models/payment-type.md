
# Payment Type

*This model accepts additional fields of type array.*

## Structure

`PaymentType`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | A Payment Type is an agreed means for a payee to receive legal tender from a payer. The way one pays for a commercial financial transaction. Examples: Card, Bank Transfer, Digital, Direct Debit.<br>Possible values:<br><br>- `CARD` (use this for a PIN debit transaction)<br>- `CHECK` (use this for all eCheck payment transactions - ECP Debit, ECP Follow-on Credit, ECP StandAlone Credit)<br>- `bankTransfer` (use for Online Bank Transafer for methods such as P24, iDeal, Estonia Bank, KCP)<br>- `localCard` (KCP Local card via Altpay)<br>- `carrierBilling` (KCP Carrier Billing via Altpay) | getName(): ?string | setName(?string name): void |
| `subTypeName` | `?string` | Optional | In case the APM supports multiple modes of initiation (e.g. Alipay via QR Code or Barcode) | getSubTypeName(): ?string | setSubTypeName(?string subTypeName): void |
| `method` | [`?Method`](../../doc/models/method.md) | Optional | - | getMethod(): ?Method | setMethod(?Method method): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentTypeBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MethodBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentType = PaymentTypeBuilder::init()
    ->name('name6')
    ->subTypeName('subTypeName0')
    ->method(
        MethodBuilder::init()
            ->name('name6')
            ->type('type4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

