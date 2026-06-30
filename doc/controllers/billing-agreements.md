# Billing Agreements

A billingAgreement is a stand-alone transaction that is not linked to any previous transactions. It takes money from
your merchant bank account and returns it to the customer.

```php
$billingAgreementsApi = $client->getBillingAgreementsApi();
```

## Class Name

`BillingAgreementsApi`

## Methods

* [Billing Agreements Registration](../../doc/controllers/billing-agreements.md#billing-agreements-registration)
* [Billing Agreements De Registration](../../doc/controllers/billing-agreements.md#billing-agreements-de-registration)
* [Billing Agreements Intimation](../../doc/controllers/billing-agreements.md#billing-agreements-intimation)


# Billing Agreements Registration

#### Standing Instruction:

Standing Instruction with or without Token. Transaction amount in case First payment is coming along with registration. Only 2 decimal places allowed

#### Create Mandate:

You can create a mandate through the direct debit mandate flow.
Possible create mandate status values:

- Pending—the create mandate request was successfully processed.
- Failed—the create mandate request was not accepted.

#### Import Mandate:

In the Bacs scheme, a mandate is created with a status of active. Direct debit collections can be made against it immediately.
You can import a mandate to the Visa Acceptance database when:

- You have existing customers with signed, active mandates
- You manage mandates outside of Visa Acceptance.

When you import an existing mandate to the Visa Acceptance database, provide a unique value for the mandate ID or the request results in an error.
If an import mandate request is not accepted, the import mandate status value is failed.

```php
function billingAgreementsRegistration(CreateBillingAgreement $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateBillingAgreement`](../../doc/models/create-billing-agreement.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2CreateBillingAgreementPost201Response`](../../doc/models/pts-v2-create-billing-agreement-post-201-response.md).

## Example Usage

```php
$body = CreateBillingAgreementBuilder::init()->build();

$billingAgreementsApi = $client->getBillingAgreementsApi();
$apiResponse = $billingAgreementsApi->billingAgreementsRegistration($body);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2CreateBillingAgreementPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2CreateBillingAgreementPost400Response1Exception`](../../doc/models/pts-v2-create-billing-agreement-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2CreateBillingAgreementPost502Response1Exception`](../../doc/models/pts-v2-create-billing-agreement-post-502-response-1-exception.md) |


# Billing Agreements De Registration

#### Standing Instruction:

Standing Instruction with or without Token.

#### Revoke Mandate:

When you revoke a mandate, any pending direct debits linked to that mandate are canceled. No notifications are sent.
When you revoke a mandate with no pending direct debits, the Bacs scheme or customer’s bank notify you of any subsequent direct debit events.
When you revoke a mandate, you cannot send a direct debit request using the mandate ID. Customer payments cannot be made against a revoked mandate.
You can revoke a mandate when the customer:

- Requests that you revoke the mandate.
- Closes their account with you.
  Possible revoke mandate status values -
- Revoked—the revoke mandate request was successfully processed.
- Failed—the revoke mandate request was not accepted.

#### Update Mandate:

In most cases, the account details of an existing mandate cannot be updated in the Bacs schema,
except by creating a new mandate. However, some very limited customer information, like name and address,
can be updated to the mandate without needing to revoke it first

#### Mandate Status:

After the customer signs the mandate, request that the mandate status service verify the mandate status.
Possible mandate status values:

- Active—the mandate is successfully created. A direct debit can be sent for this mandate ID.
- Pending—a pending mandate means the mandate is not yet signed.
- Failed—the customer did not authenticate.
- Expired—the deadline to create the mandate passed.
- Revoked—the mandate is cancelled.

#### Paypal Billing Agreement:

A billing agreement is set up between PayPal and your customer.
When you collect the details of a customer’s billing agreement, you are able to bill that customer without requiring an authorization for each payment.
You can bill the customer at the same time you process their PayPal Express checkout order, which simplifies your business processes.

```php
function billingAgreementsDeRegistration(string $id, ModifyBillingAgreement $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID for de-registration or cancellation of Billing Agreement |
| `body` | [`ModifyBillingAgreement`](../../doc/models/modify-billing-agreement.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2ModifyBillingAgreementPost201Response`](../../doc/models/pts-v2-modify-billing-agreement-post-201-response.md).

## Example Usage

```php
$id = 'id0';

$body = ModifyBillingAgreementBuilder::init()
    ->agreementInformation(
        AgreementInformation8Builder::init()
            ->id('G8UD2OKG49UW')
            ->eSignIndicator('y')
            ->build()
    )
    ->clientReferenceInformation(
        ClientReferenceInformation28Builder::init()
            ->code('TC84105-1')
            ->build()
    )
    ->aggregatorInformation(
        AggregatorInformation5Builder::init()
            ->name('aggregatorname')
            ->subMerchant(
                SubMerchantBuilder::init()
                    ->name('rupay')
                    ->build()
            )
            ->build()
    )
    ->consumerAuthenticationInformation(
        ConsumerAuthenticationInformation2Builder::init()
            ->authenticationTransactionContextId('100000000000000000000000025253')
            ->transactionToken('AxjzbwSTcz9aHyOIL490/949UafAxfvksgAxHXa2/+xcVZ0CtA+AbkvF')
            ->build()
    )
    ->deviceInformation(
        DeviceInformation5Builder::init()
            ->httpAcceptBrowserValue('http')
            ->ipAddress('10.10.10.10')
            ->userAgentBrowserValue('safari')
            ->build()
    )
    ->installmentInformation(
        InstallmentInformation4Builder::init()
            ->identifier('1000000')
            ->paymentType('1')
            ->build()
    )
    ->merchantInformation(
        MerchantInformation11Builder::init()
            ->cancelUrl('https://www.valid.merchant.redirect.url.from.request.html?actioncancel')
            ->successUrl('https://www.valid.merchant.redirect.url.from.request.html?actionsuccess')
            ->failureUrl('https://www.valid.merchant.redirect.url.from.request.html?actionfailure')
            ->build()
    )
    ->orderInformation(
        OrderInformation20Builder::init()
            ->amountDetails(
                AmountDetails5Builder::init()
                    ->totalAmount('100.00')
                    ->currency('INR')
                    ->build()
            )
            ->billTo(
                BillTo7Builder::init()
                    ->address1('808 Metro Blvd')
                    ->address2('Suite A101')
                    ->administrativeArea('CA')
                    ->company('Visa Acceptance Trading Inc.')
                    ->country('US')
                    ->county('San Francisco')
                    ->district('SF')
                    ->email('srbuyeroffice@cybs.com')
                    ->firstName('Comet')
                    ->middleName('Foster')
                    ->lastName('Bowditch')
                    ->locality('San Francisco')
                    ->phoneNumber('16501234567')
                    ->postalCode('944041234')
                    ->title('Senior Buyer')
                    ->build()
            )
            ->build()
    )
    ->paymentInformation(
        PaymentInformation16Builder::init()
            ->card(
                Card7Builder::init()
                    ->expirationMonth('12')
                    ->expirationYear('2031')
                    ->number('5082794233463')
                    ->securityCode('123')
                    ->type('061')
                    ->build()
            )
            ->paymentType(
                PaymentType13Builder::init()
                    ->method(
                        Method13Builder::init()
                            ->name('SENTENIAL')
                            ->build()
                    )
                    ->name('directDebitBacs')
                    ->build()
            )
            ->bank(
                Bank7Builder::init()
                    ->account(
                        Account9Builder::init()
                            ->number('1234567890ABCDEFGHIJ0123456789')
                            ->build()
                    )
                    ->iban('NL51ABNC1122334455')
                    ->swiftCode('ABNCNL2AGMK')
                    ->scheme('bacs')
                    ->build()
            )
            ->build()
    )
    ->processingInformation(
        ProcessingInformation20Builder::init()
            ->commerceIndicator('rpy')
            ->actionList(
                [
                    'UPDATE_AGREEMENT'
                ]
            )
            ->build()
    )
    ->buyerInformation(
        BuyerInformation7Builder::init()
            ->dateOfBirth('19990101')
            ->gender('F')
            ->language('en')
            ->build()
    )
    ->build();

$billingAgreementsApi = $client->getBillingAgreementsApi();
$apiResponse = $billingAgreementsApi->billingAgreementsDeRegistration(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2ModifyBillingAgreementPost201Response:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2ModifyBillingAgreementPost400Response1Exception`](../../doc/models/pts-v2-modify-billing-agreement-post-400-response-1-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2ModifyBillingAgreementPost502Response1Exception`](../../doc/models/pts-v2-modify-billing-agreement-post-502-response-1-exception.md) |


# Billing Agreements Intimation

Standing Instruction with or without Token.

```php
function billingAgreementsIntimation(string $id, IntimateBillingAgreement $body): ApiResponse
```

## Authentication

This endpoint requires [BearerAuth](../../doc/auth/custom-header-signature.md) **AND** [Accept](../../doc/auth/custom-header-signature-1.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID for intimation of Billing Agreement |
| `body` | [`IntimateBillingAgreement`](../../doc/models/intimate-billing-agreement.md) | Body, Required | - |

## Response Type

**201**: Successful response.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` method on this instance returns the response data which is of type [`PtsV2CreditsPost201Response1`](../../doc/models/pts-v2-credits-post-201-response-1.md).

## Example Usage

```php
$id = 'id0';

$body = IntimateBillingAgreementBuilder::init()
    ->installmentInformation(
        InstallmentInformation4Builder::init()
            ->alertPreference('SMS')
            ->firstInstallmentDate('2111')
            ->identifier('1000000000')
            ->lastInstallmentDate('3110')
            ->maxAmount('1000')
            ->minAmount('100')
            ->paymentType('1')
            ->preferredDay('1')
            ->sequence(2)
            ->build()
    )
    ->merchantInformation(
        MerchantInformation11Builder::init()
            ->transactionLocalDateTime('20211216124549')
            ->build()
    )
    ->orderInformation(
        OrderInformation20Builder::init()
            ->amountDetails(
                AmountDetails5Builder::init()
                    ->totalAmount('00')
                    ->currency('INR')
                    ->build()
            )
            ->build()
    )
    ->paymentInformation(
        PaymentInformation16Builder::init()
            ->card(
                Card7Builder::init()
                    ->expirationMonth('12')
                    ->expirationYear('2031')
                    ->number('5082302886091')
                    ->securityCode('123')
                    ->type('061')
                    ->build()
            )
            ->build()
    )
    ->build();

$billingAgreementsApi = $client->getBillingAgreementsApi();
$apiResponse = $billingAgreementsApi->billingAgreementsIntimation(
    $id,
    $body
);

// Extracting response status code
var_dump($apiResponse->getStatusCode());
// Extracting response headers
var_dump($apiResponse->getHeaders());

if ($apiResponse->isSuccess()) {
    echo 'PtsV2CreditsPost201Response1:';
    var_dump($apiResponse->getResult());
} else {
    $error = $apiResponse->getResult();
    var_dump($error);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request. | [`PtsV2CreditsPost400Response21Exception`](../../doc/models/pts-v2-credits-post-400-response-21-exception.md) |
| 502 | Unexpected system error or system timeout. | [`PtsV2CreditsPost502Response21Exception`](../../doc/models/pts-v2-credits-post-502-response-21-exception.md) |

