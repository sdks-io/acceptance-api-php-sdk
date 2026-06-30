
# Customer 1

*This model accepts additional fields of type array.*

## Structure

`Customer1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional | This is the endpoint of the resource that was created by the successful request. | getHref(): ?string | setHref(?string href): void |
| `method` | `?string` | Optional | `method` refers to the HTTP method that you can send to the `self` endpoint to retrieve details of the resource. | getMethod(): ?string | setMethod(?string method): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$customer1 = Customer1Builder::init()
    ->href('href8')
    ->method('method0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

