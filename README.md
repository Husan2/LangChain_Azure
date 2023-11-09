# LangChain_Azure
LangChain on Microsoft Azure

## 環境
conda create --name LangChain_Azure python=3.10.6

1. **Azure Container Registry**: To manage the Docker images.
2. **App Services**: Where the application will be hosted.
3. **Blob Storage**: For storing unstructured data.
4. **Azure Cognitive Search**: Powers the application's Q&A functionality.
5. **OpenAI API Key**: For generating natural language model responses.

### `blob.py`

自動執行將資料從本機「Data」目錄上傳至 Azure Blob storage 
初始化 Blob service
在指定目錄中發現的每個檔案上傳到 Container。

### `azurecognitive_search.py`

建立 vector embeddings 並載入到 Azure 認知搜尋(Azure Cognitive Search)。
使用 OpenAI API 進行 embedding generation
embeddings 建立後，儲存在 Azure Search index，以便隨時可用於快速且有效率的搜尋。


### `application.py`

 and an appropriate answer is retrieved or generated. Past interactions can be reviewed in the session.
使用 Streamlit 作為對話 UI 
在 OpenAI's model 與 Azure Cognitive Search 處理使用者輸入的問題(input)
產生 / 檢索(retrieved) 合適的 answer