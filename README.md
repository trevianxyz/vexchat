# Doc-Web AI Chat 💬🌐


Doc-Web AI Chat is the ultimate app powered by LangChain, OpenAI, and Streamlit that allows you to unlock the power of knowledge by effortlessly interacting with your PDFs. With Doc-Web AI Chat, you can seamlessly navigate through your PDF documents, ask questions directly, and augment your search with SERPAPI to gather additional information from the web. Get ready to get accurate and relevant answers to your burning questions in one convenient place.

## Features 📚🔎

Doc-Web AI Chat offers the following key features:

- **Interact:** Seamlessly navigate through your PDF documents and ask questions directly.
- **Augmented Search:** Access an extensive web search using SERPAPI to gather additional information.
- **Get Answers:** Leverage advanced AI algorithms to provide accurate and relevant answers to your queries.

## Installation

To run Doc-Web AI Chat, follow these steps:

1. Clone this repository to your local machine.
2. Navigate to the project directory.

```bash
git clone https://github.com/your-username/doc-web-ai-chat.git
cd doc-web-ai-chat
```
3. Install the required packages using `pip` with the provided `requirements.txt` file.
```bash
pip install -r requirements.txt
```
## Usage

To start Doc-Web AI Chat, run the following command:
```bash
streamlit run ai_chat.py
```
This command will launch the Doc-Web AI Chat app in your default web browser. You can then start interacting with your PDFs, asking questions, and accessing augmented search capabilities.

<img src="Doc-Web-ai.PNG" alt="Doc-Web AI App Homepage">

## Feedback and Contributions
If you have any feedback, suggestions, or issues related to Doc-Web AI Chat, please open an issue on the GitHub repository. Contributions are also welcome! If you would like to contribute to Doc-Web AI Chat, please follow the guidelines outlined in the Contribution Guidelines.

## License
Doc-Web AI Chat is licensed under the MIT License.

---

<p><em>Doc-Web AI Chat is a project powered by <strong>LangChain</strong>, <strong>OpenAI</strong>, and <strong>Streamlit</strong>.</em></p>

```def handle_upload():
        """
        Handles the file upload and displays the uploaded file
        """
        uploaded_file = st.sidebar.file_uploader("upload", type=["pdf"], label_visibility="collapsed", accept_multiple_files = True)
        if uploaded_file is not None:

            def show_pdf_file(uploaded_file):
                file_container = st.expander("Your PDF file :")
                for i in range(len(uploaded_file)):
                    with pdfplumber.open(uploaded_file[i]) as pdf:
                        pdf_text = ""
                        for page in pdf.pages:
                            pdf_text += page.extract_text() + "\n\n"
                    file_container.write(pdf_text)
            
            file_extension = ".pdf"

            if file_extension== ".pdf" :
                show_pdf_file(uploaded_file)

        else:
            st.sidebar.info(
                "👆 Upload your PDF file to get started..!"
            )
            st.session_state["reset_chat"] = True

        #print(uploaded_file)
        return uploaded_file


                file.getvalue().decode('utf-8').splitlines()