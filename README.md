# PDF Accessibility with OpenAI

A docker image that automatically fixes accessibility issues in PDF files using PDFix SDK and OpenAI.

## Table of Contents

- [PDF Accessibility with OpenAI](#pdf-accessibility-with-openai)
  - [Table of Contents](#table-of-contents)
  - [Available Actions](#available-actions)
  - [Getting Started](#getting-started)
  - [Run using Command Line Interface](#run-using-command-line-interface)
  - [Run Description Generation using REST API](#run-description-generation-using-rest-api)
    - [Export the Configuration File for Integration](#export-the-configuration-file-for-integration)
  - [License \& libraries used](#license--libraries-used)
  - [Help \& Support](#help--support)
  
## Available Actions
- Generate Alternate Text for images
- Generate Table Summary

```
PDF Accessibility with OpenAI

commands:
  {config,generate-alt-text,generate-table-summary}
    config                  Save the default configuration file
    generate-alt-text       Generate alternate text for images
    generate-table-summary  Generate Table Summary

options:
  -h, --help                show this help message and exit
  --openai-key OPENAI_KEY   OpenAI API key
  --input INPUT             The input PDF file
  --output OUTPUT           The output file
  --tags TAGS               Regular expression defining the tag names tpo process
  --overwrite OVERWRITE     Overwrite the existing value
  --lang LANG               The laguage of the alternate description and table summary
  --name NAME               PDFix license name
  --key KEY                 PDFix license key
```

## Getting Started

To use this Docker application, you'll need to have Docker installed on your system. If Docker is not installed, please follow the instructions on the [official Docker website](https://docs.docker.com/get-docker/) to install it.

## Run using Command Line Interface

To run the docker container as CLI, you should share the folder containing the PDF for processing using the `-i` parameter. In this example, the current folder is used.

```bash 
docker run -v $(pwd):/data/ -w /data pdfix/pdf-accessibility-openai:latest generate-alt-text --input document.pdf --output out.pdf --tags "Figure|Formula" --openai_key <api_key> --lang English --overwrite true
```

To run With a PDFix License add these arguments.
```bash
--name ${LICENSE_NAME} --key ${LICENSE_KEY}
```
Contact support for more infomation.

First run will pull the docker image, which may take some time. Make your own image for more advanced use.

For more detailed information about the available command-line arguments, you can run the following command:

```bash
docker run --rm pdfix/pdf-accessibility-openai:latest --help
```

## Run Description Generation using REST API
Comming soon. Please contact us.

### Export the Configuration File for Integration
To export the configuration JSON file, use the following command:
```bash
docker run -v $(pwd):/data -w /data --rm pdfix/pdf-accessibility-openai:latest config --output config.json
```

## License & libraries used
- PDFix SDK - https://pdfix.net/terms
- OpenAI API - https://openai.com/policies/

Trial version of the PDFix SDK may apply a watermark on the page and redact random parts of the PDF including the scanned image in background. Contact us to get an evaluation or production license.

## Help & Support
To obtain a PDFix SDK license or report an issue please contact us at support@pdfix.net.
For more information visit https://pdfix.net


