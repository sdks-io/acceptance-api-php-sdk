
# Installment Information 10

*This model accepts additional fields of type array.*

## Structure

`InstallmentInformation10`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `numberOfInstallments` | `?string` | Optional | Number of Installments. | getNumberOfInstallments(): ?string | setNumberOfInstallments(?string numberOfInstallments): void |
| `identifier` | `?string` | Optional | Standing Instruction/Installment identifier. | getIdentifier(): ?string | setIdentifier(?string identifier): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InstallmentInformation10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$installmentInformation10 = InstallmentInformation10Builder::init()
    ->numberOfInstallments('numberOfInstallments4')
    ->identifier('identifier8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

