
# Emv 6

*This model accepts additional fields of type array.*

## Structure

`Emv6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `tags` | `?string` | Optional | EMV data that is transmitted from the chip card to the issuer, and from the issuer to the chip card. The EMV<br>data is in the tag-length-value format and includes chip card tags, terminal tags, and transaction detail tags.<br><br>For information about the individual tags, see the “Application Specification” section in the EMV 4.3 Specifications:<br><br>**Note** Card present information about EMV applies only to credit card processing and PIN debit processing.<br>All other card present information applies only to credit card processing. PIN debit processing is available only<br>on FDC Nashville Global.<br><br>**Important** The following tags contain sensitive information and **must not** be included in this field:<br><br>- `56`: Track 1 equivalent data<br>- `57`: Track 2 equivalent data<br>- `5A`: Application PAN<br>- `5F20`: Cardholder name<br>- `5F24`: Application expiration date (This sensitivity has been relaxed for Credit Mutuel-CIC, American Express Direct, FDC Nashville Global, First Data Merchant Solutions, and SIX)<br>- `99`: Transaction PIN<br>- `9F0B`: Cardholder name (extended)<br>- `9F1F`: Track 1 discretionary data<br>- `9F20`: Track 2 discretionary data<br><br>For captures, this field is required for contact EMV transactions. Otherwise, it is optional.<br><br>For credits, this field is required for contact EMV stand-alone credits and contactless EMV stand-alone credits.<br>Otherwise, it is optional.<br><br>**Important** For contact EMV captures, contact EMV stand-alone credits, and contactless EMV stand-alone credits,<br>you must include the following tags in this field. For all other types of EMV transactions, the following tags<br>are optional.<br><br>- `95`: Terminal verification results<br>- `9F10`: Issuer application data<br>- `9F26`: Application cryptogram<br><br>#### Visa Acceptance through VisaNet<br><br>- In Japan: 199 bytes<br>- In other countries: String (252)<br><br>For Mastercard Transactions, Optionally Tag 9F60 (Authenticated Application Data) and<br>Tag 96 (Kernel Identifier - Terminal) can be included in the Field.<br><br>#### GPX<br><br>This field only supports transactions from the following card types:<br><br>- Visa<br>- Mastercard<br>- AMEX<br>- Discover<br>- Diners<br>- JCB<br>- Union Pay International<br><br>#### JCN Gateway<br><br>The following tags must be included:<br><br>- `4F`: Application identifier<br>- `84`: Dedicated file name<br><br>Data length: 199 bytes<br><br>#### All other processors:<br><br>String (999)<br><br>#### Used by<br><br>Authorization: Optional<br>Authorization Reversal: Optional<br>Credit: Optional<br>PIN Debit processing (purchase, credit and reversal): Optional<br><br>**Constraints**: *Maximum Length*: `1998` | getTags(): ?string | setTags(?string tags): void |
| `fallback` | `?bool` | Optional | Indicates whether a fallback method was used to enter credit card information into the POS terminal. When a<br>technical problem prevents a successful exchange of information between a chip card and a chip-capable terminal:<br><br>1. Swipe the card or key the credit card information into the POS terminal.<br>2. Use the pointOfSaleInformation.entryMode field to indicate whether the information was swiped or keyed.<br><br>Possible values:<br><br>- `true`: Fallback method was used.<br>- `false` (default): Fallback method was not used.<br><br>This field is supported only on American Express Direct, Chase Paymentech Solutions, Visa Acceptance through VisaNet,<br>FDC Nashville Global, GPN, JCN Gateway, OmniPay Direct, and SIX. | getFallback(): ?bool | setFallback(?bool fallback): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Emv6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$emv6 = Emv6Builder::init()
    ->tags('tags2')
    ->fallback(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

