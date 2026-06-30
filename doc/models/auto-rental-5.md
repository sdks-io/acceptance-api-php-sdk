
# Auto Rental 5

*This model accepts additional fields of type array.*

## Structure

`AutoRental5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `companyName` | `?string` | Optional | Merchant to send their auto rental company name<br><br>**Constraints**: *Maximum Length*: `50` | getCompanyName(): ?string | setCompanyName(?string companyName): void |
| `affiliateName` | `?string` | Optional | When merchant wants to send the affiliate name.<br><br>**Constraints**: *Maximum Length*: `50` | getAffiliateName(): ?string | setAffiliateName(?string affiliateName): void |
| `rentalAddress` | [`?RentalAddress`](../../doc/models/rental-address.md) | Optional | - | getRentalAddress(): ?RentalAddress | setRentalAddress(?RentalAddress rentalAddress): void |
| `returnAddress` | [`?ReturnAddress`](../../doc/models/return-address.md) | Optional | - | getReturnAddress(): ?ReturnAddress | setReturnAddress(?ReturnAddress returnAddress): void |
| `returnDateTime` | `?string` | Optional | Date/time the auto was returned to the rental agency.<br>Format: `yyyy-MM-dd HH-mm-ss z`<br>This field is supported for Visa, MasterCard, and American Express.<br><br>**Constraints**: *Maximum Length*: `21` | getReturnDateTime(): ?string | setReturnDateTime(?string returnDateTime): void |
| `rentalDateTime` | `?string` | Optional | Date/time the auto was picked up from the rental agency.<br>Format: `yyyy-MM-dd HH-mm-ss z`<br>This field is supported for Visa, MasterCard, and American Express.<br><br>**Constraints**: *Maximum Length*: `21` | getRentalDateTime(): ?string | setRentalDateTime(?string rentalDateTime): void |
| `customerName` | `?string` | Optional | Name of the individual making the rental agreement.<br><br>Valid data lengths by card:<br><br>\|Card Specific Validation\|VISA\|MasterCard\|Discover\|AMEX\|<br>\|--- \|--- \|--- \|--- \|<br>\| Filed Length\| 40\| 40\| 29\| 26\|<br>\| Field Type\| AN\| ANS\| AN\| AN\|<br>\| M/O/C\| O\| M\| M\| M\|<br><br>**Constraints**: *Maximum Length*: `40` | getCustomerName(): ?string | setCustomerName(?string customerName): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AutoRental5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\RentalAddressBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ReturnAddressBuilder;

$autoRental5 = AutoRental5Builder::init()
    ->companyName('companyName0')
    ->affiliateName('affiliateName2')
    ->rentalAddress(
        RentalAddressBuilder::init()
            ->city('city6')
            ->state('state0')
            ->country('country8')
            ->locationId('locationId6')
            ->address1('address12')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->returnAddress(
        ReturnAddressBuilder::init()
            ->city('city0')
            ->state('state4')
            ->country('country4')
            ->locationId('locationId2')
            ->address1('address12')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->returnDateTime('returnDateTime0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

