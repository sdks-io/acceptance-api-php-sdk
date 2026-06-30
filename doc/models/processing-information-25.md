
# Processing Information 25

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation25`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `processingInstruction` | `?string` | Optional | The instruction to process an order.<br><br>- default value: 'NO_INSTRUCTION'<br>- 'ORDER_SAVED_EXPLICITLY'<br><br>**Constraints**: *Maximum Length*: `36` | getProcessingInstruction(): ?string | setProcessingInstruction(?string processingInstruction): void |
| `authorizationOptions` | [`?AuthorizationOptions5`](../../doc/models/authorization-options-5.md) | Optional | - | getAuthorizationOptions(): ?AuthorizationOptions5 | setAuthorizationOptions(?AuthorizationOptions5 authorizationOptions): void |
| `actionList` | `?(string[])` | Optional | Array of actions (one or more) to be included in the order to invoke bundled services along with order.<br>Possible values:<br><br>- `AP_ORDER`: Use this when Alternative Payment Order service is requested. | getActionList(): ?array | setActionList(?array actionList): void |
| `highRiskTransactionFlag` | `?string` | Optional | Indicates if the transaction is flagged as high risk. | getHighRiskTransactionFlag(): ?string | setHighRiskTransactionFlag(?string highRiskTransactionFlag): void |
| `transactionRetry` | `?string` | Optional | Indicates if the transaction is a retry. | getTransactionRetry(): ?string | setTransactionRetry(?string transactionRetry): void |
| `lastOneHrTransactionCount` | `?string` | Optional | The number of transactions in the last one hour. | getLastOneHrTransactionCount(): ?string | setLastOneHrTransactionCount(?string lastOneHrTransactionCount): void |
| `lastOneDayTransactionCount` | `?string` | Optional | The number of transactions in the last one day. | getLastOneDayTransactionCount(): ?string | setLastOneDayTransactionCount(?string lastOneDayTransactionCount): void |
| `lastThreeMonthsTxnCount` | `?string` | Optional | The number of transactions in the last three months. | getLastThreeMonthsTxnCount(): ?string | setLastThreeMonthsTxnCount(?string lastThreeMonthsTxnCount): void |
| `totalTransactionCount` | `?string` | Optional | The total number of transactions. | getTotalTransactionCount(): ?string | setTotalTransactionCount(?string totalTransactionCount): void |
| `pinVerification` | `?string` | Optional | Indicates if PIN verification is required. | getPinVerification(): ?string | setPinVerification(?string pinVerification): void |
| `faceIdVerification` | `?string` | Optional | Indicates if face ID verification is required. | getFaceIdVerification(): ?string | setFaceIdVerification(?string faceIdVerification): void |
| `userPassedVerification` | `?string` | Optional | Indicates if the user passed verification. | getUserPassedVerification(): ?string | setUserPassedVerification(?string userPassedVerification): void |
| `ipAddress` | `?string` | Optional | The IP address of the user. | getIpAddress(): ?string | setIpAddress(?string ipAddress): void |
| `transactionDate` | `?string` | Optional | The date of the transaction. | getTransactionDate(): ?string | setTransactionDate(?string transactionDate): void |
| `tangible` | `?string` | Optional | Indicates if the transaction involves tangible goods. | getTangible(): ?string | setTangible(?string tangible): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation25Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationOptions5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation25 = ProcessingInformation25Builder::init()
    ->processingInstruction('processingInstruction4')
    ->authorizationOptions(
        AuthorizationOptions5Builder::init()
            ->authType('authType2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->actionList(
        [
            'actionList9',
            'actionList0',
            'actionList1'
        ]
    )
    ->highRiskTransactionFlag('highRiskTransactionFlag8')
    ->transactionRetry('transactionRetry4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

