
# Bill to 14

*This model accepts additional fields of type array.*

## Structure

`BillTo14`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `email` | `?string` | Optional | Email address of the PayPal account holder.<br><br>**Constraints**: *Minimum Length*: `3`, *Maximum Length*: `254` | getEmail(): ?string | setEmail(?string email): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo14Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$billTo14 = BillTo14Builder::init()
    ->email('email8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

