
# Capture Mandate

*This model accepts additional fields of type array.*

## Structure

`CaptureMandate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billingType` | `?string` | Optional | Configure Unified Checkout to capture billing address information.<br><br>Possible values:<br><br>- FULL: Capture complete billing address information.<br>- PARTIAL: Capture first name, last name, country and postal/zip code only.<br>- NONE: Capture only first name and last name.<br><br>**Constraints**: *Maximum Length*: `25` | getBillingType(): ?string | setBillingType(?string billingType): void |
| `requestEmail` | `?bool` | Optional | Configure Unified Checkout to capture customer email address.<br><br>Possible values:<br><br>- True<br>- False | getRequestEmail(): ?bool | setRequestEmail(?bool requestEmail): void |
| `requestPhone` | `?bool` | Optional | Configure Unified Checkout to capture customer phone number.<br><br>Possible values:<br><br>- True<br>- False | getRequestPhone(): ?bool | setRequestPhone(?bool requestPhone): void |
| `requestShipping` | `?bool` | Optional | Configure Unified Checkout to capture customer shipping details.<br><br>Possible values:<br><br>- True<br>- False | getRequestShipping(): ?bool | setRequestShipping(?bool requestShipping): void |
| `shipToCountries` | `?(string[])` | Optional | List of countries available to ship to.  <br>Use the two-character ISO Standard Country Codes.<br><br>**Constraints**: *Maximum Length*: `2` | getShipToCountries(): ?array | setShipToCountries(?array shipToCountries): void |
| `showAcceptedNetworkIcons` | `?bool` | Optional | Configure Unified Checkout to display the list of accepted card networks beneath the payment button<br><br>Possible values:<br><br>- True<br>- False | getShowAcceptedNetworkIcons(): ?bool | setShowAcceptedNetworkIcons(?bool showAcceptedNetworkIcons): void |
| `showConfirmationStep` | `?bool` | Optional | Configure Unified Checkout to display the final confirmation screen when using Click to Pay.<br><br>Where 'BillingType'= NONE and 'requestShipping'= FALSE and the customer is using an existing Click to Pay card as their chosen payment method, a final confirmation screen can be removed allowing the customer to check out as soon as they have selected their payment method from within their Click to Pay card tray.<br><br>Possible values:<br><br>- True<br>- False | getShowConfirmationStep(): ?bool | setShowConfirmationStep(?bool showConfirmationStep): void |
| `requestSaveCard` | `?bool` | Optional | Configure Unified Checkout to display the "Save card for future use" checkbox.<br><br><br>Configurable check box that will show in a Manual card entry flow to allow a Cardholder to give consent to store their manually entered credential with the Merchant that they are paying.<br><br>Applicable when manually entering the details and not enrolling in Click to Pay.<br><br>Possible values:<br><br>- True<br>- False<br><br><br><br>**Use Cases:**<br><br>**Offer consumers option to save their card in Unified Checkout:**<br><br>- Include the captureMandate.requestSaveCard field in the capture context request and set it to true.<br>- When set to true, this will show a checkbox with the message ‘Save card for future use’ in Unified Checkout.<br>- When selected this provides a response in both the Transient Token and Get Credentials API response.<br><br><br><br>**Do not offer consumers the option to save their card in Unified Checkout:**<br><br>- Include the captureMandate.requestSaveCard field in the capture context request and set it to false OR omit the field from the capture context request.<br>- When set to false, the save card option is not shown to consumers when manually entering card details. | getRequestSaveCard(): ?bool | setRequestSaveCard(?bool requestSaveCard): void |
| `comboCard` | `?bool` | Optional | Configure Unified Checkout to display combo card at checkout.<br><br><br>A combo debit/credit card is a single card that functions both as a Debit/Credit card.<br>Unified Checkout / Click to Pay Drop-in UI allows the Cardholder to choose whether they would like the transaction to be paid for using either debit or credit card.<br>**Important:** This is applicable to Visa cards only.<br><br>Possible values:<br><br>- True<br>- False<br><br><br><br>**Use Cases:**<br><br>**Offer Combo Card at Checkout:**<br><br>- Include the captureMandate.comboCard field in the capture context request and set it to true.<br>- When set to true, Combo Card selection is shown at checkout <br><br><br><br>**Do not offer Combo Card at Checkout:**<br><br>- Include the captureMandate.comboCard field in the capture context request and set it to false OR omit the field from the capture context request.<br>- The Combo Card selection is not shown at checkout. | getComboCard(): ?bool | setComboCard(?bool comboCard): void |
| `cpf` | `?bool` | Optional | Configure Unified Checkout to display and capture the CPF number (Cadastro de Pessoas Físicas).  The CPF number is a unique 11-digit identifier issued to Brazilian citizens and residents for tax purposes.<br><br>Possible values:<br><br>- True<br>- False<br><br><br><br>This field is optional.  <br>If set to true the field is required.<br>If set to false the field is optional.<br>If the field is not included in the capture context then it is not captured.<br><br><br><br>**Important:**<br><br>- If PANENTRY is specified in the allowedPaymentTypes field, the CPF number will be displayed in Unified Checkout regardless of what card number is entered.<br>- If CLICKTOPAY is specified in the allowedPaymentTypes field, the CPF number will be displayed in Unified Checkout only when a Visa Click To Pay card is entered. | getCpf(): ?bool | setCpf(?bool cpf): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CaptureMandateBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$captureMandate = CaptureMandateBuilder::init()
    ->billingType('FULL')
    ->requestEmail(false)
    ->requestPhone(false)
    ->requestShipping(false)
    ->shipToCountries(
        [
            'shipToCountries5',
            'shipToCountries6'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

