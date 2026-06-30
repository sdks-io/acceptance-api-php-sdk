
# Buyer Information 1

*This model accepts additional fields of type array.*

## Structure

`BuyerInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantCustomerId` | `?string` | Optional | Your identifier for the customer.<br><br>When a subscription or customer profile is being created, the maximum length for this field for most processors is 30. Otherwise, the maximum length is 100.<br><br>#### Comercio Latino<br><br>For recurring payments in Mexico, the value is the customer’s contract number.<br>Note Before you request the authorization, you must inform the issuer of the customer contract numbers that will be used for recurring transactions.<br><br>#### Worldpay VAP<br><br>For a follow-on credit with Worldpay VAP, Visa Acceptance checks the following locations, in the order<br>given, for a customer account ID value and uses the first value it finds:<br><br>1. `customer_account_id` value in the follow-on credit request<br>2. Customer account ID value that was used for the capture that is being credited<br>3. Customer account ID value that was used for the original authorization<br>   If a customer account ID value cannot be found in any of these locations, then no value is used.<br><br>**Constraints**: *Maximum Length*: `100` | getMerchantCustomerId(): ?string | setMerchantCustomerId(?string merchantCustomerId): void |
| `dateOfBirth` | `?string` | Optional | Recipient’s date of birth. **Format**: `YYYYMMDD`.<br><br>This field is a `pass-through`, which means that Visa Acceptance ensures that the value is eight numeric characters<br>but otherwise does not verify the value or modify it in any way before sending it to the processor. If the field<br>is not required for the transaction, Visa Acceptance does not forward it to the processor.<br><br>**Constraints**: *Maximum Length*: `8` | getDateOfBirth(): ?string | setDateOfBirth(?string dateOfBirth): void |
| `vatRegistrationNumber` | `?string` | Optional | Customer’s government-assigned tax identification number.<br><br>#### Tax Calculation<br><br>Optional for international and value added taxes only. Not applicable to U.S. and Canadian taxes.<br><br>**Constraints**: *Maximum Length*: `20` | getVatRegistrationNumber(): ?string | setVatRegistrationNumber(?string vatRegistrationNumber): void |
| `personalIdentification` | [`?(PersonalIdentification[])`](../../doc/models/personal-identification.md) | Optional | - | getPersonalIdentification(): ?array | setPersonalIdentification(?array personalIdentification): void |
| `taxId` | `?string` | Optional | The description for this field is not available. | getTaxId(): ?string | setTaxId(?string taxId): void |
| `loginId` | `?string` | Optional | The buyer’s Alipay login Id, the id might be an email or mobile number. The id is partially masked for privacy. cao***@126.com  or 186***22156<br><br>**Constraints**: *Maximum Length*: `64` | getLoginId(): ?string | setLoginId(?string loginId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PersonalIdentificationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$buyerInformation1 = BuyerInformation1Builder::init()
    ->merchantCustomerId('merchantCustomerId8')
    ->dateOfBirth('dateOfBirth2')
    ->vatRegistrationNumber('vatRegistrationNumber6')
    ->personalIdentification(
        [
            PersonalIdentificationBuilder::init()
                ->type('type2')
                ->id('id8')
                ->issuedBy('issuedBy6')
                ->verificationResults('verificationResults0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->taxId('taxId2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

