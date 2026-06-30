
# Transaction Advice Addendum

*This model accepts additional fields of type array.*

## Structure

`TransactionAdviceAddendum`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | `?string` | Optional | Four Transaction Advice Addendum (TAA) fields. These fields are used to display descriptive information<br>about a transaction on the customer’s American Express card statement. When you send TAA fields, start<br>with amexdata_taa1, then ...taa2, and so on. Skipping a TAA field causes subsequent TAA fields to be<br>ignored.<br><br>To use these fields, contact Visa Acceptance Customer Support to have your account enabled for this feature.<br><br>**Constraints**: *Maximum Length*: `40` | getData(): ?string | setData(?string data): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TransactionAdviceAddendumBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$transactionAdviceAddendum = TransactionAdviceAddendumBuilder::init()
    ->data('data8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

