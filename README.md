# plainify
Take complex PDF documents and turn them into easy to understand markdown

# Medical PDF Simplifier

A Python tool that converts technical PDFs into simplified Markdown documents with lay explanations of complex terms. The tool uses OpenAI's GPT API to provide clear, accessible explanations of medical content.

## Features

- Converts PDF documents to Markdown format
- Preserves document structure and formatting
- Splits large documents into manageable chunks
- Processes text using GPT-3.5-turbo to create simplified explanations
- Provides parenthetical definitions for medical terms
- Handles concurrent API requests efficiently
- Comprehensive logging system

## Prerequisites

- Python 3.8 or higher
- OpenAI API key
- Tesseract OCR (optional, for PDFs with scanned text)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/jmcdice/plainify
cd plainify
```

2. Create and activate a virtual environment (recommended):
```bash
python -m venv .venv
source .venv/bin/activate
```

3. Install the required packages:
```bash
pip install -r requirements.txt
```

4. Set up your OpenAI API key:
Create a `.env` file in the project root and add your OpenAI API key:
```
export OPENAI_API_KEY=your_api_key_here
```

## Usage

Run the script from the command line:

```bash
mdkir outputs
./plainify complex_paper.pdf outputs/simplified_output.md
```

This will create two files:
- `simplified_output_original.md`: The direct PDF-to-Markdown conversion
- `simplified_output.md`: The simplified version with explanations

### Example

```bash
./plainify complex_paper.pdf outputs/simplified_paper.md
```

## How It Works

1. **PDF Conversion**: The tool first converts the PDF to Markdown format using the `docling` library, preserving the document's structure.

2. **Text Processing**: The Markdown content is split into manageable chunks while preserving sentence boundaries.

3. **AI Processing**: Each chunk is processed through OpenAI's GPT-3.5-turbo model, which:
   - Simplifies complex medical terminology
   - Adds parenthetical explanations for technical terms
   - Makes the content more accessible to non-medical readers

4. **Result Compilation**: The simplified chunks are combined into a final Markdown document.

## Error Handling

The tool includes comprehensive error handling and logging:
- Input file validation
- API error handling
- Conversion process monitoring
- Detailed error messages and logging

## Limitations

- Requires an active OpenAI API key and internet connection
- Processing time depends on document length and API response time
- API costs may apply based on document length
- Maximum chunk size of 7000 characters (configurable)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

For issues, questions, or contributions, please open an issue in the GitHub repo.
