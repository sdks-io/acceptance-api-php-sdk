
# Consumer Authentication Information 4

*This model accepts additional fields of type array.*

## Structure

`ConsumerAuthenticationInformation4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eciRaw` | `?string` | Optional | Raw electronic commerce indicator (ECI).<br><br>**Constraints**: *Maximum Length*: `2` | getEciRaw(): ?string | setEciRaw(?string eciRaw): void |
| `cavv` | `?string` | Optional | Cardholder authentication verification value (CAVV).<br><br>**Constraints**: *Maximum Length*: `40` | getCavv(): ?string | setCavv(?string cavv): void |
| `xid` | `?string` | Optional | Transaction identifier.<br><br>**Constraints**: *Maximum Length*: `40` | getXid(): ?string | setXid(?string xid): void |
| `transactionId` | `?string` | Optional | Payer auth Transaction identifier. | getTransactionId(): ?string | setTransactionId(?string transactionId): void |
| `strongAuthentication` | [`?StrongAuthentication2`](../../doc/models/strong-authentication-2.md) | Optional | - | getStrongAuthentication(): ?StrongAuthentication2 | setStrongAuthentication(?StrongAuthentication2 strongAuthentication): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ConsumerAuthenticationInformation4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\StrongAuthentication2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$consumerAuthenticationInformation4 = ConsumerAuthenticationInformation4Builder::init()
    ->eciRaw('eciRaw2')
    ->cavv('cavv8')
    ->xid('xid0')
    ->transactionId('transactionId2')
    ->strongAuthentication(
        StrongAuthentication2Builder::init()
            ->lowValueExemptionIndicator('lowValueExemptionIndicator0')
            ->riskAnalysisExemptionIndicator('riskAnalysisExemptionIndicator0')
            ->trustedMerchantExemptionIndicator('trustedMerchantExemptionIndicator0')
            ->secureCorporatePaymentIndicator('secureCorporatePaymentIndicator6')
            ->delegatedAuthenticationExemptionIndicator('delegatedAuthenticationExemptionIndicator6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

