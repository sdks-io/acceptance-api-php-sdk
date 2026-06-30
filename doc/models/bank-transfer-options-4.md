
# Bank Transfer Options 4

*This model accepts additional fields of type array.*

## Structure

`BankTransferOptions4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `secCode` | `?string` | Optional | Specifies the authorization method for the transaction.<br><br>#### TeleCheck<br><br>Possible Values:<br><br>- `ARC`: account receivable conversion<br>- `CCD`: corporate cash disbursement<br>- `POP`: point of purchase conversion<br>- `PPD`: prearranged payment and deposit entry<br>- `TEL`: telephone-initiated entry<br>- `WEB`: internet-initiated entry<br><br># For details, see `ecp_sec_code` field description in the [Electronic Check Services Using the SCMP API Guide.](<br><br>**Constraints**: *Maximum Length*: `3` | getSecCode(): ?string | setSecCode(?string secCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BankTransferOptions4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bankTransferOptions4 = BankTransferOptions4Builder::init()
    ->secCode('SECCode8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

