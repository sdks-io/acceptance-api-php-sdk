
# Buyer Information 6

*This model accepts additional fields of type array.*

## Structure

`BuyerInformation6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantCustomerId` | `?string` | Optional | Your identifier for the customer.<br><br>When a subscription or customer profile is being created, the maximum length for this field for most processors is 30. Otherwise, the maximum length is 100.<br><br>#### SEPA/BACS<br><br>Required for Create Mandate and Import Mandate<br><br>#### Comercio Latino<br><br>For recurring payments in Mexico, the value is the customer’s contract number.<br>Note Before you request the authorization, you must inform the issuer of the customer contract numbers that will be used for recurring transactions.<br><br>#### Worldpay VAP<br><br>For a follow-on credit with Worldpay VAP, Visa Acceptance checks the following locations, in the order<br>given, for a customer account ID value and uses the first value it finds:<br><br>1. `customer_account_id` value in the follow-on credit request<br>2. Customer account ID value that was used for the capture that is being credited<br>3. Customer account ID value that was used for the original authorization<br>   If a customer account ID value cannot be found in any of these locations, then no value is used.<br><br>**Constraints**: *Maximum Length*: `100` | getMerchantCustomerId(): ?string | setMerchantCustomerId(?string merchantCustomerId): void |
| `dateOfBirth` | `?string` | Optional | Recipient’s date of birth. **Format**: `YYYYMMDD`.<br><br>This field is a `pass-through`, which means that Visa Acceptance ensures that the value is eight numeric characters<br>but otherwise does not verify the value or modify it in any way before sending it to the processor. If the field<br>is not required for the transaction, Visa Acceptance does not forward it to the processor.<br><br>**Constraints**: *Maximum Length*: `8` | getDateOfBirth(): ?string | setDateOfBirth(?string dateOfBirth): void |
| `gender` | `?string` | Optional | Customer's gender. Possible values are F (female), M (male), O (other).<br><br>**Constraints**: *Maximum Length*: `1` | getGender(): ?string | setGender(?string gender): void |
| `language` | `?string` | Optional | language setting of the user<br><br>**Constraints**: *Maximum Length*: `5` | getLanguage(): ?string | setLanguage(?string language): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$buyerInformation6 = BuyerInformation6Builder::init()
    ->merchantCustomerId('merchantCustomerId0')
    ->dateOfBirth('dateOfBirth6')
    ->gender('gender2')
    ->language('language6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

