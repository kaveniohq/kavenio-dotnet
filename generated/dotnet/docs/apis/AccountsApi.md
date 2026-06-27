# Kavenio.Sdk.Api.AccountsApi

All URIs are relative to *https://api.kavenio.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CheckAccountHealth**](AccountsApi.md#checkaccounthealth) | **POST** /v1/accounts/{accountId}/health | Check account health |
| [**DisconnectAccount**](AccountsApi.md#disconnectaccount) | **POST** /v1/accounts/{accountId}/disconnect | Disconnect an account |
| [**GetAccount**](AccountsApi.md#getaccount) | **GET** /v1/accounts/{accountId} | Get a connected account |
| [**ListAccounts**](AccountsApi.md#listaccounts) | **GET** /v1/accounts | List connected accounts |
| [**MoveAccount**](AccountsApi.md#moveaccount) | **POST** /v1/accounts/{accountId}/move | Move a connected account |
| [**RefreshTikTokCreatorInfo**](AccountsApi.md#refreshtiktokcreatorinfo) | **POST** /v1/accounts/{accountId}/tiktok/creator-info | Refresh TikTok creator info |
| [**ReplaceAccount**](AccountsApi.md#replaceaccount) | **PUT** /v1/accounts/{accountId} | Replace account fields |
| [**UpdateAccount**](AccountsApi.md#updateaccount) | **PATCH** /v1/accounts/{accountId} | Update a connected account |

<a id="checkaccounthealth"></a>
# **CheckAccountHealth**
> CheckAccountHealth200Response CheckAccountHealth (string accountId)

Check account health

Refreshes account health and readiness information for a connected account.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**CheckAccountHealth200Response**](CheckAccountHealth200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Account health returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **422** | Path parameter validation failed. |  -  |
| **500** | Account health check failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="disconnectaccount"></a>
# **DisconnectAccount**
> DisconnectAccount200Response DisconnectAccount (string accountId)

Disconnect an account

Disconnects a connected account and returns the resulting account state.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**DisconnectAccount200Response**](DisconnectAccount200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connected account disconnected. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **409** | Connected account cannot be disconnected. |  -  |
| **422** | Path parameter validation failed. |  -  |
| **500** | Connected account disconnect failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getaccount"></a>
# **GetAccount**
> GetAccount200Response GetAccount (string accountId)

Get a connected account

Returns one connected account by ID.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**GetAccount200Response**](GetAccount200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connected account returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **422** | Path parameter validation failed. |  -  |
| **500** | Connected account lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listaccounts"></a>
# **ListAccounts**
> ListAccounts200Response ListAccounts (string profileId = null, string platform = null, string status = null, int limit = null, string cursor = null)

List connected accounts

Returns connected social accounts for the authenticated organization.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  | [optional]  |
| **platform** | **string** |  | [optional]  |
| **status** | **string** |  | [optional]  |
| **limit** | **int** |  | [optional]  |
| **cursor** | **string** |  | [optional]  |

### Return type

[**ListAccounts200Response**](ListAccounts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connected accounts returned. |  -  |
| **401** | Authentication failed. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Connected account lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="moveaccount"></a>
# **MoveAccount**
> GetAccount200Response MoveAccount (string accountId, MoveAccountRequest moveAccountRequest)

Move a connected account

Moves a connected account to another profile.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **moveAccountRequest** | [**MoveAccountRequest**](MoveAccountRequest.md) |  |  |

### Return type

[**GetAccount200Response**](GetAccount200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connected account moved. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account or profile not found. |  -  |
| **409** | Connected account cannot be moved. |  -  |
| **422** | Request validation failed. |  -  |
| **500** | Connected account move failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="refreshtiktokcreatorinfo"></a>
# **RefreshTikTokCreatorInfo**
> RefreshTikTokCreatorInfo200Response RefreshTikTokCreatorInfo (string accountId)

Refresh TikTok creator info

Refreshes TikTok creator information and posting readiness for a connected account.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**RefreshTikTokCreatorInfo200Response**](RefreshTikTokCreatorInfo200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | TikTok creator information returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **422** | Path parameter validation failed. |  -  |
| **500** | TikTok creator information refresh failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="replaceaccount"></a>
# **ReplaceAccount**
> GetAccount200Response ReplaceAccount (string accountId, ReplaceAccountRequest replaceAccountRequest)

Replace account fields

Updates editable connected account fields. Public metadata updates must not include provider credential fields.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **replaceAccountRequest** | [**ReplaceAccountRequest**](ReplaceAccountRequest.md) |  |  |

### Return type

[**GetAccount200Response**](GetAccount200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connected account updated. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **409** | Connected account cannot be updated. |  -  |
| **422** | Request validation failed. |  -  |
| **500** | Connected account update failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updateaccount"></a>
# **UpdateAccount**
> GetAccount200Response UpdateAccount (string accountId, ReplaceAccountRequest replaceAccountRequest)

Update a connected account

Partially updates editable connected account fields. Public metadata updates must not include provider credential fields.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **replaceAccountRequest** | [**ReplaceAccountRequest**](ReplaceAccountRequest.md) |  |  |

### Return type

[**GetAccount200Response**](GetAccount200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connected account updated. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **409** | Connected account cannot be updated. |  -  |
| **422** | Request validation failed. |  -  |
| **500** | Connected account update failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

