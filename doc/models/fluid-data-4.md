
# Fluid Data 4

*This model accepts additional fields of type array.*

## Structure

`FluidData4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `descriptor` | `?string` | Optional | The identifier for a payment solution, which is sending the encrypted payment data for decryption. Valid values:<br>Samsung Pay: RklEPUNPTU1PTi5TQU1TVU5HLklOQVBQLlBBWU1FTlQ=<br>Note: For other payment solutions, the value may be specific to the terminal or device initiatinf the payment. For example, the descriptor for a Bluefin payment encryption would be a device-generated descriptor.<br>Used by Authorization and Standalone Credits. Required for authorizations and standalone credits.<br><br>Card Present processing:<br>Format of the encrypted payment data.<br>The value for Bluefin PCI P2PE is `Ymx1ZWZpbg==`. paymentInformation.fluidData.encoding must be `Base64`.<br>The value for Visa Acceptance P2PE decryption depends on the encoding method used and identified in encoding field.<br>If paymentInformation.fluidData.encoding is `Base64`, the value is: `RklEPUVNVi5QQVlNRU5ULkFQSQ==`<br>If paymentInformation.fluidData.encoding is `HEX`, the value is: `4649443D454D562E5041594D454E542E41504`<br><br>**Constraints**: *Maximum Length*: `128` | getDescriptor(): ?string | setDescriptor(?string descriptor): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\FluidData4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$fluidData4 = FluidData4Builder::init()
    ->descriptor('descriptor2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

