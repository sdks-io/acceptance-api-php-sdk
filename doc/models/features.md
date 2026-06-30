
# Features

*This model accepts additional fields of type array.*

## Structure

`Features`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountFundingSource` | `?string` | Optional | This field contains the account funding source.<br>Possible values:<br><br>- `CREDIT`<br>- `DEBIT`<br>- `PREPAID`<br>- `DEFERRED DEBIT`<br>- `CHARGE`<br><br>**Constraints**: *Maximum Length*: `20` | getAccountFundingSource(): ?string | setAccountFundingSource(?string accountFundingSource): void |
| `accountFundingSourceSubType` | `?string` | Optional | This field contains the type of prepaid card.<br>Possible values:<br><br>- `Reloadable`<br>- `Non-reloadable`<br><br>**Constraints**: *Maximum Length*: `20` | getAccountFundingSourceSubType(): ?string | setAccountFundingSourceSubType(?string accountFundingSourceSubType): void |
| `cardProduct` | `?string` | Optional | This field contains the type of issuer product.<br>Example values:<br><br>- Visa Classic<br>- Visa Signature<br>- Visa Infinite<br><br>**Constraints**: *Maximum Length*: `50` | getCardProduct(): ?string | setCardProduct(?string cardProduct): void |
| `messageType` | `?string` | Optional | This field contains the type of BIN based authentication.<br>Possible values:<br><br>- `S`: Single Message<br>- `D`: Dual Message<br><br>**Constraints**: *Maximum Length*: `1` | getMessageType(): ?string | setMessageType(?string messageType): void |
| `acceptanceLevel` | `?string` | Optional | This field contains the acceptance level of the PAN.<br>Possible values:<br><br>- `0` : Normal<br>- `1` : Monitor<br>- `2` : Refuse<br>- `3` : Not Allowed<br>- `4` : Private<br>- `5` : Test<br><br>**Constraints**: *Maximum Length*: `2` | getAcceptanceLevel(): ?string | setAcceptanceLevel(?string acceptanceLevel): void |
| `cardPlatform` | `?string` | Optional | This field contains the type of card platform.<br>Possible values:<br><br>- `BUSINESS`<br>- `CONSUMER`<br>- `CORPORATE`<br>- `COMMERCIAL`<br>- `GOVERNMENT`<br><br>**Constraints**: *Maximum Length*: `20` | getCardPlatform(): ?string | setCardPlatform(?string cardPlatform): void |
| `comboCard` | `?string` | Optional | This field indicates the type of combo card.<br>Possible values:<br><br>- 0 (Not a combo card)<br>- 1 (Credit and Prepaid Combo card)<br>- 2 (Credit and Debit Combo card)<br>- 3 (Prepaid Credit and Prepaid Debit combo card)<br><br>**Constraints**: *Maximum Length*: `1` | getComboCard(): ?string | setComboCard(?string comboCard): void |
| `corporatePurchase` | `?bool` | Optional | This field indicates if the instrument can be used for corporate purchasing. This field is only applicable for American Express cards.<br>Possible values:<br><br>- `true`<br>- `false` | getCorporatePurchase(): ?bool | setCorporatePurchase(?bool corporatePurchase): void |
| `healthCard` | `?bool` | Optional | This field indicates if the BIN is for healthcare (HSA/FSA). Currently, this field is only supported for Visa BINs.<br>Possible values:<br><br>- `true`<br>- `false` | getHealthCard(): ?bool | setHealthCard(?bool healthCard): void |
| `sharedBin` | `?bool` | Optional | This field indicates if the BIN is shared by multiple issuers<br>Possible values:<br><br>- `true`<br>- `false` | getSharedBin(): ?bool | setSharedBin(?bool sharedBin): void |
| `posDomesticOnly` | `?bool` | Optional | This field indicates if the BIN is valid only for POS domestic usage.<br>Possible values:<br><br>- `true`<br>- `false` | getPosDomesticOnly(): ?bool | setPosDomesticOnly(?bool posDomesticOnly): void |
| `gamblingAllowed` | `?bool` | Optional | This field indicates if gambling transactions are allowed on the BIN.<br>Possible values:<br><br>- `true`<br>- `false` | getGamblingAllowed(): ?bool | setGamblingAllowed(?bool gamblingAllowed): void |
| `commercialCardLevel2` | `?bool` | Optional | This field indicates if a transaction on the instrument qualifies for level 2 interchange rates.<br>Possible values:<br><br>- `true`<br>- `false` | getCommercialCardLevel2(): ?bool | setCommercialCardLevel2(?bool commercialCardLevel2): void |
| `commercialCardLevel3` | `?bool` | Optional | This field indicates if a transaction on the instrument qualifies for level 3 interchange rates.<br>Possible values:<br><br>- `true`<br>- `false` | getCommercialCardLevel3(): ?bool | setCommercialCardLevel3(?bool commercialCardLevel3): void |
| `exemptBin` | `?bool` | Optional | This field indicates if a transaction on the instrument qualifies for government exempt interchange fee.<br>Possible values:<br><br>- `true`<br>- `false` | getExemptBin(): ?bool | setExemptBin(?bool exemptBin): void |
| `accountLevelManagement` | `?bool` | Optional | This field indicates if the BIN participates in Account Level Management (ALM).<br>Possible values:<br><br>- `true`<br>- `false` | getAccountLevelManagement(): ?bool | setAccountLevelManagement(?bool accountLevelManagement): void |
| `onlineGamblingBlock` | `?bool` | Optional | This field indicates if online gambling is blocked on the BIN.<br>Possible values:<br><br>- `true`<br>- `false` | getOnlineGamblingBlock(): ?bool | setOnlineGamblingBlock(?bool onlineGamblingBlock): void |
| `autoSubstantiation` | `?bool` | Optional | This field indicates if auto-substantiation is enabled on the BIN.<br>Possible values:<br><br>- `true`<br>- `false` | getAutoSubstantiation(): ?bool | setAutoSubstantiation(?bool autoSubstantiation): void |
| `flexCredential` | `?bool` | Optional | This field indicates if the instrument is a flex credential.<br>Possible values:<br><br>- `true`<br>- `false` | getFlexCredential(): ?bool | setFlexCredential(?bool flexCredential): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\FeaturesBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$features = FeaturesBuilder::init()
    ->accountFundingSource('accountFundingSource0')
    ->accountFundingSourceSubType('accountFundingSourceSubType6')
    ->cardProduct('cardProduct8')
    ->messageType('messageType6')
    ->acceptanceLevel('acceptanceLevel8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

