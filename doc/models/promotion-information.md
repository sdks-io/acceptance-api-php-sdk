
# Promotion Information

*This model accepts additional fields of type array.*

## Structure

`PromotionInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalCode` | `?string` | Optional | Additional rental agency marketed coupons for consumers to discount the rate of the vehicle rental agreement.<br><br>**Constraints**: *Maximum Length*: `12` | getAdditionalCode(): ?string | setAdditionalCode(?string additionalCode): void |
| `code` | `?string` | Optional | Code for a promotion or discount.<br><br>**Constraints**: *Maximum Length*: `12` | getCode(): ?string | setCode(?string code): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PromotionInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$promotionInformation = PromotionInformationBuilder::init()
    ->additionalCode('additionalCode4')
    ->code('code8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

