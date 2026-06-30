
# Point of Sale Information 14

*This model accepts additional fields of type array.*

## Structure

`PointOfSaleInformation14`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `terminalId` | `?string` | Optional | Identifier for the terminal at your retail location. You can define this value yourself, but consult the processor for requirements.<br><br>#### Visa Acceptance through VisaNet<br><br>A list of all possible values is stored in your Visa Acceptance account. If terminal ID validation is enabled for<br>your Visa Acceptance account, the value you send for this field is validated against the list each time you include<br>the field in a request. To enable or disable terminal ID validation, contact Visa Acceptance Customer Support.<br><br>When you do not include this field in a request, Visa Acceptance uses the default value that is defined in your Visa Acceptance account.<br><br>#### FDC Nashville Global<br><br>To have your account configured to support this field, contact Visa Acceptance Customer Support. This value must be a value that FDC Nashville Global issued to you.<br><br>#### For Payouts<br><br>This field is applicable for Visa Acceptance through VisaNet.<br><br>#### GPX<br><br>Identifier for the terminal at your retail location. A list of all possible values is stored in your account.<br>If terminal ID validation is enabled for your account, the value you send for this field is validated against<br>the list each time you include the field in a request. To enable or disable terminal ID validation, contact<br>customer support.<br><br>When you do not include this field in a request, the default value that is defined in your account is used.<br><br>Optional for authorizations.<br><br>#### Used by<br><br>**Authorization**<br>Optional for the following processors. When you do not include this field in a request, the default value that is<br>defined in your account is used.<br><br>- American Express Direct<br>- Credit Mutuel-CIC<br>- FDC Nashville Global<br>- SIX<br>- Chase Paymentech Solutions: Optional field. If you include this field in your request, you must also include `pointOfSaleInformation.catLevel`.<br>- FDMS Nashville: The default value that is defined in your account is used.<br>- GPX<br>- OmniPay Direct: Optional field.<br><br>For the following processors, this field is not used.<br><br>- GPN<br>- JCN Gateway<br>- RBS WorldPay Atlanta<br>- TSYS Acquiring Solutions<br>- Worldpay VAP<br><br>#### Card Present reply<br><br>Terminal identifier assigned by the acquirer. This value must be printed on the receipt.<br><br>**Constraints**: *Maximum Length*: `8` | getTerminalId(): ?string | setTerminalId(?string terminalId): void |
| `entryMode` | `?string` | Optional | Method of entering payment card information into the POS terminal. Possible values:<br><br>- `contact`: Read from direct contact with chip card.<br>- `contactless`: Read from a contactless interface using chip data.<br>- `keyed`: Manually keyed into POS terminal. This value is not supported on OmniPay Direct.<br>- `msd`: Read from a contactless interface using magnetic stripe data (MSD). This value is not supported on OmniPay Direct.<br>- `swiped`: Read from credit card magnetic stripe.<br><br>The `contact`, `contactless`, and `msd` values are supported only for EMV transactions.<br><br>#### Used by<br><br>**Authorization**<br>Required field.<br><br>#### Card Present<br><br>Card present information about EMV applies only to credit card processing and PIN debit processing. All other<br>card present information applies only to credit card processing.<br><br>#### PIN debit<br><br>Required for a PIN debit purchase and a PIN debit credit request.<br><br>**Constraints**: *Maximum Length*: `11` | getEntryMode(): ?string | setEntryMode(?string entryMode): void |
| `terminalCapability` | `?int` | Optional | POS terminal’s capability. Possible values:<br><br>- `1`: Terminal has a magnetic stripe reader only.<br>- `2`: Terminal has a magnetic stripe reader and manual entry capability.<br>- `3`: Terminal has manual entry capability only.<br>- `4`: Terminal can read chip cards.<br>- `5`: Terminal can read contactless chip cards; cannot use contact to read chip cards.<br><br>For an EMV transaction, the value of this field must be `4` or `5`.<br><br>#### PIN debit<br><br>Required for PIN debit purchase and PIN debit credit request.<br><br>#### Used by<br><br>**Authorization**<br>Required for the following processors:<br><br>- American Express Direct<br>- Chase Paymentech Solutions<br>- Credit Mutuel-CIC<br>- FDC Nashville Global<br>- FDMS Nashville<br>- OmniPay Direct<br>- SIX<br>- Worldpay VAP<br><br>Optional for the following processors:<br><br>- Visa Acceptance through VisaNet<br>- GPN<br>- GPX<br>- JCN Gateway<br>- RBS WorldPay Atlanta<br>- TSYS Acquiring Solutions<br><br>**Constraints**: `>= 1`, `<= 5` | getTerminalCapability(): ?int | setTerminalCapability(?int terminalCapability): void |
| `cardholderVerificationMethodUsed` | `?int` | Optional | Method that was used to verify the cardholder's identity. Possible values:<br><br>- `0`: No verification<br>- `1`: Signature<br>- `2`: PIN<br>- `3`: Cardholder device CVM<br>- `4`: Biometric<br>- `5`: OTP | getCardholderVerificationMethodUsed(): ?int | setCardholderVerificationMethodUsed(?int cardholderVerificationMethodUsed): void |
| `emv` | [`?Emv2`](../../doc/models/emv-2.md) | Optional | - | getEmv(): ?Emv2 | setEmv(?Emv2 emv): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PointOfSaleInformation14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Emv2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$pointOfSaleInformation14 = PointOfSaleInformation14Builder::init()
    ->terminalId('terminalId4')
    ->entryMode('entryMode0')
    ->terminalCapability(5)
    ->cardholderVerificationMethodUsed(178)
    ->emv(
        Emv2Builder::init()
            ->tags('tags4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

