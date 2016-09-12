# ErrorField

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**path** | **string** | &lt;ul&gt; &lt;li style&#x3D;&#39;margin-left: 12px;&#39;&gt;JSONPath referring to a field containing an error&lt;/li&gt; &lt;strong style&#x3D;&#39;margin-left: 12px;&#39;&gt;OR&lt;/strong&gt; &lt;li style&#x3D;&#39;margin-left: 12px;&#39;&gt;JSONPath referring to a field that refers to an object containing an error, with more detail in &#x60;pathRelated&#x60;&lt;/li&gt; &lt;/ul&gt; | 
**path_related** | **string** | JSONPath referring to a field containing an error, which is referenced by &#x60;path&#x60; | [optional] 
**code** | **string** | Short identifier for the error, suitable for indicating the specific error within client code | 
**message** | **string** | Human-readable, English description of the problem with the contents of the field | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


