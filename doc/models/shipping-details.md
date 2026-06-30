
# Shipping Details

Contains shipping information not related to address.

*This model accepts additional fields of type array.*

## Structure

`ShippingDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `giftWrap` | `?bool` | Optional | Boolean that indicates whether the customer requested gift wrapping for this<br>purchase. This field can contain one of the following<br>values:<br><br>- true: The customer requested gift wrapping.<br>- false: The customer did not request gift wrapping. | getGiftWrap(): ?bool | setGiftWrap(?bool giftWrap): void |
| `shippingMethod` | `?string` | Optional | Shipping method for the product. Possible values:<br><br>- `lowcost`: Lowest-cost service<br>- `sameday`: Courier or same-day service<br>- `oneday`: Next-day or overnight service<br>- `twoday`: Two-day service<br>- `threeday`: Three-day service<br>- `pickup`: Store pick-up<br>- `other`: Other shipping method<br>- `none`: No shipping method because product is a service or subscription<br><br>**Constraints**: *Maximum Length*: `32` | getShippingMethod(): ?string | setShippingMethod(?string shippingMethod): void |
| `shipFromPostalCode` | `?string` | Optional | Postal code for the address from which the goods are shipped, which is used to establish nexus. The default is<br>the postal code associated with your Visa Acceptance account.<br><br>The postal code must consist of 5 to 9 digits. When the billing country is the U.S., the 9-digit postal code<br>must follow this format:<br><br>`[5 digits][dash][4 digits]`<br><br>Example 12345-6789<br><br>When the billing country is Canada, the 6-digit postal code must follow this format:<br><br>`[alpha][numeric][alpha][space] [numeric][alpha][numeric]`<br><br>Example A1B 2C3<br><br>This field is frequently used for Level II and Level III transactions.<br><br>**Constraints**: *Maximum Length*: `10` | getShipFromPostalCode(): ?string | setShipFromPostalCode(?string shipFromPostalCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingDetailsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shippingDetails = ShippingDetailsBuilder::init()
    ->giftWrap(false)
    ->shippingMethod('shippingMethod6')
    ->shipFromPostalCode('shipFromPostalCode8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

