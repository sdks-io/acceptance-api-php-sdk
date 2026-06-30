
# Transaction Batch

*This model accepts additional fields of type array.*

## Structure

`TransactionBatch`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier assigned to the batch file.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `8`, *Pattern*: `^[a-zA-Z0-9_+-]*$` | getId(): ?string | setId(?string id): void |
| `uploadDate` | `?string` | Optional | Date when the batch template was update. | getUploadDate(): ?string | setUploadDate(?string uploadDate): void |
| `completionDate` | `?string` | Optional | The date when the batch template processing completed. | getCompletionDate(): ?string | setCompletionDate(?string completionDate): void |
| `transactionCount` | `?int` | Optional | Number of transactions in the transaction. | getTransactionCount(): ?int | setTransactionCount(?int transactionCount): void |
| `acceptedTransactionCount` | `?int` | Optional | Number of transactions accepted. | getAcceptedTransactionCount(): ?int | setAcceptedTransactionCount(?int acceptedTransactionCount): void |
| `rejectedTransactionCount` | `?string` | Optional | Number of transactions rejected. | getRejectedTransactionCount(): ?string | setRejectedTransactionCount(?string rejectedTransactionCount): void |
| `status` | `?string` | Optional | The status of you batch template processing. | getStatus(): ?string | setStatus(?string status): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TransactionBatchBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$transactionBatch = TransactionBatchBuilder::init()
    ->id('psy8s1d')
    ->uploadDate('2018-01-01')
    ->completionDate('2018-01-01')
    ->transactionCount(7534)
    ->acceptedTransactionCount(50013)
    ->rejectedTransactionCount('2508')
    ->status('Completed')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

