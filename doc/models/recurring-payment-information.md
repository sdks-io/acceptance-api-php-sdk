
# Recurring Payment Information

This object contains recurring payment information.

*This model accepts additional fields of type array.*

## Structure

`RecurringPaymentInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `endDate` | `string` | Required | The date after which no further recurring authorizations should be performed. Format: `YYYY-MM-DD`<br>**Note** This field is required for recurring transactions.<br><br>**Constraints**: *Maximum Length*: `10` | getEndDate(): string | setEndDate(string endDate): void |
| `frequency` | `int` | Required | Integer value indicating the minimum number of days between recurring authorizations. A frequency<br>of monthly is indicated by the value 28. Multiple of 28 days will be used to indicate months.<br><br>Example: 6 months = 168<br><br>Example values accepted (31 days):<br><br>- 31<br>- 031<br>- 0031<br><br>**Note** This field is required for recurring transactions. | getFrequency(): int | setFrequency(int frequency): void |
| `numberOfPayments` | `?int` | Optional | Total number of payments for the duration of the recurring subscription. | getNumberOfPayments(): ?int | setNumberOfPayments(?int numberOfPayments): void |
| `originalPurchaseDate` | `?string` | Optional | Date of original purchase. Required for recurring transactions.<br>Format: `YYYY-MM-DDTHH:MM:SSZ`<br>**Note**: If this field is empty, the current date is used.<br><br>**Constraints**: *Maximum Length*: `17` | getOriginalPurchaseDate(): ?string | setOriginalPurchaseDate(?string originalPurchaseDate): void |
| `sequenceNumber` | `?int` | Optional | This field is mandatory for Cartes Bancaires recurring transactions on Credit Mutuel-CIC.  <br>This field records recurring sequence, e.g. 1st for initial,  2 for subsequent, 3 etc | getSequenceNumber(): ?int | setSequenceNumber(?int sequenceNumber): void |
| `type` | `?string` | Optional | This contains the type of recurring payment.<br>Valid Values :<br>1 - Registration/First transaction<br>2 - Subsequent transaction<br>3 - Modification<br>4 - Cancellation<br><br>**Constraints**: *Maximum Length*: `1` | getType(): ?string | setType(?string type): void |
| `occurrence` | `?string` | Optional | This value indicates how often a recurring payment occurs.<br>Valid Values :<br>• 01 (Daily)<br>• 02 (Twice weekly)<br>• 03 (Weekly)<br>• 04 (Ten days)<br>• 05 (Fortnightly)<br>• 06 (Monthly)<br>• 07 (Every two months)<br>• 08 (Trimester)<br>• 09 (Quarterly)<br>• 10 (Twice yearly)<br>• 11 (Annually)<br>• 12 (Unscheduled)<br><br>**Constraints**: *Maximum Length*: `2` | getOccurrence(): ?string | setOccurrence(?string occurrence): void |
| `validationIndicator` | `?string` | Optional | This tag will contain a value that indicates whether or not the recurring payment transaction has been validated.<br>Valid values :<br>0- Not validated<br>1- Validated<br><br>**Constraints**: *Maximum Length*: `1` | getValidationIndicator(): ?string | setValidationIndicator(?string validationIndicator): void |
| `amountType` | `?string` | Optional | Indicates recurring amount type agreed by the cardholder<br>Valid Values :<br>1- Fixed amount recurring payment<br>2- Recurring payment with maximum amount<br><br>**Constraints**: *Maximum Length*: `1` | getAmountType(): ?string | setAmountType(?string amountType): void |
| `maximumAmount` | `?string` | Optional | This API field will contain the maximum amount agreed to by the cardholder. The currency of this amount<br>will be specified in Field 49—Currency Code,Transaction.<br><br>**Constraints**: *Maximum Length*: `12` | getMaximumAmount(): ?string | setMaximumAmount(?string maximumAmount): void |
| `referenceNumber` | `?string` | Optional | This will contain a unique reference number for the recurring payment transaction.<br><br>**Constraints**: *Maximum Length*: `35` | getReferenceNumber(): ?string | setReferenceNumber(?string referenceNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RecurringPaymentInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$recurringPaymentInformation = RecurringPaymentInformationBuilder::init(
    'endDate2',
    64
)
    ->numberOfPayments(4)
    ->originalPurchaseDate('originalPurchaseDate0')
    ->sequenceNumber(132)
    ->type('type0')
    ->occurrence('occurrence8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

