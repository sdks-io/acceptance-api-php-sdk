
# Features 24

*This model accepts additional fields of type array.*

## Structure

`Features24`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountFundingSource` | `?string` | Optional | This field contains the account funding source.<br>Possible values:<br><br>- `CREDIT`<br>- `DEBIT`<br>- `PREPAID`<br>- `DEFERRED DEBIT`<br>- `CHARGE`<br><br>**Constraints**: *Maximum Length*: `20` | getAccountFundingSource(): ?string | setAccountFundingSource(?string accountFundingSource): void |
| `accountFundingSourceSubType` | `?string` | Optional | This field contains the type of prepaid card.<br>Possible values:<br><br>- `Reloadable`<br>- `Non-reloadable`<br><br>**Constraints**: *Maximum Length*: `20` | getAccountFundingSourceSubType(): ?string | setAccountFundingSourceSubType(?string accountFundingSourceSubType): void |
| `cardProduct` | `?string` | Optional | This field contains the type of issuer product.<br>Example values:<br><br>- Visa Classic<br>- Visa Signature<br>- Visa Infinite<br><br>**Constraints**: *Maximum Length*: `50` | getCardProduct(): ?string | setCardProduct(?string cardProduct): void |
| `messageType` | `?string` | Optional | This field contains the type of BIN based authentication.<br>Possible values:<br><br>- `S`: Single Message<br>- `D`: Dual Message<br><br>**Constraints**: *Maximum Length*: `1` | getMessageType(): ?string | setMessageType(?string messageType): void |
| `acceptanceLevel` | `?string` | Optional | This field contains the acceptance level of the PAN.<br>Possible values:<br><br>- `0` : Normal<br>- `1` : Monitor<br>- `2` : Refuse<br>- `3` : Not Allowed<br>- `4` : Private<br>- `5` : Test<br><br>**Constraints**: *Maximum Length*: `2` | getAcceptanceLevel(): ?string | setAcceptanceLevel(?string acceptanceLevel): void |
| `cardPlatform` | `?string` | Optional | This field contains the type of card platform.<br>Possible values:<br><br>- `BUSINESS`<br>- `CONSUMER`<br>- `COMMERCIAL`<br>- `GOVERNMENT`<br><br>**Constraints**: *Maximum Length*: `20` | getCardPlatform(): ?string | setCardPlatform(?string cardPlatform): void |
| `comboCard` | `?string` | Optional | This field indicates the type of combo card.<br>Possible values:<br><br>- 0 (Not a combo card)<br>- 1 (Credit and Prepaid Combo card)<br>- 2 (Credit and Debit Combo card)<br><br>**Constraints**: *Maximum Length*: `1` | getComboCard(): ?string | setComboCard(?string comboCard): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Features24Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$features24 = Features24Builder::init()
    ->accountFundingSource('accountFundingSource2')
    ->accountFundingSourceSubType('accountFundingSourceSubType8')
    ->cardProduct('cardProduct0')
    ->messageType('messageType6')
    ->acceptanceLevel('acceptanceLevel0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

