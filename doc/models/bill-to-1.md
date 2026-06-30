
# Bill to 1

*This model accepts additional fields of type array.*

## Structure

`BillTo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | - | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | - | getLastName(): ?string | setLastName(?string lastName): void |
| `address1` | `?string` | Optional | First line of the billing street address.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Second line of the billing street address.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | City of the billing address.<br><br>**Constraints**: *Maximum Length*: `60` | getLocality(): ?string | setLocality(?string locality): void |
| `postalCode` | `?string` | Optional | Postal code for the billing address. The postal code must consist of 5 to 9 digits.<br>When the billing country is the U.S., the 9-digit postal code must follow this format:<br>[5 digits][dash][4 digits]<br>Example: 12345-6789<br>When the billing country is Canada, the 6-digit postal code must follow this format:<br>[alpha][numeric][alpha][space]<br>[numeric][alpha][numeric]<br>Example: A1B 2C3<br><br>**Constraints**: *Maximum Length*: `10` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `administrativeArea` | `?string` | Optional | State or province of the billing address. Use the State, Province, and Territory Codes for the United States and Canada.<br><br>**Constraints**: *Maximum Length*: `60` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `country` | `?string` | Optional | Country of the billing address. Use the two-character ISO Standard Country Codes.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `email` | `?string` | Optional | Email address of the customer.<br><br>**Constraints**: *Maximum Length*: `256` | getEmail(): ?string | setEmail(?string email): void |
| `alternatePhoneNumberVerificationStatus` | `?string` | Optional | #### Visa Platform Connect<br><br>Contains one of the following values that will identify the phone number result code in the account verification response message:<br><br>'VERIFIED' - Customer verified<br><br>'UNVERIFIED' - Customer not verified<br><br>'FAILED' - Customer verification failed<br><br>**Constraints**: *Maximum Length*: `15` | getAlternatePhoneNumberVerificationStatus(): ?string | setAlternatePhoneNumberVerificationStatus(?string alternatePhoneNumberVerificationStatus): void |
| `alternateEmailVerificationStatus` | `?string` | Optional | #### Visa Platform Connect<br><br>Contains one of the following values that will identify the phone number result code in the account verification response message:<br><br>'VERIFIED' - Customer verified<br><br>'UNVERIFIED' - Customer not verified<br><br>'FAILED' - Customer verification failed<br><br>**Constraints**: *Maximum Length*: `15` | getAlternateEmailVerificationStatus(): ?string | setAlternateEmailVerificationStatus(?string alternateEmailVerificationStatus): void |
| `phoneNumber` | `?string` | Optional | Customer’s phone number.<br><br>It is recommended that you include the country code when the order is from outside the U.S.<br><br>#### Chase Paymentech Solutions<br><br>Optional field.<br><br>#### Credit Mutuel-CIC<br><br>Optional field.<br><br>#### Visa Acceptance through VisaNet<br><br>Credit card networks cannot process transactions that contain non-ASCII characters. Visa Acceptance through VisaNet accepts and stores non-ASCII characters correctly and displays them correctly in reports. However, the limitations of the credit card networks prevent Visa Acceptance through VisaNet from transmitting non-ASCII characters to the credit card networks. Therefore, Visa Acceptance through VisaNet replaces non-ASCII characters with meaningless ASCII characters for transmission to the credit card networks.<br><br>#### For Payouts:<br><br>This field may be sent only for FDC Compass.<br><br>#### OmniPay Direct<br><br>Optional field.<br><br>#### SIX<br><br>Optional field.<br><br>#### TSYS Acquiring Solutions<br><br>Optional field.<br><br>#### Worldpay VAP<br><br>Optional field.<br><br>#### All other processors<br><br>Not used.<br><br>**Constraints**: *Maximum Length*: `15` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `nameSuffix` | `?string` | Optional | Customer’s name suffix.<br><br>**Constraints**: *Maximum Length*: `60` | getNameSuffix(): ?string | setNameSuffix(?string nameSuffix): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$billTo1 = BillTo1Builder::init()
    ->firstName('firstName2')
    ->lastName('lastName6')
    ->address1('address10')
    ->address2('address24')
    ->locality('locality2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

