
# Merchant Descriptor 1

*This model accepts additional fields of type array.*

## Structure

`MerchantDescriptor1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `storeId` | `?string` | Optional | The identifier of the store.<br><br>**Constraints**: *Maximum Length*: `50` | getStoreId(): ?string | setStoreId(?string storeId): void |
| `storeName` | `?string` | Optional | The name of the store.<br><br>**Constraints**: *Maximum Length*: `50` | getStoreName(): ?string | setStoreName(?string storeName): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantDescriptor1 = MerchantDescriptor1Builder::init()
    ->storeId('storeId8')
    ->storeName('storeName6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

