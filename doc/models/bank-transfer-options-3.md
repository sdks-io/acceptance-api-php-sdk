
# Bank Transfer Options 3

*This model accepts additional fields of type array.*

## Structure

`BankTransferOptions3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `settlementMethod` | `?string` | Optional | Method used for settlement.<br><br>Possible values:<br><br>- `A`: Automated Clearing House (default for credits and for transactions using Canadian dollars)<br>- `F`: Facsimile draft (U.S. dollars only)<br>- `B`: Best possible (U.S. dollars only) (default if the field has not already been configured for your<br>  merchant ID)<br><br>**Constraints**: *Maximum Length*: `1` | getSettlementMethod(): ?string | setSettlementMethod(?string settlementMethod): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BankTransferOptions3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bankTransferOptions3 = BankTransferOptions3Builder::init()
    ->settlementMethod('settlementMethod8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

