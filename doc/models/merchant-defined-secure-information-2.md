
# Merchant Defined Secure Information 2

*This model accepts additional fields of type array.*

## Structure

`MerchantDefinedSecureInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `secure1` | `?string` | Optional | The value you assign for your merchant-secure data field 1.<br><br>**Constraints**: *Maximum Length*: `2048` | getSecure1(): ?string | setSecure1(?string secure1): void |
| `secure2` | `?string` | Optional | The value you assign for your merchant-secure data field 2.<br><br>**Constraints**: *Maximum Length*: `2048` | getSecure2(): ?string | setSecure2(?string secure2): void |
| `secure3` | `?string` | Optional | The value you assign for your merchant-secure data field 3.<br><br>**Constraints**: *Maximum Length*: `2048` | getSecure3(): ?string | setSecure3(?string secure3): void |
| `secure4` | `?string` | Optional | The value you assign for your merchant-secure data field 4.<br><br>**Constraints**: *Maximum Length*: `2048` | getSecure4(): ?string | setSecure4(?string secure4): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDefinedSecureInformation2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantDefinedSecureInformation2 = MerchantDefinedSecureInformation2Builder::init()
    ->secure1('secure18')
    ->secure2('secure28')
    ->secure3('secure36')
    ->secure4('secure40')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

