
# Customer 2

*This model accepts additional fields of type array.*

## Structure

`Customer2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `personalIdResult` | `?string` | Optional | Personal identifier result. This field is supported only for Redecard in Brazil for Visa Acceptance Latin<br>American Processing. If you included `buyerInformation.personalIdentification[].ID` in the request, this<br>value indicates whether or not `buyerInformation.personalIdentification[].ID` matched a value in a record<br>on file. Returned only when the personal ID result is returned by the processor.<br><br>Possible values:<br><br>- `Y`: Match<br>- `N`: No match<br>- `K`: Not supported<br>- `U`: Unknown<br>- `Z`: No response returned<br>  **Note** Visa Acceptance Latin American Processing is the name of a specific processing connection that Visa Acceptance supports. In the Visa Acceptance API documentation, Visa Acceptance Latin American Processing does not refer to the general topic of processing in Latin America.The information in this field description is for the specific processing<br>  connection called Visa Acceptance Latin American Processing. It is not for any other Latin American processors that Visa Acceptance supports.<br><br>**Constraints**: *Maximum Length*: `1` | getPersonalIdResult(): ?string | setPersonalIdResult(?string personalIdResult): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$customer2 = Customer2Builder::init()
    ->personalIdResult('personalIdResult4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

