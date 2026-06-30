
# Weights

*This model accepts additional fields of type array.*

## Structure

`Weights`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | `?string` | Optional | Degree of correlation between a customer’s address and an entry in the DPL<br>before a match occurs. This field can contain one of the following values:<br><br>- exact: The address must be identical to the entry in the DPL.<br>- high: (default) The address cannot differ significantly from the entry in the DPL.<br>- medium: The address can differ slightly more from the entry in the DPL.<br>- low: The address can differ significantly from the entry in the DPL.<br><br>**Constraints**: *Maximum Length*: `6` | getAddress(): ?string | setAddress(?string address): void |
| `company` | `?string` | Optional | Degree of correlation between a company address and an entry in the DPL<br>before a match occurs. This field can contain one of the following values:<br><br>- exact: The company name must be identical to the entry in the DPL.<br>- high: (default) The company name cannot differ significantly from the entry in the DPL.<br>- medium: The company name can differ slightly more from the entry in the DPL.<br>- low: The company name can differ significantly from the entry in the DPL.<br><br>**Constraints**: *Maximum Length*: `6` | getCompany(): ?string | setCompany(?string company): void |
| `name` | `?string` | Optional | Degree of correlation between a customer’s name and an entry in the DPL<br>before a match occurs. This field can contain one of the following values:<br><br>- exact: The name must be identical to the entry in the DPL.<br>- high: (default) The name cannot differ significantly from the entry in the DPL.<br>- medium: The name can differ slightly more from the entry in the DPL.<br>- low: The name can differ significantly the entry in the DPL.<br><br>**Constraints**: *Maximum Length*: `6` | getName(): ?string | setName(?string name): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\WeightsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$weights = WeightsBuilder::init()
    ->address('address2')
    ->company('company4')
    ->name('name6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

