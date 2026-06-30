
# Sub Merchant

*This model accepts additional fields of type array.*

## Structure

`SubMerchant`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardAcceptorId` | `?string` | Optional | Unique identifier assigned by the payment card company to the sub-merchant.<br><br>**Constraints**: *Maximum Length*: `15` | getCardAcceptorId(): ?string | setCardAcceptorId(?string cardAcceptorId): void |
| `id` | `?string` | Optional | The ID you assigned to your sub-merchant.<br>Visa Acceptance through VisaNet: For American Express transaction, the value for this field corresponds to the following data in the TC 33 capture file:<br><br>- Record: CP01 TCRB<br>- Position: 65-84<br>- Field: American Express Seller ID<br>  For  Mastercard transactions, the value for this field corresponds to the following data in the TC 33 capture file:<br>- Record: CP01 TCR6<br>- Position: 117-131<br>- Field: Sub-Merchant ID<br>  FDC Compass: This value must consist of uppercase characters.<br><br>American Express Direct: String (20)<br>Visa Acceptance through VisaNet with American Express: String (20)<br>Visa Acceptance through VisaNet with Visa,Mastercard and Discover: String (15)<br>FDC Compass: String (20)<br>FDC Nashville Global: String (14)<br><br>**Constraints**: *Maximum Length*: `20` | getId(): ?string | setId(?string id): void |
| `name` | `?string` | Optional | Sub-merchant’s business name.<br><br>#### American Express Direct<br><br>The maximum length of the sub-merchant name depends on the length of the aggregator name. The combined length for both values must not exceed 36 characters.<br><br>#### Visa Acceptance through VisaNet<br><br>With American Express, the maximum length of the sub-merchant name depends on the length of the aggregator name. The combined length for both values must not exceed 36 characters. The value for this field does not map to the TC 33 capture file5.<br><br>#### FDC Compass<br><br>This value must consist of uppercase characters.<br><br>#### FDC Nashville Global<br><br>With Mastercard, the maximum length of the sub-merchant name depends on the length of the aggregator name:<br><br>- If aggregator name length is 1 through 3, maximum sub-merchant name length is 21.<br>- If aggregator name length is 4 through 7, maximum sub-merchant name length is 17.<br>- If aggregator name length is 8 through 12, maximum sub-merchant name length is 12.<br><br>**Constraints**: *Maximum Length*: `37` | getName(): ?string | setName(?string name): void |
| `address1` | `?string` | Optional | First line of the sub-merchant’s street address.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field does not map to the TC 33 capture file5.<br><br>#### FDC Compass<br><br>This value must consist of uppercase characters.<br><br>**Constraints**: *Maximum Length*: `38` | getAddress1(): ?string | setAddress1(?string address1): void |
| `locality` | `?string` | Optional | Sub-merchant’s city.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field does not map to the TC 33 capture file5.<br><br>#### FDC Compass<br><br>This value must consist of uppercase characters.<br><br>**Constraints**: *Maximum Length*: `21` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | Sub-merchant’s state or province.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field does not map to the TC 33 capture file5.<br><br>#### FDC Compass<br><br>This value must consist of uppercase characters.<br><br>**Constraints**: *Maximum Length*: `50` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `region` | `?string` | Optional | Sub-merchant’s region.<br><br>**Example**\<br>`NE` indicates that the sub-merchant is in the northeast region.<br><br>**Constraints**: *Maximum Length*: `3` | getRegion(): ?string | setRegion(?string region): void |
| `postalCode` | `?string` | Optional | Partial postal code for the sub-merchant’s address.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field does not map to the TC 33 capture file5.<br><br>#### FDC Compass<br><br>This value must consist of uppercase characters.<br><br>**Constraints**: *Maximum Length*: `15` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Sub-merchant’s country. Use the [ISO Standard Country Codes](<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field does not map to the TC 33 capture file.<br><br>#### FDC Compass<br><br>This value must consist of uppercase characters.<br><br>**Constraints**: *Maximum Length*: `3` | getCountry(): ?string | setCountry(?string country): void |
| `email` | `?string` | Optional | Sub-merchant’s email address.<br><br>**Maximum length for processors**<br><br>- American Express Direct: 40<br>- Visa Acceptance through VisaNet: 40<br>- FDC Compass: 40<br>- FDC Nashville Global: 19<br><br>#### Visa Acceptance through VisaNet<br><br>With American Express, the value for this field corresponds to the following data in the TC 33 capture file:<br><br>- Record: CP01 TCRB<br>- Position: 25-64<br>- Field: American Express Seller E-mail Address<br><br>**Note** The TC 33 Capture file contains information about the purchases and refunds that a merchant submits to Visa Acceptance. Visa Acceptance through VisaNet creates the TC 33 Capture file at the end of the day and sends it to the merchant’s acquirer, who uses this information to facilitate end-of-day clearing processing with payment card companies.<br><br>**Constraints**: *Maximum Length*: `40` | getEmail(): ?string | setEmail(?string email): void |
| `phoneNumber` | `?string` | Optional | Sub-merchant’s telephone number.<br><br>**Maximum length for procesors**<br><br>- American Express Direct: 20<br>- Visa Acceptance through VisaNet: 20<br>- FDC Compass: 13<br>- FDC Nashville Global: 10<br><br>#### Visa Acceptance through VisaNet<br><br>With American Express, the value for this field corresponds to the following data in the TC 33 capture file5:<br><br>- Record: CP01 TCRB<br>- Position: 5-24<br>- Field: American Express Seller Telephone Number<br><br>**FDC Compass**\<br>This value must consist of uppercase characters. Use one of these recommended formats:\<br>`NNN-NNN-NNNN`\<br>`NNN-AAAAAAA`<br><br>**Constraints**: *Maximum Length*: `20` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\SubMerchantBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$subMerchant = SubMerchantBuilder::init()
    ->cardAcceptorId('cardAcceptorId0')
    ->id('id6')
    ->name('name6')
    ->address1('address16')
    ->locality('locality4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

