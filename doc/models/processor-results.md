
# Processor Results

*This model accepts additional fields of type array.*

## Structure

`ProcessorResults`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fraudDecision` | `?string` | Optional | Type of filter. Possible values:<br><br>- ACCEPT<br>- PENDING<br>- DENY<br>- REPORT<br><br>**Constraints**: *Maximum Length*: `60` | getFraudDecision(): ?string | setFraudDecision(?string fraudDecision): void |
| `fraudDecisionReason` | `?string` | Optional | possible values<br><br>- AVS_NO_MATCH<br>- AVS_PARTIAL_MATCH<br>- AVS_UNAVAILABLE_OR_UNSUPPORTED<br>- CARD_SECURITY_CODE_MISMATCH<br>- MAXIMUM_TRANSACTION_AMOUNT<br>- UNCONFIRMED_ADDRESS<br>- COUNTRY_MONITOR<br>- LARGE_ORDER_NUMBER<br>- BILLING_OR_SHIPPING_ADDRESS_MISMATCH<br>- RISKY_ZIP_CODE<br>- SUSPECTED_FREIGHT_FORWARDER_CHECK<br>- TOTAL_PURCHASE_PRICE_MINIMUM<br>- IP_ADDRESS_VELOCITY<br>- RISKY_EMAIL_ADDRESS_DOMAIN_CHECK<br>- RISKY_BANK_IDENTIFICATION_NUMBER_CHECK,<br>  RISKY_IP_ADDRESS_RANGE<br>- PAYPAL_FRAUD_MODEL<br><br>**Constraints**: *Maximum Length*: `60` | getFraudDecisionReason(): ?string | setFraudDecisionReason(?string fraudDecisionReason): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessorResultsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processorResults = ProcessorResultsBuilder::init()
    ->fraudDecision('fraudDecision2')
    ->fraudDecisionReason('fraudDecisionReason0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

