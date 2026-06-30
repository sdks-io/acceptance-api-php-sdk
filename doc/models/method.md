
# Method

*This model accepts additional fields of type array.*

## Structure

`Method`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | A Payment Type is enabled through a Method. Examples: Visa, Master Card, ApplePay, iDeal, 7Eleven, alfamart, bofaPayByBank, payToPayByBank, etc<br><br>For Japan Payment Processing Valid Values:<br><br>- 1 Banking Data<br>- 2 Authorization Data<br><br>#### Via KCP<br><br>- `KCP` : Local Card, Bank Transfer and Carrier Billing.<br>- `PAYCO`<br>- `KAKAOPAY`<br>- `NAVERPAY` | getName(): ?string | setName(?string name): void |
| `type` | `?string` | Optional | The payment channel that facilitates the transactions. This parameter can be used if the payment channels are listed on the merchant’s site, and the payment channel is known.<br><br>Possible Values:<br><br>#### Via PPRO<br><br>- `alfaVa`<br>- `kredivo`<br>- `consumerBarCode`<br>- `merchantQrCode`<br>- `dokuWallet` | getType(): ?string | setType(?string type): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MethodBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$method = MethodBuilder::init()
    ->name('name6')
    ->type('type4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

