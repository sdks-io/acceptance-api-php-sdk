
# Application Information

*This model accepts additional fields of type array.*

## Structure

`ApplicationInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | `?string` | Optional | The status of the submitted transaction. | getStatus(): ?string | setStatus(?string status): void |
| `reasonCode` | `?string` | Optional | Indicates the reason why a request succeeded or failed and possible action to take if a request fails.<br><br>For details, see the appendix of reason codes in the documentation for the relevant payment method. | getReasonCode(): ?string | setReasonCode(?string reasonCode): void |
| `rCode` | `?string` | Optional | Indicates whether the service request was successful.<br>Possible values:<br><br>- `-1`: An error occurred.<br>- `0`: The request was declined.<br>- `1`: The request was successful. | getRCode(): ?string | setRCode(?string rCode): void |
| `rFlag` | `?string` | Optional | One-word description of the result of the application. | getRFlag(): ?string | setRFlag(?string rFlag): void |
| `applications` | [`?(Application[])`](../../doc/models/application.md) | Optional | - | getApplications(): ?array | setApplications(?array applications): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ApplicationInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ApplicationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$applicationInformation = ApplicationInformationBuilder::init()
    ->status('status0')
    ->reasonCode('reasonCode2')
    ->rCode('rCode2')
    ->rFlag('rFlag2')
    ->applications(
        [
            ApplicationBuilder::init()
                ->name('name8')
                ->status('status0')
                ->reasonCode('reasonCode8')
                ->rCode('rCode8')
                ->rFlag('rFlag8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            ApplicationBuilder::init()
                ->name('name8')
                ->status('status0')
                ->reasonCode('reasonCode8')
                ->rCode('rCode8')
                ->rFlag('rFlag8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

