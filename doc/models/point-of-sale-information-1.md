
# Point of Sale Information 1

*This model accepts additional fields of type array.*

## Structure

`PointOfSaleInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `emv` | [`?Emv1`](../../doc/models/emv-1.md) | Optional | - | getEmv(): ?Emv1 | setEmv(?Emv1 emv): void |
| `amexCapnData` | `?string` | Optional | Point-of-sale details for the transaction. This value is returned only for **American Express Direct**.<br>Visa Acceptance generates this value, which consists of a series of codes that identify terminal capability,<br>security data, and specific conditions present at the time the transaction occurred. To comply with the CAPN<br>requirements, this value must be included in all subsequent follow-on requests, such as captures and follow-on<br>credits.<br><br>When you perform authorizations, captures, and credits through Visa Acceptance, Visa Acceptance passes this value from<br>the authorization service to the subsequent services for you. However, when you perform authorizations through<br>Visa Acceptance and perform subsequent services through other financial institutions, you must ensure that your<br>requests for captures and credits include this value.<br><br>**Constraints**: *Maximum Length*: `15` | getAmexCapnData(): ?string | setAmexCapnData(?string amexCapnData): void |
| `terminalId` | `?string` | Optional | Identifier for the terminal at your retail location. You can define this value yourself, but consult the processor for requirements.<br><br>#### Visa Acceptance through VisaNet<br><br>A list of all possible values is stored in your Visa Acceptance account. If terminal ID validation is enabled for<br>your Visa Acceptance account, the value you send for this field is validated against the list each time you include<br>the field in a request. To enable or disable terminal ID validation, contact Visa Acceptance Customer Support.<br><br>When you do not include this field in a request, Visa Acceptance uses the default value that is defined in your Visa Acceptance account.<br><br>#### FDC Nashville Global<br><br>To have your account configured to support this field, contact Visa Acceptance Customer Support. This value must be a value that FDC Nashville Global issued to you.<br><br>#### For Payouts<br><br>This field is applicable for Visa Acceptance through VisaNet.<br><br>#### GPX<br><br>Identifier for the terminal at your retail location. A list of all possible values is stored in your account.<br>If terminal ID validation is enabled for your account, the value you send for this field is validated against<br>the list each time you include the field in a request. To enable or disable terminal ID validation, contact<br>customer support.<br><br>When you do not include this field in a request, the default value that is defined in your account is used.<br><br>Optional for authorizations.<br><br>#### Used by<br><br>**Authorization**<br>Optional for the following processors. When you do not include this field in a request, the default value that is<br>defined in your account is used.<br><br>- American Express Direct<br>- Credit Mutuel-CIC<br>- FDC Nashville Global<br>- SIX<br>- Chase Paymentech Solutions: Optional field. If you include this field in your request, you must also include `pointOfSaleInformation.catLevel`.<br>- FDMS Nashville: The default value that is defined in your account is used.<br>- GPX<br>- OmniPay Direct: Optional field.<br><br>For the following processors, this field is not used.<br><br>- GPN<br>- JCN Gateway<br>- RBS WorldPay Atlanta<br>- TSYS Acquiring Solutions<br>- Worldpay VAP<br><br>#### Card Present reply<br><br>Terminal identifier assigned by the acquirer. This value must be printed on the receipt.<br><br>**Constraints**: *Maximum Length*: `8` | getTerminalId(): ?string | setTerminalId(?string terminalId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PointOfSaleInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Emv1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$pointOfSaleInformation1 = PointOfSaleInformation1Builder::init()
    ->emv(
        Emv1Builder::init()
            ->tags('tags4')
            ->chipValidationType('chipValidationType6')
            ->chipValidationResult('chipValidationResult8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->amexCapnData('amexCapnData8')
    ->terminalId('terminalId8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

