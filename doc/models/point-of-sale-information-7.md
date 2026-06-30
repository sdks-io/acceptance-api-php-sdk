
# Point of Sale Information 7

*This model accepts additional fields of type array.*

## Structure

`PointOfSaleInformation7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `terminalId` | `?string` | Optional | Identifier for the terminal at your retail location. You can define this value yourself, but consult the processor for requirements.<br><br>#### Visa Acceptance through VisaNet<br><br>A list of all possible values is stored in your Visa Acceptance account. If terminal ID validation is enabled for<br>your Visa Acceptance account, the value you send for this field is validated against the list each time you include<br>the field in a request. To enable or disable terminal ID validation, contact Visa Acceptance Customer Support.<br><br>When you do not include this field in a request, Visa Acceptance uses the default value that is defined in your Visa Acceptance account.<br><br>#### FDC Nashville Global<br><br>To have your account configured to support this field, contact Visa Acceptance Customer Support. This value must be a value that FDC Nashville Global issued to you.<br><br>#### For Payouts<br><br>This field is applicable for Visa Acceptance through VisaNet.<br><br>#### GPX<br><br>Identifier for the terminal at your retail location. A list of all possible values is stored in your account.<br>If terminal ID validation is enabled for your account, the value you send for this field is validated against<br>the list each time you include the field in a request. To enable or disable terminal ID validation, contact<br>customer support.<br><br>When you do not include this field in a request, the default value that is defined in your account is used.<br><br>Optional for authorizations.<br><br>#### Used by<br><br>**Authorization**<br>Optional for the following processors. When you do not include this field in a request, the default value that is<br>defined in your account is used.<br><br>- American Express Direct<br>- Credit Mutuel-CIC<br>- FDC Nashville Global<br>- SIX<br>- Chase Paymentech Solutions: Optional field. If you include this field in your request, you must also include `pointOfSaleInformation.catLevel`.<br>- FDMS Nashville: The default value that is defined in your account is used.<br>- GPX<br>- OmniPay Direct: Optional field.<br><br>For the following processors, this field is not used.<br><br>- GPN<br>- JCN Gateway<br>- RBS WorldPay Atlanta<br>- TSYS Acquiring Solutions<br>- Worldpay VAP<br><br>#### Card Present reply<br><br>Terminal identifier assigned by the acquirer. This value must be printed on the receipt.<br><br>**Constraints**: *Maximum Length*: `8` | getTerminalId(): ?string | setTerminalId(?string terminalId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PointOfSaleInformation7Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$pointOfSaleInformation7 = PointOfSaleInformation7Builder::init()
    ->terminalId('terminalId8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

