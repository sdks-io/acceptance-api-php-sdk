
# Amount Details 12

*This model accepts additional fields of type array.*

## Structure

`AmountDetails12`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `settlementAmount` | `?string` | Optional | This is a multicurrency field. It contains the transaction amount (field 4), converted to the Currency used to bill the cardholder’s account.<br>This field is returned for OCT transactions.<br><br>**Constraints**: *Maximum Length*: `12` | getSettlementAmount(): ?string | setSettlementAmount(?string settlementAmount): void |
| `settlementCurrency` | `?string` | Optional | This is a multicurrency-only field. It contains a 3-digit numeric code that identifies the currency used by the issuer to bill the cardholder's account.<br>This field is returned for OCT transactions.<br><br>**Constraints**: *Maximum Length*: `3` | getSettlementCurrency(): ?string | setSettlementCurrency(?string settlementCurrency): void |
| `exchangeRate` | `?string` | Optional | Exchange rate returned by the DCC service. Includes a decimal point and a maximum of 4 decimal places.<br><br>**Constraints**: *Maximum Length*: `13` | getExchangeRate(): ?string | setExchangeRate(?string exchangeRate): void |
| `foreignAmount` | `?string` | Optional | Set this field to the converted amount that was returned by the DCC provider.<br><br>**Constraints**: *Maximum Length*: `15` | getForeignAmount(): ?string | setForeignAmount(?string foreignAmount): void |
| `foreignCurrency` | `?string` | Optional | Set this field to the converted amount that was returned by the DCC provider.<br><br>**Constraints**: *Maximum Length*: `5` | getForeignCurrency(): ?string | setForeignCurrency(?string foreignCurrency): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$amountDetails12 = AmountDetails12Builder::init()
    ->settlementAmount('settlementAmount4')
    ->settlementCurrency('settlementCurrency4')
    ->exchangeRate('exchangeRate2')
    ->foreignAmount('foreignAmount4')
    ->foreignCurrency('foreignCurrency8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

