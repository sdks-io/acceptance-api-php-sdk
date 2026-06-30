
# E Wallet 5

*This model accepts additional fields of type array.*

## Structure

`EWallet5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Valid Values:<br><br>- CreditCard<br>- BankTransfer<br>- MobileTransfer<br>- KakaoMoney<br>- NaverPayPoint<br><br>**Constraints**: *Maximum Length*: `30` | getName(): ?string | setName(?string name): void |
| `fundingSource` | `?string` | Optional | Valid Values:<br><br>- PAYCO<br>- Kakaopay<br>- NaverPay<br>- SSG Pay<br>- L.Pay<br>- Apple Pay<br>- TOSS Pay<br>- Samsung Pay<br><br>**Constraints**: *Maximum Length*: `30` | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$eWallet5 = EWallet5Builder::init()
    ->name('name8')
    ->fundingSource('fundingSource8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

