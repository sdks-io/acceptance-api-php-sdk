
# Issuer Information 2

*This model accepts additional fields of type array.*

## Structure

`IssuerInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `country` | `?string` | Optional | Country in which the card was issued. This information enables you to determine whether the card was issued<br>domestically or internationally. Use the two-character [ISO Standard Country Codes](<br><br>This field is supported for Visa, Mastercard, Discover, Diners Club, JCB, and Maestro (International) on Chase<br>Paymentech Solutions.<br><br>**Constraints**: *Maximum Length*: `3` | getCountry(): ?string | setCountry(?string country): void |
| `discretionaryData` | `?string` | Optional | Data defined by the issuer.<br><br>The value for this reply field will probably be the same as the value that you submitted in the authorization request, but it is possible for the processor, issuer, or acquirer to modify the value.<br><br>This field is supported only for Visa transactions on **Visa Acceptance through VisaNet**.<br><br>**Constraints**: *Maximum Length*: `255` | getDiscretionaryData(): ?string | setDiscretionaryData(?string discretionaryData): void |
| `countrySpecificDiscretionaryData` | `?string` | Optional | Data defined by the issuer.<br><br>This national use field contains two subfields for information unique to the processing of Visa transactions by members in Japan.<br>This subfield contains the Katakana text to be printed on the receipt.<br><br>**Constraints**: *Maximum Length*: `140` | getCountrySpecificDiscretionaryData(): ?string | setCountrySpecificDiscretionaryData(?string countrySpecificDiscretionaryData): void |
| `responseCode` | `?string` | Optional | This is the raw Association/Issuer Response Codes. You can use ‘issuer/association’ response codes to identify when you can retry to authorize a declined transaction and increase successful transaction volumes. You’ll receive an association/issuer response code for the majority of transactions.<br><br>#### Processors supported:<br><br>- HSBC<br>- FDC Nashville Global<br>- SIX<br><br>Currently SIX is not receiving Association/Issuer Response Codes here it receives the additional authorization code that must be printed on the receipt when returned by the processor.<br><br>#### Possible values:<br><br>\| Card Type   \| Response Code \| Description                                                                    \|<br>\| ----------- \| ------------- \| ------------------------------------------------------------------------------ \|<br>\| VISA        \| 000           \| Successful approval/completion or that V.I.P. PIN verification is successful   \|<br>\| VISA        \| 001           \| Refer to card issuer                                                           \|<br>\| VISA        \| 002           \| Refer to card issuer, special condition                                        \|<br>\| VISA        \| 003           \| Invalid merchant or service provider                                           \|<br>\| VISA        \| 004           \| Pickup card                                                                    \|  <br>\| MasterCard  \| 000           \| Approved or completed successfully                                             \|<br>\| MasterCard  \| 001           \| Refer to card issuer                                                           \|<br>\| MasterCard  \| 003           \| Invalid merchant                                                               \|<br>\| MasterCard  \| 004           \| Capture card                                                                   \|<br>\| MasterCard  \| 005           \| Do not honor                                                                   \|<br>\| AMEX        \| 000           \| Approved                                                                       \|<br>\| AMEX        \| 001           \| Approve with ID                                                                \|<br>\| AMEX        \| 002           \| Partial Approval (Prepaid Cards only)                                          \|<br>\| AMEX        \| 100           \| Deny                                                                           \|<br>\| AMEX        \| 101           \| Expired Card/Invalid Expiration Date                                           \|<br>\| Discover    \| 000           \| Approved or completed successfully                                             \|<br>\| Discover    \| 001           \| Reserved for future USE                                                        \|<br>\| Discover    \| 002           \| Reserved for future USE                                                        \|<br>\| Discover    \| 003           \| Invalid Merchant                                                               \|<br>\| Discover    \| 004           \| Capture Card                                                                   \|<br><br>**Constraints**: *Maximum Length*: `6` | getResponseCode(): ?string | setResponseCode(?string responseCode): void |
| `pinRequestIndicator` | `?string` | Optional | This field contains value ‘1’ which is sent by Issuer in the response when PIN is requested by issuer,<br><br>This field is only supported for Visa Platform Connect.<br><br>**Constraints**: *Maximum Length*: `1` | getPinRequestIndicator(): ?string | setPinRequestIndicator(?string pinRequestIndicator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerInformation2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuerInformation2 = IssuerInformation2Builder::init()
    ->country('country4')
    ->discretionaryData('discretionaryData4')
    ->countrySpecificDiscretionaryData('countrySpecificDiscretionaryData0')
    ->responseCode('responseCode0')
    ->pinRequestIndicator('pinRequestIndicator2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

