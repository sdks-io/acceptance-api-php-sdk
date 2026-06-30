
# Ancillary Information

*This model accepts additional fields of type array.*

## Structure

`AncillaryInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ticketNumber` | `?string` | Optional | Ticket number, which consists of the carrier code, form, and serial number, without the check digit.<br>**Important** This field is required in the U.S. in order for you to qualify for either the<br>custom payment service (CPS) or the electronic interchange reimbursement fee (EIRF) program.<br>Format: English characters only.<br>Optional field for ancillary services.<br><br>**Constraints**: *Maximum Length*: `15` | getTicketNumber(): ?string | setTicketNumber(?string ticketNumber): void |
| `passengerName` | `?string` | Optional | Name of the passenger. If the passenger’s name is not available, this value is the cardholder’s name. If neither the passenger’s name nor the cardholder’s name is available,<br>this value is a description of the ancillary purchase.<br>**Important** This field is required in the U.S. in order for you to qualify for either the custom payment service (CPS) or the electronic interchange reimbursement fee (EIRF)<br>program.<br>Format: English characters only.<br>Optional field for ancillary service.<br><br>**Constraints**: *Maximum Length*: `20` | getPassengerName(): ?string | setPassengerName(?string passengerName): void |
| `connectedTicketNumber` | `?string` | Optional | Number for the airline ticket to which the ancillary purchase is connected.<br><br>If this purchase has a connection or relationship to another purchase such as a baggage fee for a passenger transport ticket, this field must contain the ticket number for the other purchase.<br><br>For a stand-alone purchase, the value for this field must be the same as the value for the `travelInformation.transit.airline.ancillaryInformation.ticketNumber` field.<br>**Important** This field is required in the U.S. in order for you to qualify for either the custom payment service (CPS) or the electronic interchange reimbursement fee (EIRF)<br>program.<br>Format: English characters only.<br>Optional request field for ancillary services.<br><br>**Constraints**: *Maximum Length*: `15` | getConnectedTicketNumber(): ?string | setConnectedTicketNumber(?string connectedTicketNumber): void |
| `creditReasonIndicator` | `?string` | Optional | Reason for the credit.<br>Possible values:<br><br>- `A`: Cancellation of the ancillary passenger transport purchase.<br>- `B`: Cancellation of the airline ticket and the passenger transport ancillary purchase.<br>- `C`: Cancellation of the airline ticket.<br>- `O`: Other.<br>- `P`: Partial refund of the airline ticket.<br>  Format: English characters only.<br>  Optional field for ancillary services.<br><br>**Constraints**: *Maximum Length*: `15` | getCreditReasonIndicator(): ?string | setCreditReasonIndicator(?string creditReasonIndicator): void |
| `service` | [`?(Service[])`](../../doc/models/service.md) | Optional | - | getService(): ?array | setService(?array service): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AncillaryInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ServiceBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$ancillaryInformation = AncillaryInformationBuilder::init()
    ->ticketNumber('ticketNumber4')
    ->passengerName('passengerName0')
    ->connectedTicketNumber('connectedTicketNumber6')
    ->creditReasonIndicator('creditReasonIndicator2')
    ->service(
        [
            ServiceBuilder::init()
                ->categoryCode('categoryCode0')
                ->subCategoryCode('subCategoryCode2')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            ServiceBuilder::init()
                ->categoryCode('categoryCode0')
                ->subCategoryCode('subCategoryCode2')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            ServiceBuilder::init()
                ->categoryCode('categoryCode0')
                ->subCategoryCode('subCategoryCode2')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

