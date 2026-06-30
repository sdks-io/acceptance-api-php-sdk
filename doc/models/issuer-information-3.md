
# Issuer Information 3

*This model accepts additional fields of type array.*

## Structure

`IssuerInformation3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `responseCode` | `?string` | Optional | This is the raw Association/Issuer Response Codes. You can use ‘issuer/association’ response codes to identify when you can retry to authorize a declined transaction and increase successful transaction volumes. You’ll receive an association/issuer response code for the majority of transactions.<br><br>#### Processors supported:<br><br>- HSBC<br>- FDC Nashville Global<br>- SIX<br><br>Currently SIX is not receiving Association/Issuer Response Codes here it receives the additional authorization code that must be printed on the receipt when returned by the processor.<br><br>#### Possible values:<br><br>\| Card Type   \| Response Code \| Description                                                                    \|<br>\| ----------- \| ------------- \| ------------------------------------------------------------------------------ \|<br>\| VISA        \| 000           \| Successful approval/completion or that V.I.P. PIN verification is successful   \|<br>\| VISA        \| 001           \| Refer to card issuer                                                           \|<br>\| VISA        \| 002           \| Refer to card issuer, special condition                                        \|<br>\| VISA        \| 003           \| Invalid merchant or service provider                                           \|<br>\| VISA        \| 004           \| Pickup card                                                                    \|  <br>\| MasterCard  \| 000           \| Approved or completed successfully                                             \|<br>\| MasterCard  \| 001           \| Refer to card issuer                                                           \|<br>\| MasterCard  \| 003           \| Invalid merchant                                                               \|<br>\| MasterCard  \| 004           \| Capture card                                                                   \|<br>\| MasterCard  \| 005           \| Do not honor                                                                   \|<br>\| AMEX        \| 000           \| Approved                                                                       \|<br>\| AMEX        \| 001           \| Approve with ID                                                                \|<br>\| AMEX        \| 002           \| Partial Approval (Prepaid Cards only)                                          \|<br>\| AMEX        \| 100           \| Deny                                                                           \|<br>\| AMEX        \| 101           \| Expired Card/Invalid Expiration Date                                           \|<br>\| Discover    \| 000           \| Approved or completed successfully                                             \|<br>\| Discover    \| 001           \| Reserved for future USE                                                        \|<br>\| Discover    \| 002           \| Reserved for future USE                                                        \|<br>\| Discover    \| 003           \| Invalid Merchant                                                               \|<br>\| Discover    \| 004           \| Capture Card                                                                   \|<br><br>**Constraints**: *Maximum Length*: `6` | getResponseCode(): ?string | setResponseCode(?string responseCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerInformation3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuerInformation3 = IssuerInformation3Builder::init()
    ->responseCode('responseCode8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

