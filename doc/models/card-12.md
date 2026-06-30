
# Card 12

*This model accepts additional fields of type array.*

## Structure

`Card12`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `expirationMonth` | `?string` | Optional | Two-digit month in which the payment card expires.<br><br>Format: `MM`.<br><br>Possible Values: `01` through `12`.<br><br>**Constraints**: *Maximum Length*: `2` | getExpirationMonth(): ?string | setExpirationMonth(?string expirationMonth): void |
| `expirationYear` | `?string` | Optional | Four-digit year in which the credit card expires.<br><br>Format: `YYYY`.<br><br>**Constraints**: *Maximum Length*: `4` | getExpirationYear(): ?string | setExpirationYear(?string expirationYear): void |
| `type` | `?string` | Optional | Value that indicates the card type. Possible Values v2 : v1:<br><br>* 001 : visa<br>* 002 : mastercard - Eurocard—European regional brand of Mastercard<br>* 003 : american express<br>* 004 : discover<br>* 005 : diners club<br>* 006 : carte blanche<br>* 007 : jcb<br>* 008 : optima<br>* 011 : twinpay credit<br>* 012 : twinpay debit<br>* 013 : walmart<br>* 014 : enRoute<br>* 015 : lowes consumer<br>* 016 : home depot consumer<br>* 017 : mbna<br>* 018 : dicks sportswear<br>* 019 : casual corner<br>* 020 : sears<br>* 021 : jal<br>* 023 : disney<br>* 024 : maestro uk domestic<br>* 025 : sams club consumer<br>* 026 : sams club business<br>* 028 : bill me later<br>* 029 : bebe<br>* 030 : restoration hardware<br>* 031 : delta online — use this value only for Ingenico ePayments. For other processors, use 001 for all Visa card types.<br>* 032 : solo<br>* 033 : visa electron<br>* 034 : dankort<br>* 035 : laser<br>* 036 : carte bleue — formerly Cartes Bancaires<br>* 037 : carta si<br>* 038 : pinless debit<br>* 039 : encoded account<br>* 040 : uatp<br>* 041 : household<br>* 042 : maestro international<br>* 043 : ge money uk<br>* 044 : korean cards<br>* 045 : style<br>* 046 : jcrew<br>* 047 : payease china processing ewallet<br>* 048 : payease china processing bank transfer<br>* 049 : meijer private label<br>* 050 : hipercard — supported only by the Comercio Latino processor.<br>* 051 : aura — supported only by the Comercio Latino processor.<br>* 052 : redecard<br>* 054 : elo — supported only by the Comercio Latino processor.<br>* 055 : capital one private label<br>* 056 : synchrony private label<br>* 057 : costco private label<br>* 060 : mada<br>* 062 : china union pay<br>* 063 : falabella private label | getType(): ?string | setType(?string type): void |
| `issueNumber` | `?string` | Optional | Number of times a Maestro (UK Domestic) card has been issued to the account holder. The card might or might not have an issue number. The number can consist of one or two digits, and the first digit might be a zero. When you include this value in your request, include exactly what is printed on the card. A value of 2 is different than a value of 02. Do not include the field, even with a blank value, if the card is not a Maestro (UK Domestic) card.<br><br>**Note** The issue number is not required for Maestro (UK Domestic) transactions.<br><br>**Constraints**: *Maximum Length*: `2` | getIssueNumber(): ?string | setIssueNumber(?string issueNumber): void |
| `startMonth` | `?string` | Optional | Month of the start of the Maestro (UK Domestic) card validity period. Do not include the field, even with a blank value, if the card is not a Maestro (UK Domestic) card. `Format: MM`.<br>Possible Values: 01 through 12.<br><br>**Note** The start date is not required for Maestro (UK Domestic) transactions.<br><br>**Constraints**: *Maximum Length*: `2` | getStartMonth(): ?string | setStartMonth(?string startMonth): void |
| `startYear` | `?string` | Optional | Year of the start of the Maestro (UK Domestic) card validity period. Do not include the field, even with a blank value, if the card is not a Maestro (UK Domestic) card. `Format: YYYY`.<br><br>**Note** The start date is not required for Maestro (UK Domestic) transactions.<br><br>**Constraints**: *Maximum Length*: `4` | getStartYear(): ?string | setStartYear(?string startYear): void |
| `useAs` | `?string` | Optional | 'Payment Instrument was created / updated as part of a pinless debit transaction.' | getUseAs(): ?string | setUseAs(?string useAs): void |
| `hash` | `?string` | Optional, Read-only | Hash value representing the card.<br><br>**Constraints**: *Minimum Length*: `32`, *Maximum Length*: `34` | getHash(): ?string | setHash(?string hash): void |
| `tokenizedInformation` | [`?TokenizedInformation`](../../doc/models/tokenized-information.md) | Optional | - | getTokenizedInformation(): ?TokenizedInformation | setTokenizedInformation(?TokenizedInformation tokenizedInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Card12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$card12 = Card12Builder::init()
    ->expirationMonth('expirationMonth8')
    ->expirationYear('expirationYear6')
    ->type('type8')
    ->issueNumber('issueNumber6')
    ->startMonth('startMonth2')
    ->useAs('pinless debit')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

