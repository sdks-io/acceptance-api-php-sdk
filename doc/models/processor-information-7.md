
# Processor Information 7

*This model accepts additional fields of type array.*

## Structure

`ProcessorInformation7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `approvalCode` | `?string` | Optional | Authorization code. Returned only when the processor returns this value.<br><br>The length of this value depends on your processor.<br><br>Returned by authorization service.<br><br>#### PIN debit<br><br>Authorization code that is returned by the processor.<br><br>Returned by PIN debit credit.<br><br>#### Elavon Encrypted Account Number Program<br><br>The returned value is OFFLINE.<br><br>#### TSYS Acquiring Solutions<br><br>The returned value for a successful zero amount authorization is 000000.<br><br>**Constraints**: *Maximum Length*: `6` | getApprovalCode(): ?string | setApprovalCode(?string approvalCode): void |
| `transactionId` | `?string` | Optional | Processor transaction ID.<br><br>This value identifies the transaction on a host system. This value is supported only for Moneris. It contains<br>this information:<br><br>- Terminal used to process the transaction<br>- Shift during which the transaction took place<br>- Batch number<br>- Transaction number within the batch<br><br>You must store this value. If you give the customer a receipt, display this value on the receipt.<br><br>Example For the value 66012345001069003:<br><br>- Terminal ID = 66012345<br>- Shift number = 001<br>- Batch number = 069<br>- Transaction number = 003<br><br>**Constraints**: *Maximum Length*: `18` | getTransactionId(): ?string | setTransactionId(?string transactionId): void |
| `forwardedAcquirerCode` | `?string` | Optional | Name of the Japanese acquirer that processed the transaction. Returned only for JCN Gateway.<br>Please contact the Visa Acceptance Japan Support Group for more information.<br><br>**Constraints**: *Maximum Length*: `32` | getForwardedAcquirerCode(): ?string | setForwardedAcquirerCode(?string forwardedAcquirerCode): void |
| `merchantNumber` | `?string` | Optional | Identifier that was assigned to you by your acquirer. This value must be printed on the receipt.<br><br>#### Returned by<br><br>Authorizations and Credits.<br><br>This reply field is only supported by merchants who have installed client software on their POS terminals and<br>use these processors:<br><br>- American Express Direct<br>- Credit Mutuel-CIC<br>- FDC Nashville Global<br>- OmniPay Direct<br>- SIX<br><br>**Constraints**: *Maximum Length*: `15` | getMerchantNumber(): ?string | setMerchantNumber(?string merchantNumber): void |
| `responseCode` | `?string` | Optional | For most processors, this is the error message sent directly from the bank. Returned only when the processor<br>returns this value.<br><br>**Important** Do not use this field to evaluate the result of the authorization.<br><br>#### PIN debit<br><br>Response value that is returned by the processor or bank.<br>**Important** Do not use this field to evaluate the results of the transaction request.<br><br>Returned by PIN debit credit, PIN debit purchase, and PIN debit reversal.<br><br>#### AIBMS<br><br>If this value is `08`, you can accept the transaction if the customer provides you with identification.<br><br>#### Atos<br><br>This value is the response code sent from Atos and it might also include the response code from the bank.<br>Format: `aa,bb` with the two values separated by a comma and where:<br><br>- `aa` is the two-digit error message from Atos.<br>- `bb` is the optional two-digit error message from the bank.<br><br>#### Comercio Latino<br><br>This value is the status code and the error or response code received from the processor separated by a colon.<br>Format: [status code]:E[error code] or [status code]:R[response code]<br>Example `2:R06`<br><br>#### JCN Gateway<br><br>Processor-defined detail error code. The associated response category code is in the `processorInformation.responseCategoryCode` field.<br>String (3)<br><br>#### paypalgateway<br><br>Processor generated ID for the itemized detail.<br><br>**Constraints**: *Maximum Length*: `10` | getResponseCode(): ?string | setResponseCode(?string responseCode): void |
| `achVerification` | [`?AchVerification`](../../doc/models/ach-verification.md) | Optional | - | getAchVerification(): ?AchVerification | setAchVerification(?AchVerification achVerification): void |
| `networkTransactionId` | `?string` | Optional | Same value as `processorInformation.transactionId` | getNetworkTransactionId(): ?string | setNetworkTransactionId(?string networkTransactionId): void |
| `settlementDate` | `?string` | Optional | Field contains a settlement date. The date is in mmdd format, where: mm = month and dd = day.<br><br>**Constraints**: *Maximum Length*: `4` | getSettlementDate(): ?string | setSettlementDate(?string settlementDate): void |
| `updateTimeUtc` | `?string` | Optional | The date and time when the transaction was last updated, in Internet date and time format. | getUpdateTimeUtc(): ?string | setUpdateTimeUtc(?string updateTimeUtc): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessorInformation7Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processorInformation7 = ProcessorInformation7Builder::init()
    ->approvalCode('approvalCode0')
    ->transactionId('transactionId0')
    ->forwardedAcquirerCode('forwardedAcquirerCode8')
    ->merchantNumber('merchantNumber8')
    ->responseCode('responseCode0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

