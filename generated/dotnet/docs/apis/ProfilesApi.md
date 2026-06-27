# Kavenio.Sdk.Api.ProfilesApi

All URIs are relative to *https://api.kavenio.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateProfile**](ProfilesApi.md#createprofile) | **POST** /v1/profiles | Create a profile |
| [**DeleteProfile**](ProfilesApi.md#deleteprofile) | **DELETE** /v1/profiles/{profileId} | Delete a profile |
| [**GetProfile**](ProfilesApi.md#getprofile) | **GET** /v1/profiles/{profileId} | Get a profile |
| [**ListProfiles**](ProfilesApi.md#listprofiles) | **GET** /v1/profiles | List profiles |
| [**ReplaceProfile**](ProfilesApi.md#replaceprofile) | **PUT** /v1/profiles/{profileId} | Replace profile fields |
| [**UpdateProfile**](ProfilesApi.md#updateprofile) | **PATCH** /v1/profiles/{profileId} | Update a profile |

<a id="createprofile"></a>
# **CreateProfile**
> CreateProfile201Response CreateProfile (CreateProfileRequest createProfileRequest)

Create a profile

Creates a customer-owned profile grouping.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createProfileRequest** | [**CreateProfileRequest**](CreateProfileRequest.md) |  |  |

### Return type

[**CreateProfile201Response**](CreateProfile201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Profile created. |  -  |
| **401** | Authentication failed. |  -  |
| **409** | A profile with this name already exists. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Profile creation failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deleteprofile"></a>
# **DeleteProfile**
> DeleteProfile200Response DeleteProfile (string profileId)

Delete a profile

Deletes a customer-owned profile grouping.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  |  |

### Return type

[**DeleteProfile200Response**](DeleteProfile200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Profile deleted. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Profile not found. |  -  |
| **409** | Profile cannot be deleted in its current state. |  -  |
| **422** | Path parameter validation failed. |  -  |
| **500** | Profile deletion failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getprofile"></a>
# **GetProfile**
> CreateProfile201Response GetProfile (string profileId)

Get a profile

Returns one profile by ID.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  |  |

### Return type

[**CreateProfile201Response**](CreateProfile201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Profile returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Profile not found. |  -  |
| **422** | Path parameter validation failed. |  -  |
| **500** | Profile lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listprofiles"></a>
# **ListProfiles**
> ListProfiles200Response ListProfiles ()

List profiles

Returns the profiles available to the authenticated organization.


### Parameters
This endpoint does not need any parameter.
### Return type

[**ListProfiles200Response**](ListProfiles200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Profiles returned. |  -  |
| **401** | Authentication failed. |  -  |
| **500** | Profile lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="replaceprofile"></a>
# **ReplaceProfile**
> CreateProfile201Response ReplaceProfile (string profileId, ReplaceProfileRequest replaceProfileRequest)

Replace profile fields

Updates profile fields for an existing customer-owned grouping.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  |  |
| **replaceProfileRequest** | [**ReplaceProfileRequest**](ReplaceProfileRequest.md) |  |  |

### Return type

[**CreateProfile201Response**](CreateProfile201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Profile updated. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Profile not found. |  -  |
| **409** | A profile with this name already exists. |  -  |
| **422** | Request validation failed. |  -  |
| **500** | Profile update failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updateprofile"></a>
# **UpdateProfile**
> CreateProfile201Response UpdateProfile (string profileId, ReplaceProfileRequest replaceProfileRequest)

Update a profile

Partially updates profile fields for an existing customer-owned grouping.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  |  |
| **replaceProfileRequest** | [**ReplaceProfileRequest**](ReplaceProfileRequest.md) |  |  |

### Return type

[**CreateProfile201Response**](CreateProfile201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Profile updated. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Profile not found. |  -  |
| **409** | A profile with this name already exists. |  -  |
| **422** | Request validation failed. |  -  |
| **500** | Profile update failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

