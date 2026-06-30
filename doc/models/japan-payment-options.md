
# Japan Payment Options

*This model accepts additional fields of type array.*

## Structure

`JapanPaymentOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentMethod` | `?string` | Optional | This value is a 2-digit code indicating the payment method.<br>Use Payment Method Code value that applies to the tranasction.<br><br>- 10 (One-time payment)<br>- 21, 22, 23, 24  (Bonus(one-time)payment)<br>- 61 (Installment payment)<br>- 31, 32, 33, 34  (Integrated (Bonus + Installment)payment)<br>- 80 (Revolving payment)<br><br>**Constraints**: *Maximum Length*: `2` | getPaymentMethod(): ?string | setPaymentMethod(?string paymentMethod): void |
| `bonuses` | [`?(Bonuse[])`](../../doc/models/bonuse.md) | Optional | An array of objects, each of which contains a bonus month and bonus amount.<br>Length of bonuses array is equal to the number of bonuses.  Max length = 6.<br>In case of bonus month and amount not specified, null objects to be returned in the array.<br>Example: bonuses : [ {"month": "1","amount": "200"}, {"month": "3","amount": "2500"}, null] | getBonuses(): ?array | setBonuses(?array bonuses): void |
| `preapprovalType` | `?string` | Optional | This will contain the details of the kind of transaction that has been processe. Used only for Japan.<br>Possible Values:<br><br>- 0 = Normal (authorization with amount and clearing/settlement; data capture or paper draft)<br>- 1 = Negative card authorization (authorization-only with 0 or 1 amount)<br>- 2 = Reservation of authorization (authorization-only with amount)<br>- 3 = Cancel transaction<br>- 4 = Merchant-initiated reversal/refund transactions<br>- 5 = Cancel reservation of authorization<br>- 6 = Post authorization<br><br>**Constraints**: *Maximum Length*: `1` | getPreapprovalType(): ?string | setPreapprovalType(?string preapprovalType): void |
| `installments` | `?string` | Optional | Number of Installments. | getInstallments(): ?string | setInstallments(?string installments): void |
| `terminalId` | `?string` | Optional | Unique Japan Credit Card Association (JCCA) terminal identifier.<br><br>The difference between this field and the `pointOfSaleInformation.terminalID` field is that you can define<br>`pointOfSaleInformation.terminalID`, but `processingInformation.japanPaymentOptions.terminalId` is<br>defined by the JCCA and is used only in Japan.<br><br>This field is supported only on Visa Acceptance through VisaNet and JCN Gateway.<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `13` | getTerminalId(): ?string | setTerminalId(?string terminalId): void |
| `firstBillingMonth` | `?string` | Optional | Billing month in MM format.<br><br>**Constraints**: *Maximum Length*: `2` | getFirstBillingMonth(): ?string | setFirstBillingMonth(?string firstBillingMonth): void |
| `businessName` | `?string` | Optional | Business name in Japanese characters. This field is supported only on JCN Gateway and for the Sumitomo Mitsui Card Co. acquirer on Visa Acceptance through VisaNet.<br><br>**Constraints**: *Maximum Length*: `25` | getBusinessName(): ?string | setBusinessName(?string businessName): void |
| `businessNameKatakana` | `?string` | Optional | Business name in Katakana characters. This field is supported only on JCN Gateway and for the Sumitomo Mitsui Card Co. acquirer on Visa Acceptance through VisaNet.<br><br>**Constraints**: *Maximum Length*: `25` | getBusinessNameKatakana(): ?string | setBusinessNameKatakana(?string businessNameKatakana): void |
| `jis2TrackData` | `?string` | Optional | Japanese Industrial Standard Type 2 (JIS2) track data from the front of the card.<br><br>This field is supported only on Visa Acceptance through VisaNet and JCN Gateway.<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `69` | getJis2TrackData(): ?string | setJis2TrackData(?string jis2TrackData): void |
| `businessNameAlphaNumeric` | `?string` | Optional | Business name in alphanumeric characters. This field is supported only on JCN Gateway and for the Sumitomo Mitsui Card Co. acquirer on Visa Acceptance through VisaNet.<br><br>**Constraints**: *Maximum Length*: `25` | getBusinessNameAlphaNumeric(): ?string | setBusinessNameAlphaNumeric(?string businessNameAlphaNumeric): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\JapanPaymentOptionsBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BonuseBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$japanPaymentOptions = JapanPaymentOptionsBuilder::init()
    ->paymentMethod('paymentMethod0')
    ->bonuses(
        [
            BonuseBuilder::init()
                ->month('month0')
                ->amount('amount2')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            BonuseBuilder::init()
                ->month('month0')
                ->amount('amount2')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->preapprovalType('preapprovalType2')
    ->installments('installments2')
    ->terminalId('terminalId0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

