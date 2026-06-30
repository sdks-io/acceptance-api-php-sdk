
# Ivr

*This model accepts additional fields of type array.*

## Structure

`Ivr`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enabledMessage` | `?bool` | Optional | Flag to indicate if a valid IVR transaction was detected. | getEnabledMessage(): ?bool | setEnabledMessage(?bool enabledMessage): void |
| `encryptionKey` | `?string` | Optional | Encryption key to be used in the event the ACS requires encryption of the credential field.<br><br>**Constraints**: *Maximum Length*: `16` | getEncryptionKey(): ?string | setEncryptionKey(?string encryptionKey): void |
| `encryptionMandatory` | `?bool` | Optional | Flag to indicate if the ACS requires the credential to be encrypted. | getEncryptionMandatory(): ?bool | setEncryptionMandatory(?bool encryptionMandatory): void |
| `encryptionType` | `?string` | Optional | An indicator from the ACS to inform the type of encryption that should be used in the event the ACS requires encryption of the credential field.<br><br>**Constraints**: *Maximum Length*: `20` | getEncryptionType(): ?string | setEncryptionType(?string encryptionType): void |
| `label` | `?string` | Optional | An ACS Provided label that can be presented to the Consumer. Recommended use with an application.<br><br>**Constraints**: *Maximum Length*: `20` | getLabel(): ?string | setLabel(?string label): void |
| `prompt` | `?string` | Optional | An ACS provided string that can be presented to the Consumer. Recommended use with an application.<br><br>**Constraints**: *Maximum Length*: `80` | getPrompt(): ?string | setPrompt(?string prompt): void |
| `statusMessage` | `?string` | Optional | An ACS provided message that can provide additional information or details.<br><br>**Constraints**: *Maximum Length*: `80` | getStatusMessage(): ?string | setStatusMessage(?string statusMessage): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IvrBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$ivr = IvrBuilder::init()
    ->enabledMessage(false)
    ->encryptionKey('encryptionKey4')
    ->encryptionMandatory(false)
    ->encryptionType('encryptionType2')
    ->label('label8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

