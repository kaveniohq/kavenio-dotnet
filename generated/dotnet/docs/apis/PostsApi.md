# Kavenio.Sdk.Api.PostsApi

All URIs are relative to *https://api.kavenio.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BulkUploadPosts**](PostsApi.md#bulkuploadposts) | **POST** /v1/posts/bulk-upload | Bulk upload posts |
| [**CreatePost**](PostsApi.md#createpost) | **POST** /v1/posts | Create a post |
| [**DeletePost**](PostsApi.md#deletepost) | **DELETE** /v1/posts/{postId} | Delete a post |
| [**EditPublishedPost**](PostsApi.md#editpublishedpost) | **POST** /v1/posts/{postId}/edit | Edit a published post |
| [**GetPost**](PostsApi.md#getpost) | **GET** /v1/posts/{postId} | Get a post |
| [**ListPosts**](PostsApi.md#listposts) | **GET** /v1/posts | List posts |
| [**ReplacePost**](PostsApi.md#replacepost) | **PUT** /v1/posts/{postId} | Replace post fields |
| [**RetryPost**](PostsApi.md#retrypost) | **POST** /v1/posts/{postId}/retry | Retry post publishing |
| [**UnpublishPost**](PostsApi.md#unpublishpost) | **POST** /v1/posts/{postId}/unpublish | Unpublish a post |
| [**UpdatePost**](PostsApi.md#updatepost) | **PATCH** /v1/posts/{postId} | Update a post |

<a id="bulkuploadposts"></a>
# **BulkUploadPosts**
> BulkUploadPosts201Response BulkUploadPosts (BulkUploadPostsRequest bulkUploadPostsRequest)

Bulk upload posts

Creates posts from CSV content and returns per-row creation or validation results.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **bulkUploadPostsRequest** | [**BulkUploadPostsRequest**](BulkUploadPostsRequest.md) |  |  |

### Return type

[**BulkUploadPosts201Response**](BulkUploadPosts201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Bulk upload processed. |  -  |
| **401** | Authentication failed. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Bulk upload failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createpost"></a>
# **CreatePost**
> CreatePost201Response CreatePost (CreatePostRequest createPostRequest)

Create a post

Creates a draft, scheduled post, queue-backed post, or immediate publish request depending on the payload fields.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createPostRequest** | [**CreatePostRequest**](CreatePostRequest.md) |  |  |

### Return type

[**CreatePost201Response**](CreatePost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Post created. |  -  |
| **401** | Authentication failed. |  -  |
| **409** | Post request conflicts with current state. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Post creation failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletepost"></a>
# **DeletePost**
> DeletePost200Response DeletePost (string postId)

Delete a post

Deletes a post by ID and returns the deletion count.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |

### Return type

[**DeletePost200Response**](DeletePost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post deleted. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Post not found. |  -  |
| **409** | Post cannot be deleted in its current state. |  -  |
| **422** | Path parameter validation failed. |  -  |
| **500** | Post deletion failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="editpublishedpost"></a>
# **EditPublishedPost**
> CreatePost201Response EditPublishedPost (string postId, EditPublishedPostRequest editPublishedPostRequest)

Edit a published post

Applies supported lifecycle edits to published platform targets and returns the resulting post state.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |
| **editPublishedPostRequest** | [**EditPublishedPostRequest**](EditPublishedPostRequest.md) |  |  |

### Return type

[**CreatePost201Response**](CreatePost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Published post edit processed. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Post not found. |  -  |
| **409** | Post cannot be edited in its current state. |  -  |
| **422** | Request validation failed. |  -  |
| **500** | Published post edit failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getpost"></a>
# **GetPost**
> CreatePost201Response GetPost (string postId)

Get a post

Returns a post by ID, including platform target state.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |

### Return type

[**CreatePost201Response**](CreatePost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Post not found. |  -  |
| **422** | Path parameter validation failed. |  -  |
| **500** | Post lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listposts"></a>
# **ListPosts**
> ListPosts200Response ListPosts (string profileId = null, string accountId = null, string platform = null, string status = null, string search = null, DateTime fromDate = null, DateTime toDate = null, int page = null, int limit = null)

List posts

Returns posts for the authenticated organization, optionally filtered by profile, account, platform, status, search text, or date range.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  | [optional]  |
| **accountId** | **string** |  | [optional]  |
| **platform** | **string** |  | [optional]  |
| **status** | **string** |  | [optional]  |
| **search** | **string** |  | [optional]  |
| **fromDate** | **DateTime** |  | [optional]  |
| **toDate** | **DateTime** |  | [optional]  |
| **page** | **int** |  | [optional]  |
| **limit** | **int** |  | [optional]  |

### Return type

[**ListPosts200Response**](ListPosts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Posts returned. |  -  |
| **401** | Authentication failed. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Post lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="replacepost"></a>
# **ReplacePost**
> CreatePost201Response ReplacePost (string postId, ReplacePostRequest replacePostRequest)

Replace post fields

Updates editable fields on an existing post and returns the resulting post state.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |
| **replacePostRequest** | [**ReplacePostRequest**](ReplacePostRequest.md) |  |  |

### Return type

[**CreatePost201Response**](CreatePost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post updated. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Post not found. |  -  |
| **409** | Post cannot be updated in its current state. |  -  |
| **422** | Request validation failed. |  -  |
| **500** | Post update failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="retrypost"></a>
# **RetryPost**
> CreatePost201Response RetryPost (string postId, RetryPostRequest retryPostRequest)

Retry post publishing

Retries failed platform targets for a post, optionally limited to specific target IDs.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |
| **retryPostRequest** | [**RetryPostRequest**](RetryPostRequest.md) |  |  |

### Return type

[**CreatePost201Response**](CreatePost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post retry started. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Post not found. |  -  |
| **409** | Post cannot be retried in its current state. |  -  |
| **422** | Request validation failed. |  -  |
| **500** | Post retry failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="unpublishpost"></a>
# **UnpublishPost**
> CreatePost201Response UnpublishPost (string postId, UnpublishPostRequest unpublishPostRequest)

Unpublish a post

Starts unpublishing for published platform targets, optionally limited to specific target IDs.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |
| **unpublishPostRequest** | [**UnpublishPostRequest**](UnpublishPostRequest.md) |  |  |

### Return type

[**CreatePost201Response**](CreatePost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post unpublish started. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Post not found. |  -  |
| **409** | Post cannot be unpublished in its current state. |  -  |
| **422** | Request validation failed. |  -  |
| **500** | Post unpublish failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatepost"></a>
# **UpdatePost**
> CreatePost201Response UpdatePost (string postId, ReplacePostRequest replacePostRequest)

Update a post

Partially updates editable fields on an existing post and returns the resulting post state.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |
| **replacePostRequest** | [**ReplacePostRequest**](ReplacePostRequest.md) |  |  |

### Return type

[**CreatePost201Response**](CreatePost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post updated. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Post not found. |  -  |
| **409** | Post cannot be updated in its current state. |  -  |
| **422** | Request validation failed. |  -  |
| **500** | Post update failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

