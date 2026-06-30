
# Service Fee Descriptor

*This model accepts additional fields of type array.*

## Structure

`ServiceFeeDescriptor`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Name of the service provider that is collecting the service fee. The service provider name must consist of<br>3, 7, or 12 characters followed by an asterisk (*). This value must also include the words “Service Fee.”<br><br>When you include more than one consecutive space, extra spaces are removed. Use one of the following formats<br>for this value:<br><br>- <3-character name>*Service Fee<br>- <7-character name>*Service Fee<br>- <12-character name>*Service Fee<br><br>When payments are made in installments, this value must also include installment information such as<br>“1 of 5” or “3 of 7.” For installment payments, use one of the following formats for this value:<br><br>- <3-character name>*Service Fee*<N> of <M><br>- <7-character name>*Service Fee*<N> of <M><br>- <12-character name>*Service Fee*<N> of <M><br><br>where <N> is the payment number and <M> is the total number of payments.<br><br>When you do not include this value in your request, Visa Acceptance uses the value that is in your Visa Acceptance<br>account.<br><br>This value might be displayed on the cardholder’s statement.<br><br>**Constraints**: *Maximum Length*: `22` | getName(): ?string | setName(?string name): void |
| `contact` | `?string` | Optional | Contact information for the service provider that is collecting the service fee. when you include more than one<br>consecutive space, extra spaces are removed.<br><br>When you do not include this value in your request, Visa Acceptance uses the value that is in your Visa Acceptance account.<br><br>This value might be displayed on the cardholder’s statement.<br><br>**Constraints**: *Maximum Length*: `11` | getContact(): ?string | setContact(?string contact): void |
| `state` | `?string` | Optional | State or territory in which the service provider is located.<br><br>When you do not include this value in your request, Visa Acceptance uses the value that is in your Visa Acceptance account.<br><br>This value might be displayed on the cardholder’s statement.<br><br>**Constraints**: *Maximum Length*: `20` | getState(): ?string | setState(?string state): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ServiceFeeDescriptorBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$serviceFeeDescriptor = ServiceFeeDescriptorBuilder::init()
    ->name('name6')
    ->contact('contact6')
    ->state('state2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

