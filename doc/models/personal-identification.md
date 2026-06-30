
# Personal Identification

*This model accepts additional fields of type array.*

## Structure

`PersonalIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | The type of the identification.<br><br>Possible values:<br><br>- `NATIONAL`<br>- `CPF`<br>- `CPNJ`<br>- `CURP`<br>- `SSN`<br>- `DRIVER_LICENSE`<br>- `PASSPORT_NUMBER`<br>- `PERSONAL_ID`<br>- `TAX_ID`<br>- `BR_CPF`     The individual tax ID type, typically is 11 characters long<br>- `BR_CNPJ`    The business tax ID type, typically is 14 characters long.<br><br>This field is supported only on the following processors.<br><br>#### ComercioLatino<br><br>Set this field to the Cadastro de Pessoas Fisicas (CPF).<br><br>#### Visa Acceptance Latin American Processing<br><br>Supported for Redecard in Brazil. Set this field to the Cadastro de Pessoas Fisicas (CPF), which is required for AVS for Redecard in Brazil.<br>**Note** Visa Acceptance Latin American Processing is the name of a specific processing connection that Visa Acceptance supports. In the Visa Acceptance API documentation, Visa Acceptance Latin American Processing does not refer to the general topic of processing in Latin America. The information in this field description is for the specific processing connection called Visa Acceptance Latin American Processing. It is not for any other Latin American processors that Visa Acceptance supports. | getType(): ?string | setType(?string type): void |
| `id` | `?string` | Optional | The value of the identification type. This field is supported only on the following processors.<br><br>#### ComercioLatino<br><br>Set this field to the Cadastro de Pessoas Fisicas (CPF).<br><br>#### Visa Acceptance Latin American Processing<br><br>Supported for Redecard in Brazil. Set this field to the Cadastro de Pessoas Fisicas (CPF), which is required for AVS for Redecard in Brazil.<br>**Note** Visa Acceptance Latin American Processing is the name of a specific processing connection that Visa Acceptance supports. In the Visa Acceptance API documentation, Visa Acceptance Latin American Processing does not refer to the general topic of processing in Latin America. The information in this field description is for the specific processing connection called Visa Acceptance Latin American Processing. It is not for any other Latin American processors that Visa Acceptance supports.  <br>If `type = PASSPORT`, this is the cardholder's passport number.<br>Recommended for Discover ProtectBuy.<br><br>**Constraints**: *Maximum Length*: `26` | getId(): ?string | setId(?string id): void |
| `issuedBy` | `?string` | Optional | The government agency that issued the driver's license or passport.<br><br>If **type**` = DRIVER_LICENSE`, this is the State or province where the customer’s driver’s license was issued.<br><br>If **type**` = PASSPORT`, this is the Issuing country for the cardholder’s passport. Recommended for Discover ProtectBuy.<br><br>Use the two-character [State, Province, and Territory Codes for the United States and Canada](<br><br>#### TeleCheck<br><br>Contact your TeleCheck representative to find out whether this field is required or optional.<br><br>#### All Other Processors<br><br>Not used. | getIssuedBy(): ?string | setIssuedBy(?string issuedBy): void |
| `verificationResults` | `?string` | Optional | Verification results received from Issuer or Card Network for verification transactions. Response Only Field. | getVerificationResults(): ?string | setVerificationResults(?string verificationResults): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PersonalIdentificationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$personalIdentification = PersonalIdentificationBuilder::init()
    ->type('type2')
    ->id('id8')
    ->issuedBy('issuedBy6')
    ->verificationResults('verificationResults0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

