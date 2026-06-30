
# Velocity

*This model accepts additional fields of type array.*

## Structure

`Velocity`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `morphing` | [`?(Morphing[])`](../../doc/models/morphing.md) | Optional | List of information codes triggered by the order. These information codes were generated when you created the order and product velocity rules and are returned so that you can associate them with the rules.<br><br>Returned by scoring service. | getMorphing(): ?array | setMorphing(?array morphing): void |
| `address` | `?(string[])` | Optional | **Constraints**: *Maximum Length*: `255` | getAddress(): ?array | setAddress(?array address): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\VelocityBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MorphingBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$velocity = VelocityBuilder::init()
    ->morphing(
        [
            MorphingBuilder::init()
                ->count(234)
                ->fieldName('fieldName4')
                ->informationCode('informationCode8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            MorphingBuilder::init()
                ->count(234)
                ->fieldName('fieldName4')
                ->informationCode('informationCode8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->address(
        [
            'address0'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

