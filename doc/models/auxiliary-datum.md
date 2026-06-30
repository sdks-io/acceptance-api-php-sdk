
# Auxiliary Datum

Contains auxiliary key-value pairs.

*This model accepts additional fields of type array.*

## Structure

`AuxiliaryDatum`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `key` | `?string` | Optional | Fields that you can use to send additional data to Risk services.<br>**Warning** Auxiliary fields are not intended to and MUST NOT<br>be used to capture personally identifying information.<br>Accordingly, merchants are prohibited from capturing,<br>obtaining, and/or transmitting any personally identifying<br>information in or via the auxiliary data fields. Personally<br>identifying information includes, but is not limited to,<br>address, credit card number, social security number,<br>driver's license number, state-issued identification<br>number, passport number, and card verification numbers<br>(CVV, CVC2, CVV2, CID, CVN). In the event Visa Acceptance<br>discovers that a merchant is capturing and/or transmitting<br>personally identifying information via the auxiliary data<br>fields, whether or not intentionally, Visa Acceptance WILL<br>immediately suspend the merchant's account, which will<br>result in a rejection of any and all transaction requests<br>submitted by the merchant after the point of suspension.<br><br>**Constraints**: *Maximum Length*: `255` | getKey(): ?string | setKey(?string key): void |
| `value` | `?string` | Optional | String value for the key<br><br>**Constraints**: *Maximum Length*: `255` | getValue(): ?string | setValue(?string value): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AuxiliaryDatumBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$auxiliaryDatum = AuxiliaryDatumBuilder::init()
    ->key('key4')
    ->value('value6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

