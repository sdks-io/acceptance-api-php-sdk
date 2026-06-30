
# Buyer Information 34

*This model accepts additional fields of type array.*

## Structure

`BuyerInformation34`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantCustomerId` | `?string` | Optional | Your identifier for the customer.<br><br>When a subscription or customer profile is being created, the maximum length for this field for most processors is 30. Otherwise, the maximum length is 100.<br><br>#### Comercio Latino<br><br>For recurring payments in Mexico, the value is the customer’s contract number.<br>Note Before you request the authorization, you must inform the issuer of the customer contract numbers that will be used for recurring transactions.<br><br>#### Worldpay VAP<br><br>For a follow-on credit with Worldpay VAP, Visa Acceptance checks the following locations, in the order<br>given, for a customer account ID value and uses the first value it finds:<br><br>1. `customer_account_id` value in the follow-on credit request<br>2. Customer account ID value that was used for the capture that is being credited<br>3. Customer account ID value that was used for the original authorization<br>   If a customer account ID value cannot be found in any of these locations, then no value is used.<br><br>**Constraints**: *Maximum Length*: `100` | getMerchantCustomerId(): ?string | setMerchantCustomerId(?string merchantCustomerId): void |
| `hashedPassword` | `?string` | Optional | The merchant's password that Visa Acceptance hashes and stores as a hashed password.<br><br>**Constraints**: *Maximum Length*: `100` | getHashedPassword(): ?string | setHashedPassword(?string hashedPassword): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation34Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$buyerInformation34 = BuyerInformation34Builder::init()
    ->merchantCustomerId('merchantCustomerId6')
    ->hashedPassword('hashedPassword4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

