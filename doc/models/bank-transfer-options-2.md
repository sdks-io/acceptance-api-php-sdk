
# Bank Transfer Options 2

*This model accepts additional fields of type array.*

## Structure

`BankTransferOptions2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerMemo` | `?string` | Optional | Payment related information.<br><br>This information is included on the customer’s statement.<br><br>**Constraints**: *Maximum Length*: `80` | getCustomerMemo(): ?string | setCustomerMemo(?string customerMemo): void |
| `secCode` | `?string` | Optional | Specifies the authorization method for the transaction.<br><br>#### TeleCheck<br><br>Accepts only the following values:<br><br>- `ARC`: account receivable conversion<br>- `CCD`: corporate cash disbursement<br>- `POP`: point of purchase conversion<br>- `PPD`: prearranged payment and deposit entry<br>- `TEL`: telephone-initiated entry<br>- `WEB`: internet-initiated entry<br><br>**Constraints**: *Maximum Length*: `3` | getSecCode(): ?string | setSecCode(?string secCode): void |
| `terminalCity` | `?string` | Optional | City in which the terminal is located. If more than four alphanumeric characters are submitted, the transaction<br>will be declined.<br><br>You cannot include any special characters.<br><br>**Constraints**: *Maximum Length*: `4` | getTerminalCity(): ?string | setTerminalCity(?string terminalCity): void |
| `terminalState` | `?string` | Optional | State in which the terminal is located. If more than two alphanumeric characters are submitted, the transaction<br>will be declined.<br><br>You cannot include any special characters.<br><br>**Constraints**: *Maximum Length*: `2` | getTerminalState(): ?string | setTerminalState(?string terminalState): void |
| `effectiveDate` | `?string` | Optional | Effective date for the transaction. The effective date must be within 45 days of the current day. If you do not<br>include this value, Visa Acceptance sets the effective date to the next business day.<br><br>Format: `MMDDYYYY`<br><br>Supported only for the Visa Acceptance ACH Service.<br><br>**Constraints**: *Maximum Length*: `8` | getEffectiveDate(): ?string | setEffectiveDate(?string effectiveDate): void |
| `partialPaymentId` | `?string` | Optional | Identifier for a partial payment or partial credit.<br><br>The value for each debit request or credit request must be unique within the scope of the order.<br><br>**Constraints**: *Maximum Length*: `25` | getPartialPaymentId(): ?string | setPartialPaymentId(?string partialPaymentId): void |
| `settlementMethod` | `?string` | Optional | Method used for settlement.<br><br>Possible values:<br><br>- `A`: Automated Clearing House (default for credits and for transactions using Canadian dollars)<br>- `F`: Facsimile draft (U.S. dollars only)<br>- `B`: Best possible (U.S. dollars only) (default if the field has not already been configured for your<br>  merchant ID)<br><br>**Constraints**: *Maximum Length*: `1` | getSettlementMethod(): ?string | setSettlementMethod(?string settlementMethod): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BankTransferOptions2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bankTransferOptions2 = BankTransferOptions2Builder::init()
    ->customerMemo('customerMemo6')
    ->secCode('secCode6')
    ->terminalCity('terminalCity2')
    ->terminalState('terminalState8')
    ->effectiveDate('effectiveDate0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

