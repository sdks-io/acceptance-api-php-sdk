
# Pts V1 Transaction Batches Get 500 Response 1 Exception

*This model accepts additional fields of type array.*

## Structure

`PtsV1TransactionBatchesGet500Response1Exception`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorInformation` | [`?ErrorInformation6`](../../doc/models/error-information-6.md) | Optional | - | getErrorInformation(): ?ErrorInformation6 | setErrorInformation(?ErrorInformation6 errorInformation): void |
| `submitTimeUtc` | `?string` | Optional | Time of request in UTC. Format: `YYYY-MM-DDThh:mm:ssZ`<br>**Example** `2016-08-11T22:47:57Z` equals August 11, 2016, at 22:47:57 (10:47:57 p.m.).<br>The `T` separates the date and the time. The `Z` indicates UTC.<br><br>Returned by Visa Acceptance for all services. | getSubmitTimeUtc(): ?string | setSubmitTimeUtc(?string submitTimeUtc): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

