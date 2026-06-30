
# Buyer Information

*This model accepts additional fields of type array.*

## Structure

`BuyerInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantCustomerId` | `?string` | Optional | Your identifier for the customer.<br><br>When a subscription or customer profile is being created, the maximum length for this field for most processors is 30. Otherwise, the maximum length is 100.<br><br>#### Comercio Latino<br><br>For recurring payments in Mexico, the value is the customer’s contract number.<br>Note Before you request the authorization, you must inform the issuer of the customer contract numbers that will be used for recurring transactions.<br><br>#### Worldpay VAP<br><br>For a follow-on credit with Worldpay VAP, Visa Acceptance checks the following locations, in the order<br>given, for a customer account ID value and uses the first value it finds:<br><br>1. `customer_account_id` value in the follow-on credit request<br>2. Customer account ID value that was used for the capture that is being credited<br>3. Customer account ID value that was used for the original authorization<br>   If a customer account ID value cannot be found in any of these locations, then no value is used.<br><br>**Constraints**: *Maximum Length*: `100` | getMerchantCustomerId(): ?string | setMerchantCustomerId(?string merchantCustomerId): void |
| `dateOfBirth` | `?string` | Optional | Recipient’s date of birth. **Format**: `YYYYMMDD`.<br><br>This field is a `pass-through`, which means that Visa Acceptance ensures that the value is eight numeric characters<br>but otherwise does not verify the value or modify it in any way before sending it to the processor. If the field<br>is not required for the transaction, Visa Acceptance does not forward it to the processor.<br><br>**Constraints**: *Maximum Length*: `8` | getDateOfBirth(): ?string | setDateOfBirth(?string dateOfBirth): void |
| `vatRegistrationNumber` | `?string` | Optional | Customer’s government-assigned tax identification number.<br><br>#### Tax Calculation<br><br>Optional for international and value added taxes only. Not applicable to U.S. and Canadian taxes.<br><br>**Constraints**: *Maximum Length*: `20` | getVatRegistrationNumber(): ?string | setVatRegistrationNumber(?string vatRegistrationNumber): void |
| `companyTaxId` | `?string` | Optional | Company’s tax identifier. This is only used for eCheck service.<br><br>** TeleCheck **<br>Contact your TeleCheck representative to find out whether this field is required or optional.<br><br>** All Other Processors **<br>Not used.<br><br>**Constraints**: *Maximum Length*: `9` | getCompanyTaxId(): ?string | setCompanyTaxId(?string companyTaxId): void |
| `personalIdentification` | [`?(PersonalIdentification[])`](../../doc/models/personal-identification.md) | Optional | - | getPersonalIdentification(): ?array | setPersonalIdentification(?array personalIdentification): void |
| `hashedPassword` | `?string` | Optional | The merchant's password that Visa Acceptance hashes and stores as a hashed password.<br><br>**Constraints**: *Maximum Length*: `100` | getHashedPassword(): ?string | setHashedPassword(?string hashedPassword): void |
| `gender` | `?string` | Optional | Customer's gender. Possible values are F (female), M (male),O (other).<br><br>**Constraints**: *Maximum Length*: `3` | getGender(): ?string | setGender(?string gender): void |
| `language` | `?string` | Optional | language setting of the user.<br>Supports 2-character language codes (e.g., en, fr) and 5-character locale values (e.g., en-US, fr-CA).<br><br>**Constraints**: *Maximum Length*: `5` | getLanguage(): ?string | setLanguage(?string language): void |
| `noteToSeller` | `?string` | Optional | Note to the recipient of the funds in this transaction<br><br>**Constraints**: *Maximum Length*: `255` | getNoteToSeller(): ?string | setNoteToSeller(?string noteToSeller): void |
| `mobilePhone` | `?int` | Optional | Cardholder’s mobile phone number.<br>**Important** Required for Visa Secure transactions in Brazil.<br>Do not use this request field for any other types of transactions. | getMobilePhone(): ?int | setMobilePhone(?int mobilePhone): void |
| `walletId` | `?string` | Optional | The one-time identification code of the Alipay wallet user.<br>It is scanned from the barcode that is shown by the mobile application.<br><br>**Constraints**: *Maximum Length*: `150` | getWalletId(): ?string | setWalletId(?string walletId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PersonalIdentificationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$buyerInformation = BuyerInformationBuilder::init()
    ->merchantCustomerId('merchantCustomerId4')
    ->dateOfBirth('dateOfBirth2')
    ->vatRegistrationNumber('vatRegistrationNumber0')
    ->companyTaxId('companyTaxId4')
    ->personalIdentification(
        [
            PersonalIdentificationBuilder::init()
                ->type('type2')
                ->id('id8')
                ->issuedBy('issuedBy6')
                ->verificationResults('verificationResults0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            PersonalIdentificationBuilder::init()
                ->type('type2')
                ->id('id8')
                ->issuedBy('issuedBy6')
                ->verificationResults('verificationResults0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            PersonalIdentificationBuilder::init()
                ->type('type2')
                ->id('id8')
                ->issuedBy('issuedBy6')
                ->verificationResults('verificationResults0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

