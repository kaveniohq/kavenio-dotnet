# Kavenio.Sdk.Api.ValidationApi

All URIs are relative to *https://api.kavenio.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ValidatePost**](ValidationApi.md#validatepost) | **POST** /v1/tools/validate/post | Validate a post |
| [**ValidatePostLength**](ValidationApi.md#validatepostlength) | **POST** /v1/tools/validate/post-length | Validate post length |

<a id="validatepost"></a>
# **ValidatePost**
> ValidatePost200Response ValidatePost (CreatePostRequest createPostRequest)

Validate a post

Validates a post payload against platform and scheduling rules without creating a post.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createPostRequest** | [**CreatePostRequest**](CreatePostRequest.md) |  |  |

### Return type

[**ValidatePost200Response**](ValidatePost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post validation result returned. |  -  |
| **401** | Authentication failed. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Post validation failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="validatepostlength"></a>
# **ValidatePostLength**
> ValidatePostLength200Response ValidatePostLength (ValidatePostLengthRequest validatePostLengthRequest)

Validate post length

Returns character counts and per-platform length validity for the supplied text.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **validatePostLengthRequest** | [**ValidatePostLengthRequest**](ValidatePostLengthRequest.md) |  |  |

### Return type

[**ValidatePostLength200Response**](ValidatePostLength200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post length validation result returned. |  -  |
| **401** | Authentication failed. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Post length validation failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

