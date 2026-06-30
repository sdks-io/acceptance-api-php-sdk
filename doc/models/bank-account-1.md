
# Bank Account 1

*This model accepts additional fields of type array.*

## Structure

`BankAccount1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `number` | `?string` | Optional | Account number.<br><br>When processing encoded account numbers, use this field for the encoded account number.<br><br>**Constraints**: *Maximum Length*: `17` | getNumber(): ?string | setNumber(?string number): void |
| `routingNumber` | `?string` | Optional | Bank routing number. This is also called the transit number.<br><br># For details, see `ecp_rdfi` field description in the [Electronic Check Services Using the SCMP API Guide.]( | getRoutingNumber(): ?string | setRoutingNumber(?string routingNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BankAccount1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bankAccount1 = BankAccount1Builder::init()
    ->number('number6')
    ->routingNumber('routingNumber8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

