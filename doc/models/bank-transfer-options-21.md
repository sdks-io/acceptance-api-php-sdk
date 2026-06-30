
# Bank Transfer Options 21

*This model accepts additional fields of type array.*

## Structure

`BankTransferOptions21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `secCode` | `?string` | Optional | Specifies the authorization method for the transaction.<br><br>Possible values:<br><br>- `ARC`: account receivable conversion<br>- `CCD`: corporate cash disbursement<br>- `POP`: point of purchase conversion<br>- `PPD`: prearranged payment and deposit entry<br>- `TEL`: telephone-initiated entry<br>- `WEB`: internet-initiated entry | getSecCode(): ?string | setSecCode(?string secCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BankTransferOptions21Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bankTransferOptions21 = BankTransferOptions21Builder::init()
    ->secCode('secCode0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

