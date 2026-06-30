
# Payments Strong Auth Issuer Information

*This model accepts additional fields of type array.*

## Structure

`PaymentsStrongAuthIssuerInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `riskAnalysisExemptionResult` | `?string` | Optional | Possible values: Visa Platform Connect<br><br>- `8401` Merchant not participating in Visa Trusted Listing Program.<br>- `8402` Issuer not participating in Visa Trusted Listing Program.<br>- `8403` Cardholder has not trusted the merchant (supplied by Visa Net).<br>- `8404` Indeterminate or invalid issuer response.<br>- `8473` Cardholder has not trusted the merchant (issuer-supplied).<br>- `8474` Did not meet the exemption criteria (issuer-supplied).<br><br>Upto 20 Values may be received in a transaction.<br><br>**Constraints**: *Maximum Length*: `80` | getRiskAnalysisExemptionResult(): ?string | setRiskAnalysisExemptionResult(?string riskAnalysisExemptionResult): void |
| `trustedMerchantExemptionResult` | `?string` | Optional | Possible values: Visa Platform Connect<br><br>- `2` Trusted merchant exemption validated/honored.<br>- `3` Trusted merchant exemption failed validation/not honored.<br><br>**Constraints**: *Maximum Length*: `4` | getTrustedMerchantExemptionResult(): ?string | setTrustedMerchantExemptionResult(?string trustedMerchantExemptionResult): void |
| `lowValueExemptionResult` | `?string` | Optional | This will be the value returned by Visanet when low value exemption has been requested.<br><br>Valid values: Visa Platform Connect<br><br>- `2` Low value exemption validated/honored<br>- `3` Low value exemption failed validation/not honored<br><br>**Constraints**: *Maximum Length*: `1` | getLowValueExemptionResult(): ?string | setLowValueExemptionResult(?string lowValueExemptionResult): void |
| `secureCorporatePaymentResult` | `?string` | Optional | This will be the value returned by Visanet when secure corporate payment (scp) exemption has been requested.<br><br>Valid values: Visa Platform Connect<br><br>- `2` Secure corporate payment exemption validated/honored<br>- `3` Secure corporate payment exemption failed validation/not honored<br><br>**Constraints**: *Maximum Length*: `1` | getSecureCorporatePaymentResult(): ?string | setSecureCorporatePaymentResult(?string secureCorporatePaymentResult): void |
| `transactionRiskAnalysisExemptionResult` | `?string` | Optional | This will be the value returned by Visanet when transaction risk analysis (TRA) exemption has been requested.<br><br>Valid values: Visa Platform Connect<br><br>- `2` transaction risk analysis (TRA) exemption validated/honored<br>- `3` transaction risk analysis (TRA) exemption failed validation/not honored<br><br>**Constraints**: *Maximum Length*: `1` | getTransactionRiskAnalysisExemptionResult(): ?string | setTransactionRiskAnalysisExemptionResult(?string transactionRiskAnalysisExemptionResult): void |
| `delegatedAuthenticationResult` | `?string` | Optional | This will be the value returned by Visanet when delegated authentication has been requested.<br><br>**Constraints**: *Maximum Length*: `1` | getDelegatedAuthenticationResult(): ?string | setDelegatedAuthenticationResult(?string delegatedAuthenticationResult): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentsStrongAuthIssuerInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentsStrongAuthIssuerInformation = PaymentsStrongAuthIssuerInformationBuilder::init()
    ->riskAnalysisExemptionResult('riskAnalysisExemptionResult4')
    ->trustedMerchantExemptionResult('trustedMerchantExemptionResult8')
    ->lowValueExemptionResult('lowValueExemptionResult0')
    ->secureCorporatePaymentResult('secureCorporatePaymentResult0')
    ->transactionRiskAnalysisExemptionResult('transactionRiskAnalysisExemptionResult0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

