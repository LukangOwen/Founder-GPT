# Founder-GPT

## Abstract
In assisting Vela Partners, the "Founder-GPT" project is an innovative venture capital initiative leveraging artificial intelligence to assess startup founders. Utilizing Large Language Models like GPT-4, the project aims to systematically evaluate founders' profiles, providing quantitative scores and qualitative pros and cons lists. The methodology encompasses several stages, starting with the extraction of similar founder profiles using a combination of embeddings generated from key profile dimensions and similarity measures. The subsequent phase involves leveraging GPT-4 to generate detailed rationales behind the success or failure of these profiles. This analysis forms the basis for a scoring system that quantifies the potential success of new founder profiles, along with generating insightful pros and cons lists. The results from the "Founder-GPT" project highlighted its strength in accurately identifying founders with high success potential, reflected in high scoring profiles. The system also successfully generated comprehensive pros and cons lists that provided nuanced insights into the founder profiles. However, our project faces challenges like a high false positive rate and significant computational demands. The project highlights the need for future enhancements, including refining false positive mitigation, computational efficiency, and the integration of broader data sources and advanced analytical methods. This work sets a foundation for AI-enhanced decision-making in venture capital, pointing towards areas for further development to fully realize AI's potential in founder evaluation.

Please read the paper `"Founder_GPT_Lukang Guo.pdf"` for the details of the methodology and results of this project.

## Execution of Programme

### Phase 1: Data Preparation – Founder Feature Engineering
Due to the limited size of files allowed in github, the extracted founder data and their embeddings have to be conducted manually first before the main execution of the algorithm.

1. Firstly, prepare your raw data in the folder `founder-data`, ensuring the following files exist:

`successProfilePath = 'founder-data/success_enriched_linkedin_profiles.csv'`
`sucessCompanyPath = 'founder-data/Moneyball 1.1_ Success.xlsx'`

`failProfilePath = 'founder-data/fail_enriched_linkedin_profiles.csv'`
`failCompanyPath = 'founder-data/Moneyball 1.1_ Fail.xlsx'`

Note that you will need to manually download the files for enriched_linkedin_profiles into the folder which are larger than github's limit.

2. Then, run all the cell blocks in the file `Founder Feature Engineering.ipynb` to create founder data.
The programme will first read all the founder's profiles in the dataset into individual json files stored in the following directories:

`successDataDirectory = 'founder-data/successful-founders'`

`failDataDirectory = 'founder-data/failed-founders'`

Then, the programme would read from the json files and export all processed founder data into the file `'Founder Features.csv'`. This file should be the key file that subsequent main execution of the programme should read from.

3. If you wish to use pre-determined embeddings for founder-details, you can open the file `"Similarity Comparison.ipynb"` and run the code up to the section where you split the embedding data into two files:

`output_file1 = 'Founder Features with Embeddings_Training.csv'`
`output_file2 = 'Founder Features with Embeddings_Testing.csv'`

This is, however, a lengthy process. Alternatively, you can ask the author to provide you with the files for the embeddings of founder details directly.


### Phase 2: Main Execution
The execution of the programme mainly takes place in the file \textit{'Main Programme.ipynb'}. Make sure you run all the function blocks in the Preliminary sections, and replace the openAI API\_KEYS with your own API keys (the original ones in the codes have been disabled). Then, execute one-by-one, the blocks in each of the 'Main Programme Execution' section. Some blocks may take longer to respond, as the computational time is high in some parts (particularly, the extraction of top similar founder profiles, and querying GPT-4).

Currently, all input are assumed to be taken from the testing set of our data (see the file 'Founder Features with Embeddings\_Testing.csv'). Feel free to alter the code to accept input in your own favourable ways. Also, feel free to update any methods more efficient – such as, replacing the aggregate similarity comparison in section 3.2 with Pinecone vector database.
