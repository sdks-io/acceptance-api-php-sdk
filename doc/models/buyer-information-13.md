
# Buyer Information 13

*This model accepts additional fields of type array.*

## Structure

`BuyerInformation13`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `companyTaxId` | `?string` | Optional | Company’s tax identifier. This is only used for eCheck service.<br><br>**Constraints**: *Maximum Length*: `9` | getCompanyTaxId(): ?string | setCompanyTaxId(?string companyTaxId): void |
| `currency` | `?string` | Optional | Currency used for the order. Use the three-character I[ISO Standard Currency Codes.](<br><br>For an authorization reversal (`reversalInformation`) or a capture (`processingOptions.capture` is set to `true`), you must use the same currency that you used in your payment authorization request.<br><br>#### DCC for First Data<br><br>Your local currency. For details, see the `currency` field description in [Dynamic Currency Conversion For First Data Using the SCMP API](<br><br># For details about currency as used in partial authorizations, see "Features for Debit Cards and Prepaid Cards" in the [Credit Card Services Using the SCMP API Guide](<br><br>**Constraints**: *Maximum Length*: `3` | getCurrency(): ?string | setCurrency(?string currency): void |
| `dateOfBirth` | `?DateTime` | Optional | Date of birth of the customer. Format: YYYY-MM-DD | getDateOfBirth(): ?\DateTime | setDateOfBirth(?\DateTime dateOfBirth): void |
| `personalIdentification` | [`?(PersonalIdentification9[])`](../../doc/models/personal-identification-9.md) | Optional | - | getPersonalIdentification(): ?array | setPersonalIdentification(?array personalIdentification): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation13Builder;
use VisaAcceptanceMergedSpecLib\Utils\DateTimeHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PersonalIdentification9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuedByBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$buyerInformation13 = BuyerInformation13Builder::init()
    ->companyTaxId('companyTaxID4')
    ->currency('currency4')
    ->dateOfBirth(DateTimeHelper::fromSimpleDate('1960-12-30'))
    ->personalIdentification(
        [
            PersonalIdentification9Builder::init()
                ->id('id8')
                ->type('type2')
                ->issuedBy(
                    IssuedByBuilder::init()
                        ->administrativeArea('administrativeArea4')
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build()
                )
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

