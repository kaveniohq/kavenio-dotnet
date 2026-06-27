# Kavenio.Sdk.Api.QueueApi

All URIs are relative to *https://api.kavenio.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateQueueSlotSchedule**](QueueApi.md#createqueueslotschedule) | **POST** /v1/queue/slots | Create a queue schedule |
| [**DeleteQueueSlotSchedule**](QueueApi.md#deletequeueslotschedule) | **DELETE** /v1/queue/slots | Delete a queue schedule |
| [**GetNextQueueSlot**](QueueApi.md#getnextqueueslot) | **GET** /v1/queue/next-slot | Get next queue slot |
| [**ListQueueSlots**](QueueApi.md#listqueueslots) | **GET** /v1/queue/slots | List queue schedules |
| [**PreviewQueueSlots**](QueueApi.md#previewqueueslots) | **GET** /v1/queue/preview | Preview queue slots |
| [**UpdateQueueSlotSchedule**](QueueApi.md#updatequeueslotschedule) | **PUT** /v1/queue/slots | Update a queue schedule |

<a id="createqueueslotschedule"></a>
# **CreateQueueSlotSchedule**
> UpdateQueueSlotSchedule200Response CreateQueueSlotSchedule (CreateQueueSlotScheduleRequest createQueueSlotScheduleRequest)

Create a queue schedule

Creates a reusable posting queue schedule for a profile.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createQueueSlotScheduleRequest** | [**CreateQueueSlotScheduleRequest**](CreateQueueSlotScheduleRequest.md) |  |  |

### Return type

[**UpdateQueueSlotSchedule200Response**](UpdateQueueSlotSchedule200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Queue schedule created. |  -  |
| **401** | Authentication failed. |  -  |
| **409** | Queue schedule conflicts with current state. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Queue creation failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletequeueslotschedule"></a>
# **DeleteQueueSlotSchedule**
> DeletePost200Response DeleteQueueSlotSchedule (string profileId, string queueId)

Delete a queue schedule

Deletes a reusable posting queue schedule by profile and queue ID.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  |  |
| **queueId** | **string** |  |  |

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
| **200** | Queue schedule deleted. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Queue schedule not found. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Queue deletion failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getnextqueueslot"></a>
# **GetNextQueueSlot**
> PreviewQueueSlots200Response GetNextQueueSlot (string profileId, string queueId = null, DateTime after = null)

Get next queue slot

Returns the next scheduled posting slot for a profile queue. The response uses the queue preview shape with at most one slot.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  |  |
| **queueId** | **string** |  | [optional]  |
| **after** | **DateTime** |  | [optional]  |

### Return type

[**PreviewQueueSlots200Response**](PreviewQueueSlots200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Next queue slot returned. |  -  |
| **401** | Authentication failed. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Next queue slot lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listqueueslots"></a>
# **ListQueueSlots**
> ListQueueSlots200Response ListQueueSlots (string profileId, string queueId = null, string all = null)

List queue schedules

Returns queue schedules for a profile, optionally filtered to one queue.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  |  |
| **queueId** | **string** |  | [optional]  |
| **all** | **string** |  | [optional]  |

### Return type

[**ListQueueSlots200Response**](ListQueueSlots200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Queue schedules returned. |  -  |
| **401** | Authentication failed. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Queue lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="previewqueueslots"></a>
# **PreviewQueueSlots**
> PreviewQueueSlots200Response PreviewQueueSlots (string profileId, string queueId = null, int count = null, DateTime after = null)

Preview queue slots

Returns upcoming scheduled times for a profile queue without creating posts.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  |  |
| **queueId** | **string** |  | [optional]  |
| **count** | **int** |  | [optional]  |
| **after** | **DateTime** |  | [optional]  |

### Return type

[**PreviewQueueSlots200Response**](PreviewQueueSlots200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Queue preview returned. |  -  |
| **401** | Authentication failed. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Queue preview failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatequeueslotschedule"></a>
# **UpdateQueueSlotSchedule**
> UpdateQueueSlotSchedule200Response UpdateQueueSlotSchedule (UpdateQueueSlotScheduleRequest updateQueueSlotScheduleRequest)

Update a queue schedule

Updates a reusable posting queue schedule and returns the resulting schedule.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **updateQueueSlotScheduleRequest** | [**UpdateQueueSlotScheduleRequest**](UpdateQueueSlotScheduleRequest.md) |  |  |

### Return type

[**UpdateQueueSlotSchedule200Response**](UpdateQueueSlotSchedule200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Queue schedule updated. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Queue schedule not found. |  -  |
| **409** | Queue schedule conflicts with current state. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Queue update failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

