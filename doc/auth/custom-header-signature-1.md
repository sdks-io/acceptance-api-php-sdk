
# Custom Header Signature



Documentation for accessing and setting credentials for Accept.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| Accept | `string` | - | `accept` | `getAccept()` |



**Note:** Auth credentials can be set using `AcceptCredentialsBuilder::init()` in `acceptCredentials` method in the client builder and accessed through `getAcceptCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```php
use VisaAcceptanceMergedSpecLib\Authentication\AcceptCredentialsBuilder;
use VisaAcceptanceMergedSpecLib\VisaAcceptanceMergedSpecClientBuilder;

$client = VisaAcceptanceMergedSpecClientBuilder::init()
    ->acceptCredentials(
        AcceptCredentialsBuilder::init(
            'Accept'
        )
    )
    ->build();
```


