# Kavenio.Sdk.Api.MediaApi

All URIs are relative to *https://api.kavenio.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateMediaPresign**](MediaApi.md#createmediapresign) | **POST** /v1/media/presign | Create a media presign URL |
| [**UploadMediaBatch**](MediaApi.md#uploadmediabatch) | **POST** /v1/media/upload | Upload media |
| [**ValidateMedia**](MediaApi.md#validatemedia) | **POST** /v1/tools/validate/media | Validate media |

<a id="createmediapresign"></a>
# **CreateMediaPresign**
> CreateMediaPresign200Response CreateMediaPresign (CreateMediaPresignRequest createMediaPresignRequest)

Create a media presign URL

Creates a short-lived upload URL and public media URL for direct upload workflows.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createMediaPresignRequest** | [**CreateMediaPresignRequest**](CreateMediaPresignRequest.md) |  |  |

### Return type

[**CreateMediaPresign200Response**](CreateMediaPresign200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Presign URL created. |  -  |
| **401** | Authentication failed. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Media presign failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="uploadmediabatch"></a>
# **UploadMediaBatch**
> UploadMediaBatch200Response UploadMediaBatch (UploadMediaBatchRequest uploadMediaBatchRequest)

Upload media

Uploads one or more base64-encoded media items and returns public URLs.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **uploadMediaBatchRequest** | [**UploadMediaBatchRequest**](UploadMediaBatchRequest.md) |  |  |

### Return type

[**UploadMediaBatch200Response**](UploadMediaBatch200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Media uploaded. |  -  |
| **401** | Authentication failed. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Media upload failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="validatemedia"></a>
# **ValidateMedia**
> ValidateMedia200Response ValidateMedia (ValidateMediaRequest validateMediaRequest)

Validate media

Validates a public media URL and returns content type, size, type, and platform limit information when available.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **validateMediaRequest** | [**ValidateMediaRequest**](ValidateMediaRequest.md) |  |  |

### Return type

[**ValidateMedia200Response**](ValidateMedia200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Media validation result returned. |  -  |
| **401** | Authentication failed. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Media validation failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

