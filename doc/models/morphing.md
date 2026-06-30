
# Morphing

*This model accepts additional fields of type array.*

## Structure

`Morphing`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `count` | `?int` | Optional | Morphing count specified by the number #.<br><br>**Note** The count is not returned for the initial transaction. | getCount(): ?int | setCount(?int count): void |
| `fieldName` | `?string` | Optional | Field name of the morphing element. specified by the setting that you chose in the<br>Velocity Editor.<br><br>For all possible values, see the `decisionReply_morphingElement_#_fieldName` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.]( Click **Decision Manager** > **Documentation** > **Guides** > _Decision Manager Using the SCMP API Developer Guide_ (PDF link).<br><br>**Constraints**: *Maximum Length*: `255` | getFieldName(): ?string | setFieldName(?string fieldName): void |
| `informationCode` | `?string` | Optional | Identifier that Visa Acceptance assigned to the velocity rule specified by the number #.<br><br>For all possible values, see the `decision_velocity_morphing_#_info_code` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.]( Click **Decision Manager** ><br><br>**Constraints**: *Maximum Length*: `255` | getInformationCode(): ?string | setInformationCode(?string informationCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MorphingBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$morphing = MorphingBuilder::init()
    ->count(234)
    ->fieldName('fieldName4')
    ->informationCode('informationCode8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

