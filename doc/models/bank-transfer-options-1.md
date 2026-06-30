
# Bank Transfer Options 1

*This model accepts additional fields of type array.*

## Structure

`BankTransferOptions1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `settlementMethod` | `?string` | Optional | Method used for settlement.<br><br>Possible values:<br><br>- `A`: Automated Clearing House (default for credits and for transactions using Canadian dollars)<br>- `F`: Facsimile draft (U.S. dollars only)<br>- `B`: Best possible (U.S. dollars only) (default if the field has not already been configured for your<br>  merchant ID)<br><br>**Constraints**: *Maximum Length*: `1` | getSettlementMethod(): ?string | setSettlementMethod(?string settlementMethod): void |
| `fraudScreeningLevel` | `?string` | Optional | Level of fraud screening.<br><br>Possible values:<br><br>- `1`: Validation — default if the field has not already been configured for your merchant ID<br>- `2`: Verification<br><br>**Constraints**: *Maximum Length*: `1` | getFraudScreeningLevel(): ?string | setFraudScreeningLevel(?string fraudScreeningLevel): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BankTransferOptions1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bankTransferOptions1 = BankTransferOptions1Builder::init()
    ->settlementMethod('settlementMethod8')
    ->fraudScreeningLevel('fraudScreeningLevel4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

