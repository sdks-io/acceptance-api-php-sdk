
# Service

*This model accepts additional fields of type array.*

## Structure

`Service`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `categoryCode` | `?string` | Optional | Category code for the ancillary service that is provided. Obtain the codes from the International<br>Air Transport Association (IATA).<br>**Note** `#` is either 0, 1, 2, or 3.<br>**Important** This field is required in the U.S. in order for you to qualify for either the custom<br>payment service (CPS) or the electronic interchange reimbursement fee (EIRF)program.<br>Format: English characters only.<br>Optional request field for ancillary services.<br><br>**Constraints**: *Maximum Length*: `4` | getCategoryCode(): ?string | setCategoryCode(?string categoryCode): void |
| `subCategoryCode` | `?string` | Optional | Subcategory code for the ancillary service category. Obtain the codes from the International<br>Air Transport Association (IATA).<br>**Note** `#` is either 0, 1, 2, or 3.<br>Format  English characters only.<br>Optional request field for ancillary services.<br><br>**Constraints**: *Maximum Length*: `4` | getSubCategoryCode(): ?string | setSubCategoryCode(?string subCategoryCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ServiceBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$service = ServiceBuilder::init()
    ->categoryCode('categoryCode0')
    ->subCategoryCode('subCategoryCode2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

