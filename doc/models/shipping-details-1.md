
# Shipping Details 1

*This model accepts additional fields of type array.*

## Structure

`ShippingDetails1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `shipFromPostalCode` | `?string` | Optional | Postal code for the address from which the goods are shipped, which is used to establish nexus. The default is<br>the postal code associated with your Visa Acceptance account.<br><br>The postal code must consist of 5 to 9 digits. When the billing country is the U.S., the 9-digit postal code<br>must follow this format:<br><br>`[5 digits][dash][4 digits]`<br><br>Example 12345-6789<br><br>When the billing country is Canada, the 6-digit postal code must follow this format:<br><br>`[alpha][numeric][alpha][space] [numeric][alpha][numeric]`<br><br>Example A1B 2C3<br><br>This field is frequently used for Level II and Level III transactions.<br><br>**Constraints**: *Maximum Length*: `10` | getShipFromPostalCode(): ?string | setShipFromPostalCode(?string shipFromPostalCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingDetails1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shippingDetails1 = ShippingDetails1Builder::init()
    ->shipFromPostalCode('shipFromPostalCode8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

