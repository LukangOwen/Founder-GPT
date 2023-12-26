# Founder-GPT
In assisting Vela Partners, the "Founder-GPT" project is an innovative venture capital initiative leveraging artificial intelligence to assess startup founders. Utilizing Large Language Models like GPT-4, the project aims to systematically evaluate founders' profiles, providing quantitative scores and qualitative pros and cons lists.

Please read the paper `"Founder_GPT_Lukang Guo.pdf"` for the details of the methodology and results of this project.

## Execution of Programme

### Phase 1: Founder Feature Engineering
Due to the limited size of files allowed in github, the extracted founder data and their embeddings
The execution of the programme mainly takes place in the file \textit{'Main Programme.ipynb'}. Make sure you run all the function blocks in the Preliminary sections, and replace the openAI API\_KEYS with your own API keys (the original ones in the codes have been disabled). Then, execute one-by-one, the blocks in each of the 'Main Programme Execution' section. Some blocks may take longer to respond, as the computational time is high in some parts (particularly, the extraction of top similar founder profiles, and querying GPT-4).

Currently, all input are assumed to be taken from the testing set of our data (see the file 'Founder Features with Embeddings\_Testing.csv'). Feel free to alter the code to accept input in your own favourable ways. Also, feel free to update any methods more efficient – such as, replacing the aggregate similarity comparison in section 3.2 with Pinecone vector database.
