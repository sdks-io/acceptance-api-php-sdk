
# Vehicle Data

*This model accepts additional fields of type array.*

## Structure

`VehicleData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `connectorType` | `?string` | Optional | This field will contain connector type values for electric vehicle transactions.<br><br>Possible Values:<br>001 (AC - J1772 Type 1)<br>002 (AC - Mennekes - Type 2)<br>003 (AC - GB/T)<br>100 (DC - CCS1)<br>101 (DC - CHAdeMO)<br>102 (DC - CCS2)<br>103 (DC - GB/T)<br>200 (NACS – Tesla)<br><br>**Constraints**: *Maximum Length*: `3` | getConnectorType(): ?string | setConnectorType(?string connectorType): void |
| `chargingReasonCode` | `?string` | Optional | This field will contain charging reason code values for electric vehicle transactions.<br><br>Possible Values:<br>010 (Other Error)<br>011 (Connector Lock Failure)<br>012 (EV Communication Error)<br>013 (Ground Failure)<br>014 (High Temperature)<br>015 (Internal Error)<br>016 (Over Current Failure)<br>017 (Over Voltage)<br>018 (Power Meter Failure)<br>019 (Power Switch Failure)<br>020 (Reader Failure)<br>021 (Reset Failure)<br>022 (Under Voltage)<br>023 (Weak Signal)<br>100 (No Error)<br>200 (Payment Related Error)<br><br>**Constraints**: *Maximum Length*: `3` | getChargingReasonCode(): ?string | setChargingReasonCode(?string chargingReasonCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\VehicleDataBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$vehicleData = VehicleDataBuilder::init()
    ->connectorType('connectorType8')
    ->chargingReasonCode('chargingReasonCode6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

