# DomainTransferIn

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**auth_code** | **string** | Authorization code from registrar for transferring a domain | 
**period** | **int** | Can be more than 1 but no more than 10 years total including current registration length | [optional] 
**renew_auto** | **bool** | Whether or not the domain should be configured to automatically renew | [optional] 
**privacy** | **bool** | Whether or not privacy has been requested | [optional] 
**consent** | [**\GoDaddyDomainsClient\Model\Consent**](Consent.md) | Required agreements can be retrieved via the GET ./domains/agreements endpoint | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


