
# Method 12

*This model accepts additional fields of type array.*

## Structure

`Method12`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | The payment channel that facilitates the transactions. This parameter can be used if the payment channels are listed on the merchant’s site, and the payment channel is known.<br><br>Possible Values:<br><br>#### Via PPRO<br><br>- `alfaVa`<br>- `kredivo`<br>- `consumerBarCode`<br>- `merchantQrCode`<br>- `dokuWallet` | getType(): ?string | setType(?string type): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Method12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$method12 = Method12Builder::init()
    ->type('type2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

