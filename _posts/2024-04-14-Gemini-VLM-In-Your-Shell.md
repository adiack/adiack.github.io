---
layout: post
title:  "🤖 VLM in your shell"
---


## Empower Your Shell with AI: Describe Images with a Custom Command and Gemini

Explore Google's Gemini 1.5 vision REST API via an alias bash command. We'll craft a custom command called "desc" or "openai_desc" that leverages the API to describe images directly from your terminal.
 

**Getting Started:**

1. **API Key:**
    - Head over to the Google Cloud Console and create a project if you haven't already.
    - https://aistudio.google.com/app/apikey
    - Enable the "Generative Language API" for your project.
    - Create an API key and make a note of it.
    - (same procedure applies for ChatGPT API, see https://platform.openai.com/docs/guides/vision 

2. **.bashrc :**
    - Open your terminal and edit your .bashrc file using a text editor: `vi ~/.bashrc`
    - Add the following lines, replacing "YOUR_API_KEY" with your actual API key

```html
export GOOGLE_API_KEY="YOUR_API_KEY"
export OPENAI_API_KEY="YOUR_API_KEY"

desc() {
  # Check if the filename is provided and the file exists
  if [ -z "$1" ]; then
    echo "Usage: desc <filename>"
    return 1
  elif [ ! -f "$1" ]; then
    echo "File does not exist: $1"
    return 1
  fi

  # Determine the MIME type based on file extension
  local mime_type
  case "$1" in
    *.png) mime_type="image/png" ;;
    *.jpg|*.jpeg) mime_type="image/jpeg" ;;
    *.webp) mime_type="image/webp" ;;
    *.heic) mime_type="image/heic" ;;
    *.heif) mime_type="image/heif" ;;
    *)
      echo "Unsupported image format: $1"
      return 1
      ;;
  esac

  # Encode the image file to base64
  local IMG_BASE64=$(base64 -i "$1")

  # Generate the JSON payload with the correct MIME type
  local JSON_PAYLOAD="{\"contents\":[{\"parts\":[{\"text\":\"What is this picture?\"},{\"inline_data\":{\"mime_type\":\"${mime_type}\",\"data\":\"${IMG_BASE64}\"}}]}]}"

  # Send the request to the Gemini API and extract the description
  local gemini_response=$(echo "${JSON_PAYLOAD}" | curl -s https://generativelanguage.googleapis.com/v1beta/models/gemini-pro-vision:generateContent?key=${GOOGLE_API_KEY} \
    -H 'Content-Type: application/json' -d @- | grep '"text"' | sed 's/.*: "\(.*\)".*/\1/' )

  tput bold; echo "Gemini Image Description:"
  tput sgr0; fmt -w 70 <<< "$gemini_response"
}

openai_desc() {
  # Check if filename is provided and the file exists
  if [ -z "$1" ]; then
    echo "Usage: openai_desc <filename>"
    return 1
  elif [ ! -f "$1" ]; then
    echo "File does not exist: $1"
    return 1
  fi

  # Encode the image file to base64
  local img_base64=$(base64 -i "$1")

  # Construct the JSON payload for OpenAI API
  local json_payload='{"model": "gpt-4-turbo", "messages": [{"role": "user", "content": [{"type": "text", "text": "What’s in this image?"}, {"type": "image", "image": {"base64": "'"$img_base64"'"}}]}]}'

  # Send the request to OpenAI API and extract the description
  local openai_response=$(curl -s https://api.openai.com/v1/chat/completions \
    -H "Content-Type: application/json" \
    -H "Authorization: Bearer $OPENAI_API_KEY" \
    -d "$json_payload" )

  tput bold; echo "OpenAI Image Description:"
  tput sgr0; fmt -w 70 <<< "$openai_response"
}
```

- Save and close the file. Then, reload your .bashrc: `source ~/.bashrc`

**Using the "desc" Command:**

1. Navigate to the directory containing your image.
2. Simply type `desc image_filename.jpg`.
Images must be in one of the following image data MIME types:
PNG - image/png
JPEG - image/jpeg
WEBP - image/webp
HEIC - image/heic
HEIF - image/heif

4. The script will call the Gemini API, analyze the image, and return a description.

Sample usage:
```html
bash-3.2$ desc GAfQK1-WAAARklx.jpeg 
Gemini Image Description:
 A red-winged blackbird sings on a branch in the morning sun. The
 bird's breath is visible as a small cloud of white vapor.
```

**Understanding the Script:**

* The script checks for filename input and file existence.
* It determines the image format based on the file extension.
* The image is encoded into base64 format.
* A JSON payload is generated, including the image data and a prompt ("What is this picture?").
* The payload is sent to the Gemini API using `curl`.
* The response is parsed to extract the image description.
* The description is displayed in your terminal. 

**Some ideas:**

* **Modify the prompt:**  Instead of "What is this picture?", you could ask specific questions like "What is the main object in this image?" or "Describe the emotions of the people in this picture."
* **Integrate with other tools:**  Pipe the description to a text-to-speech engine for audio output, or use it as input for other scripts or applications.
* **Explore advanced API options:** The Gemini API offers various parameters to fine-tune the responses, such as specifying the response length or creativity level. 

**More info here:**
Quickstart: Get started with Gemini using the REST API
https://ai.google.dev/tutorials/rest_quickstart

