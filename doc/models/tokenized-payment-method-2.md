
# Tokenized Payment Method 2

*This model accepts additional fields of type array.*

## Structure

`TokenizedPaymentMethod2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Description of the vaulted payment method shown to the buyer during checkout and in their PayPal account.<br><br>**Constraints**: *Maximum Length*: `128` | getDescription(): ?string | setDescription(?string description): void |
| `usagePattern` | `?string` | Optional | Indicates how the merchant will primarily use the vaulted payment method. Valid values:<br><br>- “IMMEDIATE”: For on-demand, instant payments. These payments are variable in both amount and frequency and will be used to pay for goods or services before they are rendered to the buyer<br>- “DEFERRED”: For post-pay payments; that is, payments for goods or services that have already been rendered to the buyer<br>- “RECURRING_PREPAID”: For recurring payments before services are rendered.<br>- “RECURRING_POSTPAID”: For recurring payments after services are rendered.<br>- “THRESHOLD_PREPAID”: For payments when a pre-defined threshold is reached before services are rendered.<br>- “THRESHOLD_POSTPAID”: For payments when a pre-defined threshold is reached after services are rendered.<br><br>**Constraints**: *Maximum Length*: `30` | getUsagePattern(): ?string | setUsagePattern(?string usagePattern): void |
| `usageType` | `?string` | Optional | Indicates the type of vaulting relationship. Valid values:<br><br>- “MERCHANT”: Single merchant relationship.<br>- “PLATFORM”: Platform hosting multiple merchants.<br><br>**Constraints**: *Maximum Length*: `255` | getUsageType(): ?string | setUsageType(?string usageType): void |
| `allowMultipleTokens` | `?bool` | Optional | Create multiple payment tokens for the same payer, merchant/platform combination. This helps to identify customers distinctly even though they may share the same PayPal account. | getAllowMultipleTokens(): ?bool | setAllowMultipleTokens(?bool allowMultipleTokens): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethod2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$tokenizedPaymentMethod2 = TokenizedPaymentMethod2Builder::init()
    ->description('description2')
    ->usagePattern('usagePattern0')
    ->usageType('usageType2')
    ->allowMultipleTokens(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

