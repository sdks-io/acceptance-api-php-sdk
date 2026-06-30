
# Routing

*This model accepts additional fields of type array.*

## Structure

`Routing`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `network` | `?string` | Optional | PIN Debit Services:<br>Contains the ID of the debit network to which the transaction was routed.<br><br>\| Code \| Network \|<br>\| --- \| --- \|<br>\| 0000 \| Priority Routing or Generic File Update \|<br>\| 0002 \| Visa programs, Private Label and non-Visa Authorization Gateway Services \|<br>\| 0003 \| Interlink \|<br>\| 0004 \| Plus \|<br>\| 0008 \| Star \|<br>\| 0009 \| Pulse\|<br>\| 0010 \| Star \|<br>\| 0011 \| Star \|<br>\| 0012 \| Star (primary network ID) \|<br>\| 0013 \| AFFN \|<br>\| 0015 \| Star \|<br>\| 0016 \| Maestro \|<br>\| 0017 \| Pulse (primary network ID) \|<br>\| 0018 \| NYCE (primary network ID) \|<br>\| 0019 \| Pulse \|<br>\| 0020 \| Accel \|<br>\| 0023 \| NETS \|<br>\| 0024 \| CU24 \|<br>\| 0025 \| Alaska Option \|<br>\| 0027 \| NYCE \|<br>\| 0028 \| Shazam \|<br>\| 0029 \| EBT POS \|<br><br>FDC Nashville Global authorization service:<br><br>Indicates whether the transaction was routed to a credit network, a debit network, or the STAR signature debit<br>network.<br><br>- `C`: Credit network<br>- `D`: Debit network (without signature)<br>- `S`: STAR signature debit network<br><br>**Constraints**: *Maximum Length*: `4` | getNetwork(): ?string | setNetwork(?string network): void |
| `networkName` | `?string` | Optional | Name of the network to which the transaction was routed.<br><br>**Constraints**: *Maximum Length*: `10` | getNetworkName(): ?string | setNetworkName(?string networkName): void |
| `customerSignatureRequired` | `?string` | Optional | Indicates whether you need to obtain the cardholder's signature.<br><br>Possible values:<br><br>- `Y`: You need to obtain the cardholder's signature.<br>- `N`: You do not need to obtain the cardholder's signature.<br><br>**Constraints**: *Maximum Length*: `1` | getCustomerSignatureRequired(): ?string | setCustomerSignatureRequired(?string customerSignatureRequired): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RoutingBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$routing = RoutingBuilder::init()
    ->network('network2')
    ->networkName('networkName8')
    ->customerSignatureRequired('customerSignatureRequired6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

