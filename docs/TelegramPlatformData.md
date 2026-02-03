# Late.Model.TelegramPlatformData
Telegram channel/group posting settings: - Supports text, images (up to 10), videos (up to 10), and mixed media albums - Posts to channels display the channel name and logo as author - Posts to groups display the bot name (Late) as author - Message IDs are returned for analytics tracking - Captions support up to 1024 characters for media posts, 4096 for text-only  **Analytics:** - **Not available via API.** The Telegram Bot API does not expose message analytics (views, forwards, reactions). - View counts are only visible to channel admins directly in the Telegram app. - This is a Telegram platform limitation that affects all third-party tools. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ParseMode** | **string** | Text formatting mode for the message (default is HTML) | [optional] 
**DisableWebPagePreview** | **bool** | Disable link preview generation for URLs in the message | [optional] 
**DisableNotification** | **bool** | Send the message silently (users will receive notification without sound) | [optional] 
**ProtectContent** | **bool** | Protect message content from forwarding and saving | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

