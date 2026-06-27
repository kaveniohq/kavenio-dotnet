# Kavenio.Sdk.Api.ConnectApi

All URIs are relative to *https://api.kavenio.com*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BeginConnect**](ConnectApi.md#beginconnect) | **POST** /v1/connect/begin | Begin OAuth connect |
| [**CompleteConnect**](ConnectApi.md#completeconnect) | **POST** /v1/connect/complete | Complete OAuth connect |
| [**CompleteHostedConnectCallback**](ConnectApi.md#completehostedconnectcallback) | **GET** /v1/connect/callback | Complete hosted OAuth callback |
| [**CompleteTokenConnect**](ConnectApi.md#completetokenconnect) | **POST** /v1/connect/token | Complete token connect |
| [**ConnectBlueskyCredentials**](ConnectApi.md#connectblueskycredentials) | **POST** /v1/connect/bluesky/credentials | Connect Bluesky credentials |
| [**ConnectTelegramCredentials**](ConnectApi.md#connecttelegramcredentials) | **POST** /v1/connect/telegram/credentials | Connect Telegram credentials |
| [**ListConnectProviders**](ConnectApi.md#listconnectproviders) | **GET** /v1/connect/providers | List connect providers |
| [**ListFacebookPages**](ConnectApi.md#listfacebookpages) | **GET** /v1/connect/facebook/pages | List Facebook Pages |
| [**ListGoogleBusinessConnectLocations**](ConnectApi.md#listgooglebusinessconnectlocations) | **GET** /v1/connect/googlebusiness/locations | List Google Business connect locations |
| [**ListInstagramAccounts**](ConnectApi.md#listinstagramaccounts) | **GET** /v1/connect/instagram/accounts | List Instagram accounts |
| [**ListLinkedInOrganizations**](ConnectApi.md#listlinkedinorganizations) | **GET** /v1/connect/linkedin/organizations | List LinkedIn organizations |
| [**ListPinterestBoards**](ConnectApi.md#listpinterestboards) | **GET** /v1/connect/pinterest/boards | List Pinterest boards |
| [**ListRedditFlairs**](ConnectApi.md#listredditflairs) | **GET** /v1/connect/reddit/flairs | List Reddit flairs |
| [**ListRedditSubreddits**](ConnectApi.md#listredditsubreddits) | **GET** /v1/connect/reddit/subreddits | List Reddit subreddits |
| [**ListYouTubeChannels**](ConnectApi.md#listyoutubechannels) | **GET** /v1/connect/youtube/channels | List YouTube channels |
| [**ListYouTubePlaylists**](ConnectApi.md#listyoutubeplaylists) | **GET** /v1/connect/youtube/playlists | List YouTube playlists |
| [**SelectFacebookPage**](ConnectApi.md#selectfacebookpage) | **POST** /v1/connect/facebook/select-page | Select Facebook Page |
| [**SelectGoogleBusinessLocation**](ConnectApi.md#selectgooglebusinesslocation) | **POST** /v1/connect/googlebusiness/select-location | Select Google Business location |
| [**SelectInstagramAccount**](ConnectApi.md#selectinstagramaccount) | **POST** /v1/connect/instagram/select-account | Select Instagram account |
| [**SelectLinkedInOrganization**](ConnectApi.md#selectlinkedinorganization) | **POST** /v1/connect/linkedin/select-organization | Select LinkedIn organization |
| [**SelectPinterestBoard**](ConnectApi.md#selectpinterestboard) | **POST** /v1/connect/pinterest/select-board | Select Pinterest board |
| [**SelectYouTubeChannel**](ConnectApi.md#selectyoutubechannel) | **POST** /v1/connect/youtube/select-channel | Select YouTube channel |

<a id="beginconnect"></a>
# **BeginConnect**
> BeginConnect200Response BeginConnect (BeginConnectRequest beginConnectRequest)

Begin OAuth connect

Creates an OAuth connect session and returns the provider authorization URL.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **beginConnectRequest** | [**BeginConnectRequest**](BeginConnectRequest.md) |  |  |

### Return type

[**BeginConnect200Response**](BeginConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connect session created. |  -  |
| **401** | Authentication failed. |  -  |
| **409** | Provider cannot be connected in the current state. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Connect session creation failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="completeconnect"></a>
# **CompleteConnect**
> CompleteConnect200Response CompleteConnect (CompleteConnectRequest completeConnectRequest)

Complete OAuth connect

Completes an OAuth connect session using the provider authorization code.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **completeConnectRequest** | [**CompleteConnectRequest**](CompleteConnectRequest.md) |  |  |

### Return type

[**CompleteConnect200Response**](CompleteConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connect session completed. |  -  |
| **401** | Authentication failed. |  -  |
| **409** | Connect session cannot be completed. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Connect completion failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="completehostedconnectcallback"></a>
# **CompleteHostedConnectCallback**
> void CompleteHostedConnectCallback (string state = null, string code = null, string error = null)

Complete hosted OAuth callback

Handles provider OAuth redirects for hosted connect flows and redirects back to the Kavenio app with the connection result.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **state** | **string** |  | [optional]  |
| **code** | **string** |  | [optional]  |
| **error** | **string** |  | [optional]  |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **302** | Redirects to the configured Kavenio app completion URL with connection status query parameters. |  -  |
| **500** | Hosted connect callback failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="completetokenconnect"></a>
# **CompleteTokenConnect**
> CompleteConnect200Response CompleteTokenConnect (CompleteTokenConnectRequest completeTokenConnectRequest)

Complete token connect

Connects a provider that requires user-supplied token credentials. Raw tokens are accepted only in the request and are never returned.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **completeTokenConnectRequest** | [**CompleteTokenConnectRequest**](CompleteTokenConnectRequest.md) |  |  |

### Return type

[**CompleteConnect200Response**](CompleteConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Token connect completed. |  -  |
| **401** | Authentication failed. |  -  |
| **409** | Provider cannot be connected in the current state. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Token connect failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="connectblueskycredentials"></a>
# **ConnectBlueskyCredentials**
> CompleteConnect200Response ConnectBlueskyCredentials (ConnectBlueskyCredentialsRequest connectBlueskyCredentialsRequest)

Connect Bluesky credentials

Connects a Bluesky account using an identifier and app password. The app password is accepted only in the request and is never returned.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **connectBlueskyCredentialsRequest** | [**ConnectBlueskyCredentialsRequest**](ConnectBlueskyCredentialsRequest.md) |  |  |

### Return type

[**CompleteConnect200Response**](CompleteConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bluesky account connected. |  -  |
| **401** | Authentication failed. |  -  |
| **409** | Bluesky account cannot be connected. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Bluesky credential connect failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="connecttelegramcredentials"></a>
# **ConnectTelegramCredentials**
> CompleteConnect200Response ConnectTelegramCredentials (ConnectTelegramCredentialsRequest connectTelegramCredentialsRequest)

Connect Telegram credentials

Connects a Telegram bot or chat using supplied credentials. The bot token is accepted only in the request and is never returned.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **connectTelegramCredentialsRequest** | [**ConnectTelegramCredentialsRequest**](ConnectTelegramCredentialsRequest.md) |  |  |

### Return type

[**CompleteConnect200Response**](CompleteConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Telegram account connected. |  -  |
| **401** | Authentication failed. |  -  |
| **409** | Telegram account cannot be connected. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Telegram credential connect failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listconnectproviders"></a>
# **ListConnectProviders**
> ListConnectProviders200Response ListConnectProviders ()

List connect providers

Returns social and ads providers available to the authenticated user.


### Parameters
This endpoint does not need any parameter.
### Return type

[**ListConnectProviders200Response**](ListConnectProviders200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connect providers returned. |  -  |
| **401** | Authentication failed. |  -  |
| **500** | Connect provider lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listfacebookpages"></a>
# **ListFacebookPages**
> ListFacebookPages200Response ListFacebookPages (string accountId)

List Facebook Pages

Returns Facebook Pages available from a connected Facebook account.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**ListFacebookPages200Response**](ListFacebookPages200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Facebook Pages returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Facebook Page lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listgooglebusinessconnectlocations"></a>
# **ListGoogleBusinessConnectLocations**
> ListGoogleBusinessConnectLocations200Response ListGoogleBusinessConnectLocations (string accountId, int pageSize = null, string pageToken = null, string search = null, string filter = null)

List Google Business connect locations

Returns Google Business locations available during account connection.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **pageSize** | **int** |  | [optional]  |
| **pageToken** | **string** |  | [optional]  |
| **search** | **string** |  | [optional]  |
| **filter** | **string** |  | [optional]  |

### Return type

[**ListGoogleBusinessConnectLocations200Response**](ListGoogleBusinessConnectLocations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Google Business locations returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Google Business location lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listinstagramaccounts"></a>
# **ListInstagramAccounts**
> ListInstagramAccounts200Response ListInstagramAccounts (string accountId)

List Instagram accounts

Returns Instagram business or creator accounts available from a connected account.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**ListInstagramAccounts200Response**](ListInstagramAccounts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Instagram accounts returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Instagram account lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listlinkedinorganizations"></a>
# **ListLinkedInOrganizations**
> ListLinkedInOrganizations200Response ListLinkedInOrganizations (string accountId)

List LinkedIn organizations

Returns LinkedIn organizations available from a connected LinkedIn account.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**ListLinkedInOrganizations200Response**](ListLinkedInOrganizations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | LinkedIn organizations returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | LinkedIn organization lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listpinterestboards"></a>
# **ListPinterestBoards**
> ListPinterestBoards200Response ListPinterestBoards (string accountId)

List Pinterest boards

Returns Pinterest boards available from a connected Pinterest account.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**ListPinterestBoards200Response**](ListPinterestBoards200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Pinterest boards returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Pinterest board lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listredditflairs"></a>
# **ListRedditFlairs**
> ListRedditFlairs200Response ListRedditFlairs (string accountId, string subreddit)

List Reddit flairs

Returns post flair choices for a connected Reddit account and subreddit.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **subreddit** | **string** |  |  |

### Return type

[**ListRedditFlairs200Response**](ListRedditFlairs200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reddit flairs returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account or subreddit not found. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Reddit flair lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listredditsubreddits"></a>
# **ListRedditSubreddits**
> ListRedditSubreddits200Response ListRedditSubreddits (string accountId)

List Reddit subreddits

Returns Reddit subreddits available from a connected Reddit account.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**ListRedditSubreddits200Response**](ListRedditSubreddits200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reddit subreddits returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | Reddit subreddit lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listyoutubechannels"></a>
# **ListYouTubeChannels**
> ListYouTubeChannels200Response ListYouTubeChannels (string accountId)

List YouTube channels

Returns YouTube channels available from a connected YouTube account.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**ListYouTubeChannels200Response**](ListYouTubeChannels200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | YouTube channels returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | YouTube channel lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listyoutubeplaylists"></a>
# **ListYouTubePlaylists**
> ListYouTubePlaylists200Response ListYouTubePlaylists (string accountId)

List YouTube playlists

Returns YouTube playlists available from a connected YouTube account.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**ListYouTubePlaylists200Response**](ListYouTubePlaylists200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | YouTube playlists returned. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account not found. |  -  |
| **422** | Query parameter validation failed. |  -  |
| **500** | YouTube playlist lookup failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="selectfacebookpage"></a>
# **SelectFacebookPage**
> CompleteConnect200Response SelectFacebookPage (SelectFacebookPageRequest selectFacebookPageRequest)

Select Facebook Page

Selects a Facebook Page destination and attaches it to a profile.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **selectFacebookPageRequest** | [**SelectFacebookPageRequest**](SelectFacebookPageRequest.md) |  |  |

### Return type

[**CompleteConnect200Response**](CompleteConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Facebook Page selected. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account or Page not found. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Facebook Page selection failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="selectgooglebusinesslocation"></a>
# **SelectGoogleBusinessLocation**
> CompleteConnect200Response SelectGoogleBusinessLocation (SelectGoogleBusinessLocationRequest selectGoogleBusinessLocationRequest)

Select Google Business location

Selects a Google Business location destination and attaches it to a profile.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **selectGoogleBusinessLocationRequest** | [**SelectGoogleBusinessLocationRequest**](SelectGoogleBusinessLocationRequest.md) |  |  |

### Return type

[**CompleteConnect200Response**](CompleteConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Google Business location selected. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account or location not found. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Google Business location selection failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="selectinstagramaccount"></a>
# **SelectInstagramAccount**
> CompleteConnect200Response SelectInstagramAccount (SelectInstagramAccountRequest selectInstagramAccountRequest)

Select Instagram account

Selects an Instagram account destination and attaches it to a profile.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **selectInstagramAccountRequest** | [**SelectInstagramAccountRequest**](SelectInstagramAccountRequest.md) |  |  |

### Return type

[**CompleteConnect200Response**](CompleteConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Instagram account selected. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account or Instagram account not found. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Instagram account selection failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="selectlinkedinorganization"></a>
# **SelectLinkedInOrganization**
> CompleteConnect200Response SelectLinkedInOrganization (SelectLinkedInOrganizationRequest selectLinkedInOrganizationRequest)

Select LinkedIn organization

Selects a LinkedIn organization destination and attaches it to a profile.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **selectLinkedInOrganizationRequest** | [**SelectLinkedInOrganizationRequest**](SelectLinkedInOrganizationRequest.md) |  |  |

### Return type

[**CompleteConnect200Response**](CompleteConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | LinkedIn organization selected. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account or organization not found. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | LinkedIn organization selection failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="selectpinterestboard"></a>
# **SelectPinterestBoard**
> CompleteConnect200Response SelectPinterestBoard (SelectPinterestBoardRequest selectPinterestBoardRequest)

Select Pinterest board

Selects a Pinterest board destination and attaches it to a profile.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **selectPinterestBoardRequest** | [**SelectPinterestBoardRequest**](SelectPinterestBoardRequest.md) |  |  |

### Return type

[**CompleteConnect200Response**](CompleteConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Pinterest board selected. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account or board not found. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | Pinterest board selection failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="selectyoutubechannel"></a>
# **SelectYouTubeChannel**
> CompleteConnect200Response SelectYouTubeChannel (SelectYouTubeChannelRequest selectYouTubeChannelRequest)

Select YouTube channel

Selects a YouTube channel destination and attaches it to a profile.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **selectYouTubeChannelRequest** | [**SelectYouTubeChannelRequest**](SelectYouTubeChannelRequest.md) |  |  |

### Return type

[**CompleteConnect200Response**](CompleteConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | YouTube channel selected. |  -  |
| **401** | Authentication failed. |  -  |
| **404** | Connected account or channel not found. |  -  |
| **422** | Request body validation failed. |  -  |
| **500** | YouTube channel selection failed. |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

