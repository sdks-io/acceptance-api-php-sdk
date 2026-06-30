
# Ip Address 2

*This model accepts additional fields of type array.*

## Structure

`IpAddress2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `anonymizerStatus` | `?string` | Optional | Indicates whether the transaction IP address is associated with a known anonymous proxy.<br><br>For all possible values, see the `score_ip_anonymizer_status` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.]( Click **Decision Manager** > **Documentation** > **Guides** > _Decision Manager Using the SCMP API Developer Guide_ (PDF link).<br><br>**Constraints**: *Maximum Length*: `255` | getAnonymizerStatus(): ?string | setAnonymizerStatus(?string anonymizerStatus): void |
| `locality` | `?string` | Optional | Name of the city decoded from the IP address used directly or indirectly by the customer to send the order.<br><br>For all possible values, see the `score_ip_city` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.]( Click **Decision Manager** > **Documentation** > **Guides** > _Decision Manager Using the SCMP API Developer Guide_ (PDF link).<br><br>**Constraints**: *Maximum Length*: `255` | getLocality(): ?string | setLocality(?string locality): void |
| `country` | `?string` | Optional | Name of the country decoded from the IP address used directly or indirectly by the customer to send the order.<br><br>For all possible values, see the `score_ip_country` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.]( Click **Decision Manager** > **Documentation** > **Guides** > _Decision Manager Using the SCMP API Developer Guide_ (PDF link).<br><br>**Constraints**: *Maximum Length*: `255` | getCountry(): ?string | setCountry(?string country): void |
| `administrativeArea` | `?string` | Optional | Name of the state decoded from the IP address used directly or indirectly by the customer to send the order.<br><br>For all possible values, see the `score_ip_state` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.]( Click **Decision Manager** > **Documentation** > **Guides** > _Decision Manager Using the SCMP API Developer Guide_ (PDF link).<br><br>**Constraints**: *Maximum Length*: `255` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `routingMethod` | `?string` | Optional | Routing method decoded from the IP address used directly or indirectly by the customer to send the order.<br><br>For all possible values, see the `score_ip_routing_method` field description in the _Decision Manager Using the SCMP API Developer Guide_ on the [Visa Acceptance Business Center.]( Click **Decision Manager** > **Documentation** > **Guides** > _Decision Manager Using the SCMP API Developer Guide_ (PDF link).<br><br>**Constraints**: *Maximum Length*: `255` | getRoutingMethod(): ?string | setRoutingMethod(?string routingMethod): void |
| `carrier` | `?string` | Optional | Provides the name of the organization that owns the ASN. The carrier is responsible for the traffic carried on the network or set of networks designated as an Autonomous System (AS) and identified by the ASN.<br>While there are more than 27,000 active ASNs, there are fewer carriers, because a single carrier often manages several ASNs.<br><br>**Constraints**: *Maximum Length*: `255` | getCarrier(): ?string | setCarrier(?string carrier): void |
| `organization` | `?string` | Optional | The Registering Organization is the entity responsible for the actions and content associated with a given block of IP addresses. This is in contrast to the carrier, which is responsible for the routing of traffic for network blocks. Registering Organizations include many types of entities, including corporate, government, or educational entities, and ISPs managing the allocation and use of network blocks.<br><br>**Constraints**: *Maximum Length*: `255` | getOrganization(): ?string | setOrganization(?string organization): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IpAddress2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$ipAddress2 = IpAddress2Builder::init()
    ->anonymizerStatus('anonymizerStatus4')
    ->locality('locality4')
    ->country('country8')
    ->administrativeArea('administrativeArea0')
    ->routingMethod('routingMethod6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

