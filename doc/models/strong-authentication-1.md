
# Strong Authentication 1

*This model accepts additional fields of type array.*

## Structure

`StrongAuthentication1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `issuerInformation` | [`?PaymentsStrongAuthIssuerInformation`](../../doc/models/payments-strong-auth-issuer-information.md) | Optional | - | getIssuerInformation(): ?PaymentsStrongAuthIssuerInformation | setIssuerInformation(?PaymentsStrongAuthIssuerInformation issuerInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\StrongAuthentication1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentsStrongAuthIssuerInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$strongAuthentication1 = StrongAuthentication1Builder::init()
    ->issuerInformation(
        PaymentsStrongAuthIssuerInformationBuilder::init()
            ->riskAnalysisExemptionResult('riskAnalysisExemptionResult6')
            ->trustedMerchantExemptionResult('trustedMerchantExemptionResult0')
            ->lowValueExemptionResult('lowValueExemptionResult8')
            ->secureCorporatePaymentResult('secureCorporatePaymentResult2')
            ->transactionRiskAnalysisExemptionResult('transactionRiskAnalysisExemptionResult2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

