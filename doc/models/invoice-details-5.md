
# Invoice Details 5

*This model accepts additional fields of type array.*

## Structure

`InvoiceDetails5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `level3TransmissionStatus` | `?bool` | Optional | Indicates whether Visa Acceptance sent the Level III information to the processor. The possible values are:<br><br>If your account is not enabled for Level III data or if you did not include the purchasing level field in your<br>request, Visa Acceptance does not include the Level III data in the request sent to the processor.<br><br>Possible values:<br><br>- **true**<br>- **false** | getLevel3TransmissionStatus(): ?bool | setLevel3TransmissionStatus(?bool level3TransmissionStatus): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$invoiceDetails5 = InvoiceDetails5Builder::init()
    ->level3TransmissionStatus(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

