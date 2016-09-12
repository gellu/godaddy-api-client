# GoDaddyDomainsClient\VdomainsApi

All URIs are relative to *https://api.ote-godaddy.com/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**available**](VdomainsApi.md#available) | **GET** /v1/domains/available | Determine whether or not the specified domain is available for purchase
[**callList**](VdomainsApi.md#callList) | **GET** /v1/domains | Retrieve a list of Domains for the specified Shopper
[**cancel**](VdomainsApi.md#cancel) | **DELETE** /v1/domains/{domain} | Cancel a purchased domain
[**cancelPrivacy**](VdomainsApi.md#cancelPrivacy) | **DELETE** /v1/domains/{domain}/privacy | Submit a privacy cancellation request for the given domain
[**get**](VdomainsApi.md#get) | **GET** /v1/domains/{domain} | Retrieve details for the specified Domain
[**getAgreement**](VdomainsApi.md#getAgreement) | **GET** /v1/domains/agreements | Retrieve the legal agreement(s) required to purchase the specified TLD and add-ons
[**identityDocumentsUpload**](VdomainsApi.md#identityDocumentsUpload) | **POST** /v1/domains/identityDocuments | Upload an identity document for Real Name Validation
[**purchase**](VdomainsApi.md#purchase) | **POST** /v1/domains/purchase | Purchase and register the specified Domain
[**purchasePrivacy**](VdomainsApi.md#purchasePrivacy) | **POST** /v1/domains/{domain}/privacy/purchase | Purchase privacy for a specified domain
[**recordAdd**](VdomainsApi.md#recordAdd) | **PATCH** /v1/domains/{domain}/records | Add the specified DNS Records to the specified Domain
[**recordGet**](VdomainsApi.md#recordGet) | **GET** /v1/domains/{domain}/records/{type?}/{name?} | Retrieve DNS Records for the specified Domain, optionally with the specified Type and/or Name
[**recordReplace**](VdomainsApi.md#recordReplace) | **PUT** /v1/domains/{domain}/records | Replace all DNS Records for the specified Domain
[**recordReplaceType**](VdomainsApi.md#recordReplaceType) | **PUT** /v1/domains/{domain}/records/{type} | Replace all DNS Records for the specified Domain with the specified Type
[**recordReplaceTypeName**](VdomainsApi.md#recordReplaceTypeName) | **PUT** /v1/domains/{domain}/records/{type}/{name} | Replace all DNS Records for the specified Domain with the specified Type and Name
[**renew**](VdomainsApi.md#renew) | **POST** /v1/domains/{domain}/renew | Renew the specified Domain
[**schema**](VdomainsApi.md#schema) | **GET** /v1/domains/purchase/schema/{tld} | Retrieve the schema to be submitted when registering a Domain for the specified TLD
[**suggest**](VdomainsApi.md#suggest) | **GET** /v1/domains/suggest | Suggest alternate Domain names based on a seed Domain or set of keywords
[**tlds**](VdomainsApi.md#tlds) | **GET** /v1/domains/tlds | Retrieves a list of TLDs supported and enabled for sale
[**transferIn**](VdomainsApi.md#transferIn) | **POST** /v1/domains/{domain}/transfer | Purchase and start or restart transfer process
[**update**](VdomainsApi.md#update) | **PATCH** /v1/domains/{domain} | Update details for the specified Domain
[**updateContacts**](VdomainsApi.md#updateContacts) | **PATCH** /v1/domains/{domain}/contacts | Update domain
[**validate**](VdomainsApi.md#validate) | **POST** /v1/domains/purchase/validate | Validate the request body using the Domain Purchase Schema for the specified TLD
[**verifyEmail**](VdomainsApi.md#verifyEmail) | **POST** /v1/domains/{domain}/verifyRegistrantEmail | Re-send Contact E-mail Verification for specified Domain


# **available**
> \GoDaddyDomainsClient\Model\DomainAvailableResponse available($domain, $check_type, $for_transfer, $wait_ms)

Determine whether or not the specified domain is available for purchase

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain name whose availability is to be checked
$check_type = "FAST"; // string | Optimize for time ('FAST') or accuracy ('FULL')
$for_transfer = false; // bool | Whether or not to include domains available for transfer
$wait_ms = 1000; // int | Maximum amount of time, in milliseconds, to wait for responses If elapses, return the results compiled up to that point, some of which may not be authoritative

try {
    $result = $api_instance->available($domain, $check_type, $for_transfer, $wait_ms);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->available: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain name whose availability is to be checked |
 **check_type** | **string**| Optimize for time (&#39;FAST&#39;) or accuracy (&#39;FULL&#39;) | [optional] [default to FAST]
 **for_transfer** | **bool**| Whether or not to include domains available for transfer | [optional] [default to false]
 **wait_ms** | **int**| Maximum amount of time, in milliseconds, to wait for responses If elapses, return the results compiled up to that point, some of which may not be authoritative | [optional] [default to 1000]

### Return type

[**\GoDaddyDomainsClient\Model\DomainAvailableResponse**](../Model/DomainAvailableResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **callList**
> \GoDaddyDomainsClient\Model\DomainSummary[] callList($x_shopper_id, $statuses, $status_groups, $limit, $marker, $includes)

Retrieve a list of Domains for the specified Shopper

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$x_shopper_id = "x_shopper_id_example"; // string | Shopper ID whose domains are to be retrieved
$statuses = array("statuses_example"); // string[] | Only include results with `status` value in the specified set
$status_groups = array("status_groups_example"); // string[] | Only include results with `status` value in any of the specified groups
$limit = 56; // int | Maximum number of domains to return
$marker = "marker_example"; // string | Marker Domain to use as the offset in results
$includes = array("includes_example"); // string[] | Optional details to be included in the response

try {
    $result = $api_instance->callList($x_shopper_id, $statuses, $status_groups, $limit, $marker, $includes);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->callList: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_shopper_id** | **string**| Shopper ID whose domains are to be retrieved | [optional]
 **statuses** | [**string[]**](../Model/string.md)| Only include results with &#x60;status&#x60; value in the specified set | [optional]
 **status_groups** | [**string[]**](../Model/string.md)| Only include results with &#x60;status&#x60; value in any of the specified groups | [optional]
 **limit** | **int**| Maximum number of domains to return | [optional]
 **marker** | **string**| Marker Domain to use as the offset in results | [optional]
 **includes** | [**string[]**](../Model/string.md)| Optional details to be included in the response | [optional]

### Return type

[**\GoDaddyDomainsClient\Model\DomainSummary[]**](../Model/DomainSummary.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **cancel**
> cancel($domain)

Cancel a purchased domain

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain to cancel

try {
    $api_instance->cancel($domain);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->cancel: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain to cancel |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **cancelPrivacy**
> cancelPrivacy($domain, $x_shopper_id)

Submit a privacy cancellation request for the given domain

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain whose privacy is to be cancelled
$x_shopper_id = "x_shopper_id_example"; // string | Shopper ID of the owner of the domain

try {
    $api_instance->cancelPrivacy($domain, $x_shopper_id);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->cancelPrivacy: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain whose privacy is to be cancelled |
 **x_shopper_id** | **string**| Shopper ID of the owner of the domain | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **get**
> \GoDaddyDomainsClient\Model\DomainDetail get($domain, $x_shopper_id)

Retrieve details for the specified Domain

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain name whose details are to be retrieved
$x_shopper_id = "x_shopper_id_example"; // string | Shopper ID expected to own the specified domain

try {
    $result = $api_instance->get($domain, $x_shopper_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->get: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain name whose details are to be retrieved |
 **x_shopper_id** | **string**| Shopper ID expected to own the specified domain | [optional]

### Return type

[**\GoDaddyDomainsClient\Model\DomainDetail**](../Model/DomainDetail.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getAgreement**
> \GoDaddyDomainsClient\Model\LegalAgreement[] getAgreement($tlds, $privacy, $x_market_id, $for_transfer)

Retrieve the legal agreement(s) required to purchase the specified TLD and add-ons

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$tlds = array("tlds_example"); // string[] | list of TLDs whose legal agreements are to be retrieved
$privacy = true; // bool | Whether or not privacy has been requested
$x_market_id = "en-US"; // string | Unique identifier of the Market used to retrieve/translate Legal Agreements
$for_transfer = true; // bool | Whether or not domain tranfer has been requested

try {
    $result = $api_instance->getAgreement($tlds, $privacy, $x_market_id, $for_transfer);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->getAgreement: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **tlds** | [**string[]**](../Model/string.md)| list of TLDs whose legal agreements are to be retrieved |
 **privacy** | **bool**| Whether or not privacy has been requested |
 **x_market_id** | **string**| Unique identifier of the Market used to retrieve/translate Legal Agreements | [optional] [default to en-US]
 **for_transfer** | **bool**| Whether or not domain tranfer has been requested | [optional]

### Return type

[**\GoDaddyDomainsClient\Model\LegalAgreement[]**](../Model/LegalAgreement.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **identityDocumentsUpload**
> identityDocumentsUpload($x_shopper_id, $body)

Upload an identity document for Real Name Validation

`body.consent.agreementKeys` must specify 23957<br/> On success in OTE, the domain will be automatically validated<br/> On success in Production, the domain will be manually validated

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$x_shopper_id = "x_shopper_id_example"; // string | Shopper for whom Domain is to be updated
$body = new \GoDaddyDomainsClient\Model\IdentityDocumentCreate(); // \GoDaddyDomainsClient\Model\IdentityDocumentCreate | Identity document to create

try {
    $api_instance->identityDocumentsUpload($x_shopper_id, $body);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->identityDocumentsUpload: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_shopper_id** | **string**| Shopper for whom Domain is to be updated |
 **body** | [**\GoDaddyDomainsClient\Model\IdentityDocumentCreate**](../Model/\GoDaddyDomainsClient\Model\IdentityDocumentCreate.md)| Identity document to create |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **purchase**
> \GoDaddyDomainsClient\Model\DomainPurchaseResponse purchase($body, $x_shopper_id)

Purchase and register the specified Domain

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$body = new \GoDaddyDomainsClient\Model\DomainPurchase(); // \GoDaddyDomainsClient\Model\DomainPurchase | An instance document expected to match the JSON schema returned by `./schema/{tld}`
$x_shopper_id = "x_shopper_id_example"; // string | The Shopper for whom the domain should be purchased

try {
    $result = $api_instance->purchase($body, $x_shopper_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->purchase: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\GoDaddyDomainsClient\Model\DomainPurchase**](../Model/\GoDaddyDomainsClient\Model\DomainPurchase.md)| An instance document expected to match the JSON schema returned by &#x60;./schema/{tld}&#x60; |
 **x_shopper_id** | **string**| The Shopper for whom the domain should be purchased | [optional]

### Return type

[**\GoDaddyDomainsClient\Model\DomainPurchaseResponse**](../Model/DomainPurchaseResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **purchasePrivacy**
> \GoDaddyDomainsClient\Model\DomainPurchaseResponse purchasePrivacy($domain, $body, $x_shopper_id)

Purchase privacy for a specified domain

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain for which to purchase privacy
$body = new \GoDaddyDomainsClient\Model\PrivacyPurchase(); // \GoDaddyDomainsClient\Model\PrivacyPurchase | Options for purchasing privacy
$x_shopper_id = "x_shopper_id_example"; // string | Shopper ID of the owner of the domain

try {
    $result = $api_instance->purchasePrivacy($domain, $body, $x_shopper_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->purchasePrivacy: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain for which to purchase privacy |
 **body** | [**\GoDaddyDomainsClient\Model\PrivacyPurchase**](../Model/\GoDaddyDomainsClient\Model\PrivacyPurchase.md)| Options for purchasing privacy |
 **x_shopper_id** | **string**| Shopper ID of the owner of the domain | [optional]

### Return type

[**\GoDaddyDomainsClient\Model\DomainPurchaseResponse**](../Model/DomainPurchaseResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **recordAdd**
> recordAdd($domain, $records, $x_shopper_id)

Add the specified DNS Records to the specified Domain

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain whose DNS Records are to be augmented
$records = new \GoDaddyDomainsClient\Model\DNSRecord(); // \GoDaddyDomainsClient\Model\DNSRecord | DNS Records to add to whatever currently exists
$x_shopper_id = "x_shopper_id_example"; // string | Shopper ID which owns the domain. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you're a Reseller, but purchased a Domain via http://www.godaddy.com

try {
    $api_instance->recordAdd($domain, $records, $x_shopper_id);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->recordAdd: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain whose DNS Records are to be augmented |
 **records** | [**\GoDaddyDomainsClient\Model\DNSRecord**](../Model/\GoDaddyDomainsClient\Model\DNSRecord.md)| DNS Records to add to whatever currently exists |
 **x_shopper_id** | **string**| Shopper ID which owns the domain. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you&#39;re a Reseller, but purchased a Domain via http://www.godaddy.com | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **recordGet**
> \GoDaddyDomainsClient\Model\DNSRecord[] recordGet($domain, $type, $name, $x_shopper_id, $offset, $limit)

Retrieve DNS Records for the specified Domain, optionally with the specified Type and/or Name

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain whose DNS Records are to be retrieved
$type = "type_example"; // string | DNS Record Type for which DNS Records are to be retrieved
$name = "name_example"; // string | DNS Record Name for which DNS Records are to be retrieved
$x_shopper_id = "x_shopper_id_example"; // string | Shopper ID which owns the domain. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you're a Reseller, but purchased a Domain via http://www.godaddy.com
$offset = 56; // int | Number of results to skip for pagination
$limit = 56; // int | Maximum number of items to return

try {
    $result = $api_instance->recordGet($domain, $type, $name, $x_shopper_id, $offset, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->recordGet: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain whose DNS Records are to be retrieved |
 **type** | **string**| DNS Record Type for which DNS Records are to be retrieved |
 **name** | **string**| DNS Record Name for which DNS Records are to be retrieved |
 **x_shopper_id** | **string**| Shopper ID which owns the domain. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you&#39;re a Reseller, but purchased a Domain via http://www.godaddy.com | [optional]
 **offset** | **int**| Number of results to skip for pagination | [optional]
 **limit** | **int**| Maximum number of items to return | [optional]

### Return type

[**\GoDaddyDomainsClient\Model\DNSRecord[]**](../Model/DNSRecord.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **recordReplace**
> recordReplace($domain, $records, $x_shopper_id)

Replace all DNS Records for the specified Domain

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain whose DNS Records are to be replaced
$records = array(new DNSRecord()); // \GoDaddyDomainsClient\Model\DNSRecord[] | DNS Records to replace whatever currently exists
$x_shopper_id = "x_shopper_id_example"; // string | Shopper ID which owns the domain. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you're a Reseller, but purchased a Domain via http://www.godaddy.com

try {
    $api_instance->recordReplace($domain, $records, $x_shopper_id);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->recordReplace: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain whose DNS Records are to be replaced |
 **records** | [**\GoDaddyDomainsClient\Model\DNSRecord[]**](../Model/DNSRecord.md)| DNS Records to replace whatever currently exists |
 **x_shopper_id** | **string**| Shopper ID which owns the domain. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you&#39;re a Reseller, but purchased a Domain via http://www.godaddy.com | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **recordReplaceType**
> recordReplaceType($domain, $type, $records, $x_shopper_id)

Replace all DNS Records for the specified Domain with the specified Type

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain whose DNS Records are to be replaced
$type = "type_example"; // string | DNS Record Type for which DNS Records are to be replaced
$records = array(new DNSRecordCreateType()); // \GoDaddyDomainsClient\Model\DNSRecordCreateType[] | DNS Records to replace whatever currently exists
$x_shopper_id = "x_shopper_id_example"; // string | Shopper ID which owns the domain. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you're a Reseller, but purchased a Domain via http://www.godaddy.com

try {
    $api_instance->recordReplaceType($domain, $type, $records, $x_shopper_id);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->recordReplaceType: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain whose DNS Records are to be replaced |
 **type** | **string**| DNS Record Type for which DNS Records are to be replaced |
 **records** | [**\GoDaddyDomainsClient\Model\DNSRecordCreateType[]**](../Model/DNSRecordCreateType.md)| DNS Records to replace whatever currently exists |
 **x_shopper_id** | **string**| Shopper ID which owns the domain. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you&#39;re a Reseller, but purchased a Domain via http://www.godaddy.com | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **recordReplaceTypeName**
> recordReplaceTypeName($domain, $type, $name, $records, $x_shopper_id)

Replace all DNS Records for the specified Domain with the specified Type and Name

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain whose DNS Records are to be replaced
$type = "type_example"; // string | DNS Record Type for which DNS Records are to be replaced
$name = "name_example"; // string | DNS Record Name for which DNS Records are to be replaced
$records = array(new DNSRecordCreateTypeName()); // \GoDaddyDomainsClient\Model\DNSRecordCreateTypeName[] | DNS Records to replace whatever currently exists
$x_shopper_id = "x_shopper_id_example"; // string | Shopper ID which owns the domain. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you're a Reseller, but purchased a Domain via http://www.godaddy.com

try {
    $api_instance->recordReplaceTypeName($domain, $type, $name, $records, $x_shopper_id);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->recordReplaceTypeName: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain whose DNS Records are to be replaced |
 **type** | **string**| DNS Record Type for which DNS Records are to be replaced |
 **name** | **string**| DNS Record Name for which DNS Records are to be replaced |
 **records** | [**\GoDaddyDomainsClient\Model\DNSRecordCreateTypeName[]**](../Model/DNSRecordCreateTypeName.md)| DNS Records to replace whatever currently exists |
 **x_shopper_id** | **string**| Shopper ID which owns the domain. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you&#39;re a Reseller, but purchased a Domain via http://www.godaddy.com | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **renew**
> \GoDaddyDomainsClient\Model\DomainPurchaseResponse renew($domain, $x_shopper_id, $body)

Renew the specified Domain

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain to renew
$x_shopper_id = "x_shopper_id_example"; // string | Shopper for whom Domain is to be renewed. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you're a Reseller, but purchased a Domain via http://www.godaddy.com
$body = new \GoDaddyDomainsClient\Model\DomainRenew(); // \GoDaddyDomainsClient\Model\DomainRenew | Options for renewing existing Domain

try {
    $result = $api_instance->renew($domain, $x_shopper_id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->renew: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain to renew |
 **x_shopper_id** | **string**| Shopper for whom Domain is to be renewed. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you&#39;re a Reseller, but purchased a Domain via http://www.godaddy.com | [optional]
 **body** | [**\GoDaddyDomainsClient\Model\DomainRenew**](../Model/\GoDaddyDomainsClient\Model\DomainRenew.md)| Options for renewing existing Domain | [optional]

### Return type

[**\GoDaddyDomainsClient\Model\DomainPurchaseResponse**](../Model/DomainPurchaseResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **schema**
> \GoDaddyDomainsClient\Model\JsonSchema schema($tld)

Retrieve the schema to be submitted when registering a Domain for the specified TLD



### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$tld = "tld_example"; // string | The Top-Level Domain whose schema should be retrieved

try {
    $result = $api_instance->schema($tld);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->schema: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **tld** | **string**| The Top-Level Domain whose schema should be retrieved |

### Return type

[**\GoDaddyDomainsClient\Model\JsonSchema**](../Model/JsonSchema.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **suggest**
> \GoDaddyDomainsClient\Model\DomainSuggestion[] suggest($query, $x_shopper_id, $country, $city, $sources, $tlds, $length_max, $length_min, $limit, $wait_ms)

Suggest alternate Domain names based on a seed Domain or set of keywords

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$query = "query_example"; // string | Domain name or set of keywords for which alternative domain names will be suggested
$x_shopper_id = "x_shopper_id_example"; // string | Shopper ID for which the suggestions are being generated
$country = "country_example"; // string | Two-letter ISO country code to be used as a hint for target region<br/><br/> NOTE: These are sample values, there are many <a href=\"http://www.iso.org/iso/country_codes.htm\">more</a>
$city = "city_example"; // string | Name of city to be used as a hint for target region
$sources = array("sources_example"); // string[] | Sources to be queried<br/><br/><ul> <li><strong>CC_TLD</strong> - Varies the TLD using Country Codes</li> <li><strong>EXTENSION</strong> - Varies the TLD</li> <li><strong>KEYWORD_SPIN</strong> - Identifies keywords and then rotates each one</li> <li><strong>PREMIUM</strong> - Includes variations with premium prices</li></ul>
$tlds = array("tlds_example"); // string[] | Top-level domains to be included in suggestions<br/><br/> NOTE: These are sample values, there are many <a href=\"http://www.godaddy.com/tlds/gtld.aspx#domain_search_form\">more</a>
$length_max = 56; // int | Maximum length of second-level domain
$length_min = 56; // int | Minimum length of second-level domain
$limit = 56; // int | Maximum number of suggestions to return
$wait_ms = 1000; // int | Maximum amount of time, in milliseconds, to wait for responses If elapses, return the results compiled up to that point

try {
    $result = $api_instance->suggest($query, $x_shopper_id, $country, $city, $sources, $tlds, $length_max, $length_min, $limit, $wait_ms);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->suggest: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **query** | **string**| Domain name or set of keywords for which alternative domain names will be suggested |
 **x_shopper_id** | **string**| Shopper ID for which the suggestions are being generated | [optional]
 **country** | **string**| Two-letter ISO country code to be used as a hint for target region&lt;br/&gt;&lt;br/&gt; NOTE: These are sample values, there are many &lt;a href&#x3D;\&quot;http://www.iso.org/iso/country_codes.htm\&quot;&gt;more&lt;/a&gt; | [optional]
 **city** | **string**| Name of city to be used as a hint for target region | [optional]
 **sources** | [**string[]**](../Model/string.md)| Sources to be queried&lt;br/&gt;&lt;br/&gt;&lt;ul&gt; &lt;li&gt;&lt;strong&gt;CC_TLD&lt;/strong&gt; - Varies the TLD using Country Codes&lt;/li&gt; &lt;li&gt;&lt;strong&gt;EXTENSION&lt;/strong&gt; - Varies the TLD&lt;/li&gt; &lt;li&gt;&lt;strong&gt;KEYWORD_SPIN&lt;/strong&gt; - Identifies keywords and then rotates each one&lt;/li&gt; &lt;li&gt;&lt;strong&gt;PREMIUM&lt;/strong&gt; - Includes variations with premium prices&lt;/li&gt;&lt;/ul&gt; | [optional]
 **tlds** | [**string[]**](../Model/string.md)| Top-level domains to be included in suggestions&lt;br/&gt;&lt;br/&gt; NOTE: These are sample values, there are many &lt;a href&#x3D;\&quot;http://www.godaddy.com/tlds/gtld.aspx#domain_search_form\&quot;&gt;more&lt;/a&gt; | [optional]
 **length_max** | **int**| Maximum length of second-level domain | [optional]
 **length_min** | **int**| Minimum length of second-level domain | [optional]
 **limit** | **int**| Maximum number of suggestions to return | [optional]
 **wait_ms** | **int**| Maximum amount of time, in milliseconds, to wait for responses If elapses, return the results compiled up to that point | [optional] [default to 1000]

### Return type

[**\GoDaddyDomainsClient\Model\DomainSuggestion[]**](../Model/DomainSuggestion.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **tlds**
> \GoDaddyDomainsClient\Model\TldSummary[] tlds()

Retrieves a list of TLDs supported and enabled for sale

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();

try {
    $result = $api_instance->tlds();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->tlds: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\GoDaddyDomainsClient\Model\TldSummary[]**](../Model/TldSummary.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **transferIn**
> \GoDaddyDomainsClient\Model\DomainPurchaseResponse transferIn($domain, $body, $x_shopper_id)

Purchase and start or restart transfer process

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain to transfer in
$body = new \GoDaddyDomainsClient\Model\DomainTransferIn(); // \GoDaddyDomainsClient\Model\DomainTransferIn | Details for domain transfer purchase
$x_shopper_id = "x_shopper_id_example"; // string | The Shopper to whom the domain should be transfered

try {
    $result = $api_instance->transferIn($domain, $body, $x_shopper_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->transferIn: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain to transfer in |
 **body** | [**\GoDaddyDomainsClient\Model\DomainTransferIn**](../Model/\GoDaddyDomainsClient\Model\DomainTransferIn.md)| Details for domain transfer purchase |
 **x_shopper_id** | **string**| The Shopper to whom the domain should be transfered | [optional]

### Return type

[**\GoDaddyDomainsClient\Model\DomainPurchaseResponse**](../Model/DomainPurchaseResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **update**
> update($domain, $body, $x_shopper_id)

Update details for the specified Domain

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain whose details are to be updated
$body = new \GoDaddyDomainsClient\Model\DomainUpdate(); // \GoDaddyDomainsClient\Model\DomainUpdate | Changes to apply to existing Domain
$x_shopper_id = "x_shopper_id_example"; // string | Shopper for whom Domain is to be updated. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you're a Reseller, but purchased a Domain via http://www.godaddy.com

try {
    $api_instance->update($domain, $body, $x_shopper_id);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->update: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain whose details are to be updated |
 **body** | [**\GoDaddyDomainsClient\Model\DomainUpdate**](../Model/\GoDaddyDomainsClient\Model\DomainUpdate.md)| Changes to apply to existing Domain |
 **x_shopper_id** | **string**| Shopper for whom Domain is to be updated. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you&#39;re a Reseller, but purchased a Domain via http://www.godaddy.com | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateContacts**
> updateContacts($domain, $contacts, $x_shopper_id)

Update domain

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain whose Contacts are to be updated.
$contacts = new \GoDaddyDomainsClient\Model\DomainContacts(); // \GoDaddyDomainsClient\Model\DomainContacts | Changes to apply to existing Contacts
$x_shopper_id = "x_shopper_id_example"; // string | Shopper for whom domain contacts are to be updated. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you're a Reseller, but purchased a Domain via http://www.godaddy.com

try {
    $api_instance->updateContacts($domain, $contacts, $x_shopper_id);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->updateContacts: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain whose Contacts are to be updated. |
 **contacts** | [**\GoDaddyDomainsClient\Model\DomainContacts**](../Model/\GoDaddyDomainsClient\Model\DomainContacts.md)| Changes to apply to existing Contacts |
 **x_shopper_id** | **string**| Shopper for whom domain contacts are to be updated. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you&#39;re a Reseller, but purchased a Domain via http://www.godaddy.com | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **validate**
> validate($body)

Validate the request body using the Domain Purchase Schema for the specified TLD



### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$body = new \GoDaddyDomainsClient\Model\DomainPurchase(); // \GoDaddyDomainsClient\Model\DomainPurchase | An instance document expected to match the JSON schema returned by `./schema/{tld}`

try {
    $api_instance->validate($body);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->validate: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\GoDaddyDomainsClient\Model\DomainPurchase**](../Model/\GoDaddyDomainsClient\Model\DomainPurchase.md)| An instance document expected to match the JSON schema returned by &#x60;./schema/{tld}&#x60; |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **verifyEmail**
> verifyEmail($domain, $x_shopper_id)

Re-send Contact E-mail Verification for specified Domain

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new GoDaddyDomainsClient\Api\VdomainsApi();
$domain = "domain_example"; // string | Domain whose Contact E-mail should be verified.
$x_shopper_id = "x_shopper_id_example"; // string | Shopper for whom domain contact e-mail should be verified. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you're a Reseller, but purchased a Domain via http://www.godaddy.com

try {
    $api_instance->verifyEmail($domain, $x_shopper_id);
} catch (Exception $e) {
    echo 'Exception when calling VdomainsApi->verifyEmail: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **string**| Domain whose Contact E-mail should be verified. |
 **x_shopper_id** | **string**| Shopper for whom domain contact e-mail should be verified. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you&#39;re a Reseller, but purchased a Domain via http://www.godaddy.com | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, application/xml, text/xml
 - **Accept**: application/json, application/javascript, application/xml, text/javascript, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

