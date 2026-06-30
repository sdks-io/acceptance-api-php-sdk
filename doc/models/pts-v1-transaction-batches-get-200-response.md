
# Pts V1 Transaction Batches Get 200 Response

*This model accepts additional fields of type array.*

## Structure

`PtsV1TransactionBatchesGet200Response`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionBatches` | [`?(TransactionBatch[])`](../../doc/models/transaction-batch.md) | Optional | - | getTransactionBatches(): ?array | setTransactionBatches(?array transactionBatches): void |
| `links` | [`?Links13`](../../doc/models/links-13.md) | Optional | - | getLinks(): ?Links13 | setLinks(?Links13 links): void |
| `submitTimeUtc` | `?string` | Optional | Time of request in UTC. Format: `YYYY-MM-DDThh:mm:ssZ`<br>**Example** `2016-08-11T22:47:57Z` equals August 11, 2016, at 22:47:57 (10:47:57 p.m.).<br>The `T` separates the date and the time. The `Z` indicates UTC.<br><br>Returned by Visa Acceptance for all services. | getSubmitTimeUtc(): ?string | setSubmitTimeUtc(?string submitTimeUtc): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PtsV1TransactionBatchesGet200ResponseBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TransactionBatchBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links13Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self13Builder;

$ptsV1TransactionBatchesGet200Response = PtsV1TransactionBatchesGet200ResponseBuilder::init()
    ->transactionBatches(
        [
            TransactionBatchBuilder::init()
                ->id('id0')
                ->uploadDate('uploadDate2')
                ->completionDate('completionDate0')
                ->transactionCount(94)
                ->acceptedTransactionCount(38)
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            TransactionBatchBuilder::init()
                ->id('id0')
                ->uploadDate('uploadDate2')
                ->completionDate('completionDate0')
                ->transactionCount(94)
                ->acceptedTransactionCount(38)
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            TransactionBatchBuilder::init()
                ->id('id0')
                ->uploadDate('uploadDate2')
                ->completionDate('completionDate0')
                ->transactionCount(94)
                ->acceptedTransactionCount(38)
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->links(
        Links13Builder::init()
            ->self(
                Self13Builder::init()
                    ->href('href0')
                    ->method('method8')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->submitTimeUtc('submitTimeUtc8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

