
# Processor Information 18

*This model accepts additional fields of type array.*

## Structure

`ProcessorInformation18`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `approvalCode` | `?string` | Optional | Authorization code. Returned only when the processor returns this value.<br><br>The length of this value depends on your processor.<br><br>Returned by authorization service.<br><br>#### PIN debit<br><br>Authorization code that is returned by the processor.<br><br>Returned by PIN debit credit.<br><br>#### Elavon Encrypted Account Number Program<br><br>The returned value is OFFLINE.<br><br>#### TSYS Acquiring Solutions<br><br>The returned value for a successful zero amount authorization is 000000.<br><br>**Constraints**: *Maximum Length*: `6` | getApprovalCode(): ?string | setApprovalCode(?string approvalCode): void |
| `responseCode` | `?string` | Optional | For most processors, this is the error message sent directly from the bank. Returned only when the processor<br>returns this value.<br><br>**Important** Do not use this field to evaluate the result of the authorization.<br><br>#### PIN debit<br><br>Response value that is returned by the processor or bank.<br>**Important** Do not use this field to evaluate the results of the transaction request.<br><br>Returned by PIN debit credit, PIN debit purchase, and PIN debit reversal.<br><br>#### AIBMS<br><br>If this value is `08`, you can accept the transaction if the customer provides you with identification.<br><br>#### Atos<br><br>This value is the response code sent from Atos and it might also include the response code from the bank.<br>Format: `aa,bb` with the two values separated by a comma and where:<br><br>- `aa` is the two-digit error message from Atos.<br>- `bb` is the optional two-digit error message from the bank.<br><br>#### Comercio Latino<br><br>This value is the status code and the error or response code received from the processor separated by a colon.<br>Format: [status code]:E[error code] or [status code]:R[response code]<br>Example `2:R06`<br><br>#### JCN Gateway<br><br>Processor-defined detail error code. The associated response category code is in the `processorInformation.responseCategoryCode` field.<br>String (3)<br><br>#### paypalgateway<br><br>Processor generated ID for the itemized detail.<br><br>**Constraints**: *Maximum Length*: `10` | getResponseCode(): ?string | setResponseCode(?string responseCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessorInformation18Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processorInformation18 = ProcessorInformation18Builder::init()
    ->approvalCode('approvalCode8')
    ->responseCode('responseCode8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

