
# Card 3

*This model accepts additional fields of type array.*

## Structure

`Card3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sourceAccountType` | `?string` | Optional | Flag that specifies the type of account associated with the card.<br>The cardholder provides this information during the payment process.<br><br>This field is required in the following cases:<br><br>- Debit transactions on Cielo and Comercio Latino.<br>- Transactions with Brazilian-issued cards on Visa Acceptance through VisaNet.<br>- Applicable only for Visa Acceptance through VisaNet (CtV).<br><br>**Note** Combo cards in Brazil contain credit and debit functionality in a single card. Visa systems use a credit bank<br>identification number (BIN) for this type of card. Using the BIN to determine whether a card is debit or<br>credit can cause transactions with these cards to be processed incorrectly. Visa Acceptance strongly recommends<br>that you include this field for combo card transactions.<br><br>Possible values include the following.<br><br>- `CH`: Checking account<br>- `CR`: Credit card account<br>- `SA`: Saving account<br>- `LI`: Line of credit or credit portion of combo card<br>- `PP`: Prepaid card account or prepaid portion of combo card<br>- `UA`: Universal account<br><br>If useAs is set to credit/debit and there is a value in SourceAccountType, the value in the SourceAccountType field will take precedence.<br>If useAs is set to CR/DB and there is a value in SourceAccountType, the value in the useAs field will take precedence.<br><br>**Constraints**: *Maximum Length*: `20` | getSourceAccountType(): ?string | setSourceAccountType(?string sourceAccountType): void |
| `sourceAccountTypeDetails` | `?string` | Optional | Type of account that is being used when the value for the override_payment_method field is line of credit (LI) or prepaid card (PP).<br>Possible values for line of credit:<br><br>- `AGRC`: Visa Agro Custeio<br>- `AGRE`: Visa Agro Electron<br>- `AGRI`: Visa Agro Investimento<br>- `AGRO`: Visa Agro<br>  Possible values for prepaid card:<br>- `VVA`: Visa Vale Alimentacao<br>- `VVF`: Visa Vale Flex<br>- `VVR`: Visa Vale Refeicao<br>  This field is supported only for combo card transactions in Brazil on Visa Acceptance through VisaNet.<br><br>**Constraints**: *Maximum Length*: `4` | getSourceAccountTypeDetails(): ?string | setSourceAccountTypeDetails(?string sourceAccountTypeDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Card3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$card3 = Card3Builder::init()
    ->sourceAccountType('sourceAccountType0')
    ->sourceAccountTypeDetails('sourceAccountTypeDetails0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

