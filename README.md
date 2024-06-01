# danish-parlimentary-debates
This is a collection of speech segments extracted from a corpus of 1704 Parliamentary Debates from the Danish Parliamentary Chamers (Folketingssalen). The data is intended for NLP-analyses such as topic modeling or sentiment analysis. 

**Data Acquisition** 
Parliament transcripts are freely accessible from the Danish Parliament's website (Referater, 2016), and were downloaded along with information about members of parliament, also accessible through the website (Oda.ft.dk, 2024). Transcripts contain meeting agendas, voting outcomes and importantly for the current purposes; text records of everything uttered in Folketingssalen (parliament chambers). 
Records range back to 19th of April 2005 and are continuously being updated. A change in document formatting after the 3rd of October 2007 led to data before this time to be left out for analysis. Furthermore, for the simplicity of the analysis data from incomplete years (2007 and 2024) were also omitted, resulting in the current analysis concerning data from January 2008 to December 2023. In this time frame 1704 transcripts were recorded. 


Concerning information about members of parliament, the collected metrics were; full name, age, gender, and latest party. A total of 462 current and former members of parliament's spoke in the collected transcripts. 

**Data Preprocessing {FRFL}**
The transcripts were split into segments by speaker, such that every time a new speaker spoke this would be saved as a document. This document extraction was done in Python (Van Rossum & Drake, 2009) using BeautifulSoup (Richardson, 2007). Further preprocessing consisted of the following steps: (1) extracting the speakers name for each document, (2) removing documents from the Speaker of Folktinget, as their job consist of mediation of the debates, and as such almost exclusively consisted of short parliamentary procedure formalities, (3) removing one word parliament procedure formalities, greatly decreasing the number of documents. No further preprocessing of documents was performed, as the analysis were to utilize transformer models, which leverage both lexical and non lexical linguistic information. This process resulted in a corpus of 499.390 documents of statements from Danish politicians which were to be analyzed. 

