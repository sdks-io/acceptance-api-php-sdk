
# Refund

*This model accepts additional fields of type array.*

## Structure

`Refund`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | This is the endpoint of the resource that was created by the successful request. | getHref(): ?string | setHref(?string href): void |
| `method` | `?string` | Optional | `method` refers to the HTTP method that you can send to the `self` endpoint to retrieve details of the resource. | getMethod(): ?string | setMethod(?string method): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RefundBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$refund = RefundBuilder::init()
    ->href('href0')
    ->method('method2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

