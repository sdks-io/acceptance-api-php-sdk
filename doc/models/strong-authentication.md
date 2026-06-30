
# Strong Authentication

*This model accepts additional fields of type array.*

## Structure

`StrongAuthentication`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `issuerInformation` | [`?IssuerInformation1`](../../doc/models/issuer-information-1.md) | Optional | - | getIssuerInformation(): ?IssuerInformation1 | setIssuerInformation(?IssuerInformation1 issuerInformation): void |
| `lowValueExemptionIndicator` | `?string` | Optional | This field will contain the low value exemption indicator with one of the following values:<br>Possible values:<br><br>- `0`  ( low value exemption does not apply to the transaction)<br>- `1` (Transaction exempt from SCA as the merchant/acquirer has determined it to be a low value payment)<br><br>**Constraints**: *Maximum Length*: `1` | getLowValueExemptionIndicator(): ?string | setLowValueExemptionIndicator(?string lowValueExemptionIndicator): void |
| `riskAnalysisExemptionIndicator` | `?string` | Optional | This field will contain the transaction risk analysis exemption indicator with one of the following values:<br>Possible values:<br><br>- `0`  (TRA exemption does not apply to the transaction)<br>- `1` (Transaction exempt from SCA as the merchant/acquirer has determined it to be low risk in accordance with the criteria defined by PSD2/RTS)<br><br>**Constraints**: *Maximum Length*: `1` | getRiskAnalysisExemptionIndicator(): ?string | setRiskAnalysisExemptionIndicator(?string riskAnalysisExemptionIndicator): void |
| `trustedMerchantExemptionIndicator` | `?string` | Optional | Possible values:<br><br>- `0`  (Trusted merchant exemption does not apply to the transaction)<br>- `1` (Transaction exempt from SCA as it originated at a merchant trusted by the cardholder)<br><br>**Constraints**: *Maximum Length*: `1` | getTrustedMerchantExemptionIndicator(): ?string | setTrustedMerchantExemptionIndicator(?string trustedMerchantExemptionIndicator): void |
| `secureCorporatePaymentIndicator` | `?string` | Optional | This field will contain the secure corporate payment exemption indicator with one of the following values:<br>Possible values:<br><br>- `0`  (SCA exemption does not apply to the transaction)<br>- `1` (Transaction exempt from SCA as the merchant/acquirer has determined it as a secure corporate payment)<br><br>**Constraints**: *Maximum Length*: `1` | getSecureCorporatePaymentIndicator(): ?string | setSecureCorporatePaymentIndicator(?string secureCorporatePaymentIndicator): void |
| `delegatedAuthenticationExemptionIndicator` | `?string` | Optional | This field will contain the delegated authentication exemption indicator with one of the following values:<br>Possible values:<br><br>- `0`  (delegated Authentication exemption does not apply to the transaction)<br>- `1` (Transaction exempt from SCA as authentication has been delegated to other provider (PSP,Acquirer))<br><br>**Constraints**: *Maximum Length*: `1` | getDelegatedAuthenticationExemptionIndicator(): ?string | setDelegatedAuthenticationExemptionIndicator(?string delegatedAuthenticationExemptionIndicator): void |
| `outageExemptionIndicator` | `?string` | Optional | This field will contain the outage exemption indicator with one of the following values:<br>Possible values:<br><br>- `0`  (Outage Authentication exemption does not apply to the transaction)<br>- `1` (Outage exempt from SCA as authentication could not be done due to outage)<br><br>**Constraints**: *Maximum Length*: `1` | getOutageExemptionIndicator(): ?string | setOutageExemptionIndicator(?string outageExemptionIndicator): void |
| `authenticationIndicator` | `?string` | Optional | Indicates the type of Authentication request<br><br>01 - Payment transaction<br><br>02 - Recurring transaction<br><br>03 - Installment transaction<br><br>04 - Add card<br><br>05 - Maintain card<br><br>06 - Cardholder verification as part of EMV token ID and V<br><br>**Constraints**: *Maximum Length*: `2` | getAuthenticationIndicator(): ?string | setAuthenticationIndicator(?string authenticationIndicator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\StrongAuthenticationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerInformation1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$strongAuthentication = StrongAuthenticationBuilder::init()
    ->issuerInformation(
        IssuerInformation1Builder::init()
            ->exemptionDataRaw('exemptionDataRaw0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->lowValueExemptionIndicator('lowValueExemptionIndicator0')
    ->riskAnalysisExemptionIndicator('riskAnalysisExemptionIndicator0')
    ->trustedMerchantExemptionIndicator('trustedMerchantExemptionIndicator0')
    ->secureCorporatePaymentIndicator('secureCorporatePaymentIndicator6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

