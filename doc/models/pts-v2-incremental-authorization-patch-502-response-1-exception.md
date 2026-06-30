
# Pts V2 Incremental Authorization Patch 502 Response 1 Exception

*This model accepts additional fields of type array.*

## Structure

`PtsV2IncrementalAuthorizationPatch502Response1Exception`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `submitTimeUtc` | `?string` | Optional | Time of request in UTC. Format: `YYYY-MM-DDThh:mm:ssZ`<br>**Example** `2016-08-11T22:47:57Z` equals August 11, 2016, at 22:47:57 (10:47:57 p.m.).<br>The `T` separates the date and the time. The `Z` indicates UTC.<br><br>Returned by Visa Acceptance for all services. | getSubmitTimeUtc(): ?string | setSubmitTimeUtc(?string submitTimeUtc): void |
| `status` | `?string` | Optional | The status of the submitted transaction.<br><br>Possible values:<br><br>- SERVER_ERROR | getStatus(): ?string | setStatus(?string status): void |
| `reason` | `?string` | Optional | The reason of the status.<br><br>Possible values:<br><br>- SYSTEM_ERROR<br>- SERVER_TIMEOUT<br>- SERVICE_TIMEOUT | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The detail message related to the status and reason listed above. | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

