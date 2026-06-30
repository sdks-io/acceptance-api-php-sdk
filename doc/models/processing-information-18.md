
# Processing Information 18

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation18`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `actionList` | `?(string[])` | Optional | Array of actions (one or more) to be included in the payment to invoke bundled services along with payment status.<br><br>Possible values are one or more of follows:<br><br>- `AP_STATUS`: Use this when Alternative Payment check status service is requested.<br><br>- `AP_SESSION_STATUS`: Use this when Alternative Payment check status service for Paypal, Klarna is requested.<br><br>- `AP_INITIATE_STATUS`: Use this when Alternative Payment check status service for KCP is requested.<br><br>- `AP_ORDER_STATUS`: Use this when Alternative Payment check status service for order status request.<br><br>- `AP_AUTH_STATUS`: Use this when Alternative Payment check status service for auth status request.<br><br>- `AP_CAPTURE_STATUS`: Use this when Alternative Payment check status service for capture status request.<br><br>- `AP_REFUND_STATUS`: Use this when Alternative Payment check status service for refund status request. | getActionList(): ?array | setActionList(?array actionList): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation18Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation18 = ProcessingInformation18Builder::init()
    ->actionList(
        [
            'actionList9',
            'actionList0'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

