# Advanced YouTube Video Summarizer

This application provides an advanced summarization tool for YouTube videos, leveraging the power of Cohere's language model and the YouTube Transcript API. Users can input a video link, retrieve the transcript, generate a detailed summary, and ask questions about the video's content.

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Environment Variables](#environment-variables)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Transcript Retrieval**: Automatically fetches transcripts from YouTube videos, supporting both manually created and auto-generated transcripts.
- **Detailed Summarization**: Generates comprehensive summaries that include key points, subtopics, and conclusions.
- **Interactive Q&A**: Users can ask questions based on the video content, and the application provides detailed answers.
- **User-Friendly Interface**: Built with Streamlit, the application offers an intuitive interface for easy interaction.

## Requirements

To run this application, you need:

- Python 3.7 or higher
- The following Python libraries:
  - `cohere`
  - `streamlit`
  - `youtube-transcript-api`
  - `langchain`
  - `python-dotenv`

## Installation

Follow these steps to set up the project on your local machine:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/youtube-video-summarizer.git
   cd youtube-video-summarizer
   ```

2. **Install the required libraries**:
   Make sure you have `pip` installed, then run:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables**:
   Create a `.env` file in the root directory of the project and add your Cohere API key:
   ```
   COHERE_API_KEY=your_api_key_here
   ```

## Usage

1. **Run the Streamlit app**:
   Start the application by executing:
   ```bash
   streamlit run app.py
   ```

2. **Access the application**:
   Open your web browser and navigate to `http://localhost:8501` to access the application interface.

3. **Enter YouTube Video Link**:
   Input the link of the YouTube video you want to summarize in the provided text box.

4. **Generate Summary**:
   Click the "Start" button. The application will fetch the transcript, create a detailed summary, and display it on the screen.

5. **Ask Questions**:
   After the summary appears, you can ask questions related to the video content. Input your question and click "Get Answer" to receive a detailed response.

## How It Works

1. **Transcript Retrieval**:
   - The application uses the `YouTubeTranscriptApi` to extract transcripts.
   - It first attempts to retrieve a manually created transcript. If none is available, it fetches an auto-generated transcript in a supported language.

2. **Text Processing**:
   - The retrieved transcript is processed using `langchain`'s `RecursiveCharacterTextSplitter`, which breaks the text into manageable chunks for summarization.

3. **Summarization**:
   - A detailed summary is generated using Cohere's language model. The summary includes an introduction, key points, and a conclusion, providing a comprehensive overview of the video's content.

4. **Question Answering**:
   - Users can input questions related to the video. The application generates answers based on the transcript or summary using the Cohere model.

## Environment Variables

To ensure the application runs smoothly, set the following environment variable in your `.env` file:

- `COHERE_API_KEY`: Your personal Cohere API key for accessing the summarization and language models.

## Contributing

We welcome contributions from the community! If you have suggestions for new features or improvements, please fork the repository and submit a pull request. Here are a few ways you can contribute:

- **Bug Reports**: If you find a bug, please open an issue on GitHub with details on how to reproduce it.
- **Feature Requests**: If you have an idea for a new feature, please describe it in an issue.
- **Code Contributions**: If you would like to contribute code, please create a separate branch for your feature or fix and submit a pull request.

## License

This project is licensed under the MIT License. For more details, see the [LICENSE](LICENSE) file in the repository.

---

For any questions or support, feel free to open an issue on GitHub or contact the repository maintainer. We hope you enjoy using the Advanced YouTube Video Summarizer! Happy summarizing!
