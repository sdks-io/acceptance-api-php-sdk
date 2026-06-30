
# Strong Authentication 2

*This model accepts additional fields of type array.*

## Structure

`StrongAuthentication2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `lowValueExemptionIndicator` | `?string` | Optional | This field will contain the low value exemption indicator with one of the following values:<br>Possible values:<br><br>- `0`  ( low value exemption does not apply to the transaction)<br>- `1` (Transaction exempt from SCA as the merchant/acquirer has determined it to be a low value payment)<br><br>**Constraints**: *Maximum Length*: `1` | getLowValueExemptionIndicator(): ?string | setLowValueExemptionIndicator(?string lowValueExemptionIndicator): void |
| `riskAnalysisExemptionIndicator` | `?string` | Optional | This field will contain the transaction risk analysis exemption indicator with one of the following values:<br>Possible values:<br><br>- `0`  (TRA exemption does not apply to the transaction)<br>- `1` (Transaction exempt from SCA as the merchant/acquirer has determined it to be low risk in accordance with the criteria defined by PSD2/RTS)<br><br>**Constraints**: *Maximum Length*: `1` | getRiskAnalysisExemptionIndicator(): ?string | setRiskAnalysisExemptionIndicator(?string riskAnalysisExemptionIndicator): void |
| `trustedMerchantExemptionIndicator` | `?string` | Optional | Possible values:<br><br>- `0`  (Trusted merchant exemption does not apply to the transaction)<br>- `1` (Transaction exempt from SCA as it originated at a merchant trusted by the cardholder)<br><br>**Constraints**: *Maximum Length*: `1` | getTrustedMerchantExemptionIndicator(): ?string | setTrustedMerchantExemptionIndicator(?string trustedMerchantExemptionIndicator): void |
| `secureCorporatePaymentIndicator` | `?string` | Optional | This field will contain the secure corporate payment exemption indicator with one of the following values:<br>Possible values:<br><br>- `0`  (SCA exemption does not apply to the transaction)<br>- `1` (Transaction exempt from SCA as the merchant/acquirer has determined it as a secure corporate payment)<br><br>**Constraints**: *Maximum Length*: `1` | getSecureCorporatePaymentIndicator(): ?string | setSecureCorporatePaymentIndicator(?string secureCorporatePaymentIndicator): void |
| `delegatedAuthenticationExemptionIndicator` | `?string` | Optional | This field will contain the delegated authentication exemption indicator with one of the following values:<br>Possible values:<br><br>- `0`  (delegated Authentication exemption does not apply to the transaction)<br>- `1` (Transaction exempt from SCA as authentication has been delegated to other provider (PSP,Acquirer))<br><br>**Constraints**: *Maximum Length*: `1` | getDelegatedAuthenticationExemptionIndicator(): ?string | setDelegatedAuthenticationExemptionIndicator(?string delegatedAuthenticationExemptionIndicator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\StrongAuthentication2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$strongAuthentication2 = StrongAuthentication2Builder::init()
    ->lowValueExemptionIndicator('lowValueExemptionIndicator0')
    ->riskAnalysisExemptionIndicator('riskAnalysisExemptionIndicator0')
    ->trustedMerchantExemptionIndicator('trustedMerchantExemptionIndicator0')
    ->secureCorporatePaymentIndicator('secureCorporatePaymentIndicator6')
    ->delegatedAuthenticationExemptionIndicator('delegatedAuthenticationExemptionIndicator6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

