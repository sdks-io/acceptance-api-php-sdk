
# Pts V1 Transaction Batches Get 404 Response 1 Exception

*This model accepts additional fields of type array.*

## Structure

`PtsV1TransactionBatchesGet404Response1Exception`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorInformation` | [`?ErrorInformation2`](../../doc/models/error-information-2.md) | Optional | - | getErrorInformation(): ?ErrorInformation2 | setErrorInformation(?ErrorInformation2 errorInformation): void |
| `submitTimeUtc` | `?string` | Optional | Time of request in UTC. Format: `YYYY-MM-DDThh:mm:ssZ`<br>**Example** `2016-08-11T22:47:57Z` equals August 11, 2016, at 22:47:57 (10:47:57 p.m.).<br>The `T` separates the date and the time. The `Z` indicates UTC.<br><br>Returned by Visa Acceptance for all services. | getSubmitTimeUtc(): ?string | setSubmitTimeUtc(?string submitTimeUtc): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

