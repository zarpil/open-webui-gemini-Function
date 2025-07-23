Gemini API Pipe for Open WebUI UPDATED 07/22/2025
A comprehensive integration pipe that connects Open WebUI with Google's Gemini API, providing access to all Gemini models including the latest Gemini 2.5 series with advanced capabilities.
Features

Complete Model Support: Access to all Gemini models including Gemini 2.5 Flash Preview, Gemini 2.5 Pro Preview, Gemini 2.0 Flash, and Gemini 1.5 series
Multimodal Capabilities: Support for text and image processing across all compatible models
Streaming Support: Real-time response streaming with automatic fallback to non-streaming mode
Vision Processing: Handle base64 encoded images and image URLs
System Message Integration: Proper handling of system instructions
Debug Mode: Comprehensive logging for troubleshooting
Error Handling: Robust error management with user-friendly feedback

Installation

Download the Pipe: Save the provided Python code as gemini_pipe.py
Install in Open WebUI:

Navigate to your Open WebUI admin panel
Go to Settings → Pipelines
Click Add Pipeline
Upload the gemini_pipe.py file

Configure API Key:

After installation, go to pipeline settings
Set your GEMINI_API_KEY (replace "Your API Key Here")

Configuration
Required Settings

GEMINI_API_KEY: Your Google AI Studio API key

Get your API key from Google AI Studio
Replace the default "Your API Key Here" value

Optional Settings

DEBUG: Enable/disable debug logging (default: True)
FORCE_NON_STREAMING: Force non-streaming mode (default: False)

Getting Your API Key

Visit Google AI Studio
Sign in with your Google account
Click "Create API Key"
Copy the generated key
Paste it into the GEMINI_API_KEY field in the pipeline settings

Usage
Basic Text Chat
Once installed and configured, simply:

Select a Gemini model from the model dropdown
Start chatting normally
The pipe handles all API communication transparently

Multimodal (Text + Images)
The pipe automatically handles:

Base64 Images: Directly embedded in chat
Image URLs: Converted to appropriate format
Mixed Content: Text and images in the same message

System Instructions
System messages are automatically converted to Gemini's format and prepended to conversations.
Features in Detail
Streaming Support

Real-time Responses: Get responses as they're generated
Automatic Fallback: If streaming fails, automatically switches to non-streaming
Configurable: Can be disabled via FORCE_NON_STREAMING setting

Error Handling

API Key Validation: Checks for missing or default API keys
HTTP Error Handling: Proper error messages for API failures
Graceful Degradation: Fallback mechanisms for various failure scenarios

Debug Mode
When enabled, provides detailed logging:

Request/response data
Model name transformations
Streaming vs non-streaming decisions
Error details and stack traces

Troubleshooting
Common Issues

"GEMINI_API_KEY is required" Error

Ensure you've set your API key in the pipeline settings
Verify the key is not the default "Your API Key Here"

HTTP 400 Errors

Check that your API key is valid and active
Verify the model name is supported

HTTP 429 Errors

You've exceeded API rate limits
Wait and retry, or upgrade your Google AI Studio quota

Streaming Issues

Enable debug mode to see detailed logs
Try setting FORCE_NON_STREAMING to True

Debug Mode
Enable debug mode in settings to see:
[GEMINI] Original model: gemini-2.5-flash-preview-04-17
[GEMINI] Clean model: gemini-2.5-flash-preview-04-17
[GEMINI] URL: https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-04-17:generateContent?key=***
[GEMINI] Stream requested: True
[GEMINI] Using streaming: True
API Endpoints Used

Non-streaming: https://generativelanguage.googleapis.com/v1beta/models/{model}:generateContent
Streaming: https://generativelanguage.googleapis.com/v1beta/models/{model}:streamGenerateContent

Requirements

Open WebUI: Compatible with Open WebUI pipeline system
Python Dependencies:

aiohttp: For async HTTP requests
pydantic: For configuration validation
json: For data serialization
logging: For debug output

Contributing
This pipe is designed to be:

Extensible: Easy to add new models or features
Maintainable: Clear code structure and documentation
Robust: Comprehensive error handling and fallbacks

License
This code is provided as-is for integration with Open WebUI and Google's Gemini API. Please ensure compliance with Google's API terms of service and Open WebUI's licensing requirements.
Support
For issues:

Enable debug mode and check logs
Verify API key and model availability
Check Google AI Studio status and quotas
Consult Open WebUI documentation for pipeline issues

https://openwebui.com/f/p0us/gemini_ai_studio_

Note: This pipe requires an active Google AI Studio API key. Some models may have usage restrictions or require special access.
