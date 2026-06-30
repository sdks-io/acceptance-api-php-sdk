
# Shipping Address List for Customer

A paginated container of Shipping Addresses.

*This model accepts additional fields of type array.*

## Structure

`ShippingAddressListForCustomer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?Links66`](../../doc/models/links-66.md) | Optional, Read-only | - | getLinks(): ?Links66 | setLinks(?Links66 links): void |
| `offset` | `?int` | Optional, Read-only | The offset parameter supplied in the request.<br><br>**Default**: `0` | getOffset(): ?int | setOffset(?int offset): void |
| `limit` | `?int` | Optional, Read-only | The limit parameter supplied in the request.<br><br>**Default**: `20` | getLimit(): ?int | setLimit(?int limit): void |
| `count` | `?int` | Optional, Read-only | The number of Shipping Addresses returned in the array. | getCount(): ?int | setCount(?int count): void |
| `total` | `?int` | Optional, Read-only | The total number of Shipping Addresses associated with the Customer. | getTotal(): ?int | setTotal(?int total): void |
| `embedded` | [`?Embedded8`](../../doc/models/embedded-8.md) | Optional, Read-only | - | getEmbedded(): ?Embedded8 | setEmbedded(?Embedded8 embedded): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingAddressListForCustomerBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links66Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self65Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\FirstBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PrevBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\NextBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LastBuilder;

$shippingAddressListForCustomer = ShippingAddressListForCustomerBuilder::init()
    ->links(
        Links66Builder::init()
            ->self(
                Self65Builder::init()
                    ->href('href0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->first(
                FirstBuilder::init()
                    ->href('href2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->prev(
                PrevBuilder::init()
                    ->href('href8')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->next(
                NextBuilder::init()
                    ->href('href4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->last(
                LastBuilder::init()
                    ->href('href2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->offset(0)
    ->limit(20)
    ->count(1)
    ->total(1)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

