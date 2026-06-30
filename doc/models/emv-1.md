
# Emv 1

*This model accepts additional fields of type array.*

## Structure

`Emv1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `tags` | `?string` | Optional | EMV data that is transmitted from the chip card to the issuer, and from the issuer to the chip card. The EMV<br>data is in the tag-length-value format and includes chip card tags, terminal tags, and transaction detail tags.<br><br>For information about the individual tags, see the “Application Specification” section in the EMV 4.3 Specifications:<br><br>**Note** Card present information about EMV applies only to credit card processing and PIN debit processing.<br>All other card present information applies only to credit card processing. PIN debit processing is available only<br>on FDC Nashville Global.<br><br>**Important** The following tags contain sensitive information and **must not** be included in this field:<br><br>- `56`: Track 1 equivalent data<br>- `57`: Track 2 equivalent data<br>- `5A`: Application PAN<br>- `5F20`: Cardholder name<br>- `5F24`: Application expiration date (This sensitivity has been relaxed for Credit Mutuel-CIC, American Express Direct, FDC Nashville Global, First Data Merchant Solutions, and SIX)<br>- `99`: Transaction PIN<br>- `9F0B`: Cardholder name (extended)<br>- `9F1F`: Track 1 discretionary data<br>- `9F20`: Track 2 discretionary data<br><br>For captures, this field is required for contact EMV transactions. Otherwise, it is optional.<br><br>For credits, this field is required for contact EMV stand-alone credits and contactless EMV stand-alone credits.<br>Otherwise, it is optional.<br><br>**Important** For contact EMV captures, contact EMV stand-alone credits, and contactless EMV stand-alone credits,<br>you must include the following tags in this field. For all other types of EMV transactions, the following tags<br>are optional.<br><br>- `95`: Terminal verification results<br>- `9F10`: Issuer application data<br>- `9F26`: Application cryptogram<br><br>#### Visa Acceptance through VisaNet<br><br>- In Japan: 199 bytes<br>- In other countries: String (252)<br><br>For Mastercard Transactions, Optionally Tag 9F60 (Authenticated Application Data) and<br>Tag 96 (Kernel Identifier - Terminal) can be included in the Field.<br><br>#### GPX<br><br>This field only supports transactions from the following card types:<br><br>- Visa<br>- Mastercard<br>- AMEX<br>- Discover<br>- Diners<br>- JCB<br>- Union Pay International<br><br>#### JCN Gateway<br><br>The following tags must be included:<br><br>- `4F`: Application identifier<br>- `84`: Dedicated file name<br><br>Data length: 199 bytes<br><br>#### All other processors:<br><br>String (999)<br><br>#### Used by<br><br>Authorization: Optional<br>Authorization Reversal: Optional<br>Credit: Optional<br>PIN Debit processing (purchase, credit and reversal): Optional<br><br>**Constraints**: *Maximum Length*: `1998` | getTags(): ?string | setTags(?string tags): void |
| `chipValidationType` | `?string` | Optional | Entity or service that provided the validation results returned in `chipValidationResult`.<br><br>Possible values:<br><br>- `02`: MasterCard on-behalf pre-validation service (The MasterCard authorization platform validated the M/Chip cryptogram before the authorization request reached the issuer.)<br>- `03`: MasterCard on-behalf stand-in service (The MasterCard authorization platform validated the M/Chip cryptogram because the issuer was not available.)<br>- `50`: Issuer<br>- `90`: Chip fall-back transaction downgrade process (The chip could not be read.)<br><br>This field is returned only for NFC payment network tokenization transactions with MasterCard.<br><br>**Note** No Visa Acceptance through VisaNet acquirers support EMV at this time.<br><br>**Constraints**: *Maximum Length*: `2` | getChipValidationType(): ?string | setChipValidationType(?string chipValidationType): void |
| `chipValidationResult` | `?string` | Optional | Cryptogram validation results returned by the entity or service specified in `chipValidationType`.<br><br>Possible values:<br><br>- `A`: Application cryptogram is valid, but the application transaction counter (ATC) is outside allowed range. (A large jump in ATC values may indicate data copying or other fraud.)<br>- `C`: Chip validation was completed successfully.<br>- `E`: Application cryptogram is valid but the ATC indicates possible replay fraud.<br>- `F`: Format error in the chip data.<br>- `G`: Application cryptogram is valid but is not a valid authorization request cryptogram (ARQC).<br>- `I`: Application cryptogram is invalid.<br>- `T`: Application cryptogram is valid but terminal verification results (TVR) or card verification results (CVR) are invalid.<br>- `U`: Application cryptogram could not be validated because of a technical error.<br><br>This field is returned only for NFC payment network tokenization transactions with MasterCard.<br><br>**Note** No Visa Acceptance through VisaNet acquirers support EMV at this time.<br><br>**Constraints**: *Maximum Length*: `1` | getChipValidationResult(): ?string | setChipValidationResult(?string chipValidationResult): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Emv1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$emv1 = Emv1Builder::init()
    ->tags('tags8')
    ->chipValidationType('chipValidationType0')
    ->chipValidationResult('chipValidationResult2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

