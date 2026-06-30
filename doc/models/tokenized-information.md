
# Tokenized Information

*This model accepts additional fields of type array.*

## Structure

`TokenizedInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `requestorId` | `?string` | Optional | Value that identifies your business and indicates that the cardholder’s account number is tokenized. This value<br>is assigned by the token service provider and is unique within the token service provider’s database.<br><br>**Note** This field is supported only through **VisaNet** and **FDC Nashville Global**.<br><br>**Constraints**: *Maximum Length*: `11` | getRequestorId(): ?string | setRequestorId(?string requestorId): void |
| `transactionType` | `?string` | Optional | Type of transaction that provided the token data. This value does not specify the token service provider; it<br>specifies the entity that provided you with information about the token.<br><br>Set the value for this field to 1. An application on the customer’s mobile device provided the token data.<br><br>**Constraints**: *Maximum Length*: `1` | getTransactionType(): ?string | setTransactionType(?string transactionType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$tokenizedInformation = TokenizedInformationBuilder::init()
    ->requestorId('requestorID8')
    ->transactionType('transactionType4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

