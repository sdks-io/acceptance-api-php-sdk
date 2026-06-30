
# Merchant Advice

*This model accepts additional fields of type array.*

## Structure

`MerchantAdvice`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | - Merchant should update their retry logic to ensure retry is not attempted for the cards for which Issuer won’t approve the transactions and where the retry is allowed.<br>- Card Processing Associations provides this data which is being passed through in the following data element irrespective of the Card Associations.   Usage of this data must be always associated with the Card Associations card types for merchant processing retry logic.<br>- In additions to the Merchant Advice code, Associations also provides the decline response codes which provides the reason for decline.  Association response code will be a pass-through value.<br><br>#### Processors supported:<br><br>- HSBC<br>- Barclays<br>- FDC Nash<br>- FDI Global<br>- Elavon America<br>- VPC<br>- Rede<br>- Payment tech Salem<br><br>#### Possible values:<br><br>\| Card Type   \| Advice Code   \|  Description                                \|<br>\| ----------- \| ------------- \| ------------------------------------------- \|<br>\| VISA        \| 1             \| Issuer never approves                       \|<br>\| VISA        \| 2             \| Issuer cannot approve at this time          \|<br>\| VISA        \| 3             \| Data quality/revalidate payment information \|<br>\| MasterCard  \| 01            \| New account information available           \|<br>\| MasterCard  \| 02            \| Try Again Later                             \|<br>\| MasterCard  \| 03            \| Do Not Try Again                            \|<br>\| MasterCard  \| 04            \| Token not supported                         \|<br>\| MasterCard  \| 21            \| Do not honor                                \|<br>\| MasterCard  \| 22            \| Merchant does not qualify for product code  \|<br>\| MasterCard  \| 24            \| Retry after 1 hour                          \|<br>\| MasterCard  \| 25            \| Retry after 24 hours                        \|<br>\| MasterCard  \| 26            \| Retry after 2 days                          \|<br>\| MasterCard  \| 27            \| Retry after 4 days                          \|<br>\| MasterCard  \| 28            \| Retry after 6 days                          \|<br>\| MasterCard  \| 29            \| Retry after 8 days                          \|<br>\| MasterCard  \| 30            \| Retry after 10 days                         \|<br>\| MasterCard  \| 40            \| Consumer non-reloadable prepaid card        \|<br>\| MasterCard  \| 41            \| Consumer single-use virtual card number     \|<br>\| MasterCard  \| 42            \| Sanctions score exceeds threshold value     \|<br>\| MasterCard  \| 99            \| Do Not Try Again                            \|<br><br>**Constraints**: *Maximum Length*: `2` | getCode(): ?string | setCode(?string code): void |
| `codeRaw` | `?string` | Optional | Raw merchant advice code sent directly from the processor. This field is used only for Mastercard.<br><br>#### Visa Acceptance through VisaNet<br><br>The value for this field corresponds to the following data in the TC 33 capture file1:<br><br>- Record: CP01 TCR7<br>- Position: 96-99<br>- Field: Response Data-Merchant Advice Code<br><br>**Constraints**: *Maximum Length*: `4` | getCodeRaw(): ?string | setCodeRaw(?string codeRaw): void |
| `nameMatch` | `?string` | Optional | #### Visa Platform Connect<br><br>The field contains will contain the Account Name Request Result for zero amount Authorization request. Valid values are:<br><br>00 = Name Match Performed<br>01 = Name Match not Performed<br>02 = Name Match not supported<br><br>**Constraints**: *Maximum Length*: `2` | getNameMatch(): ?string | setNameMatch(?string nameMatch): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantAdviceBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantAdvice = MerchantAdviceBuilder::init()
    ->code('code8')
    ->codeRaw('codeRaw4')
    ->nameMatch('nameMatch0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

