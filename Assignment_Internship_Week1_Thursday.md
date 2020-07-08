# Why this Mini-project?
A viral epidemic poses a threat to human life and the last resort to tackle it, on which the entire human race rely on, is the availablity of **drugs**. With varieities of drugs available to us, for example *anti-viral drugs, palliative drugs, antibacterial drugs and so on*, it has become difficult to track the role of the drug. While some drugs are proving to be effective antiviral there are drugs that only cure the symptoms. Hence, this miniproject provides the necessary tools that would provide complete information at one one place to the public.
## Objectives:
- [ ] *To create a dictionary consisting of drugs for viral diseases and its local name in different countries.*
- [ ] *Differentiate drugs that work directly against the virus and the drugs that only work on symptoms.*

## Tools :
- `getpapers` to obtain research papers.
- use of `nodejs`, `nvm`, `cmd`
- `ami` for dictionaries and sectioning.
- `ami`/`SPARQL` for the creation of dictionaries.
- `Python`, `R` related software for data analysis.

# Corpus950
This comprises of top 950 articles retrieved from EuroPMC which is a platform that provides free acces to million of articles related to biomedical science. getpapers will be used to search and download these articles. The processing of the software is very quick (approx 10 minutes) which  which when downloaded individually could have taken 'n' number of hours. In this project such articles will be downloaded to study drugs related to viral epidemics.

The other advantage of this project is we dont have to go through all the papers to understand the gist instead with the help of `ami : section` the papers are tabulated/sectioned  and one can go through all without reading them all and select the ones that is of interest. 
## Course of Action
For this purpose, the following command will be executed :

`getpapers -q "viral epidemics and drugs" -o dir_corpus950 -x -p -k 1000`

The command `getpapers` will initiate the process and `-q` refers to the query which is to be searched. The query is entered in inverted commas as is done in `"viral epidemics and drugs"`. The next element is `-o` which refers to output directory and the parameter that follows it in the name of the directory which is `dir_corpus950` in our case. Then, `-x -p` corresponds to xml and pdf files to be included in our search and `-k 1000` limits our search to 1,000 files only. After successful completion of the command we get our Corpus-950 ready.

Sectioning of downloaded files will create a tree structure for us which will help in exploring the content of the file. Sectioning done using `section` function of `ami`.
The command executed will be :
`ami -p dir_corpus950 section`


# Drugs Dictionary
Wikidata is an open-source database containing information stored semantically. Thus, applications of softwares could help us relate various properties of similar drugs and use it constructively. So, we will be creating a `dictionary` with an attempt to simplify the downloaded 950 articles and relate drugs with its usage. This would require application of 'machine learning' to achieve the same.

## Course of Action
When all the files are downloaded and succesfully stored in our `dir_corpus950` directory, our next task is to generate the dictionary using `ami` tools. We will use the follwing command:

`ami -p dir_corpus950 search --dictionary drugs`

`ami` will initiate the ami function and `-p` will set the path to `dir_corpus950`. Then `search --dictionary drugs` will search drugs from the dictionary and create an html file consisting of the data in a tabular form.

# Goals
1. To differentiate false positive and true positive, i.e to find papers that are related to "viral epidemic and drugs" and remove unnecessary ones.
2. To find relationship between drugs, this may help in suggesting alternative drug for an epidemic.
3. To segregate drugs that take action against the virus and the drugs that suppresses only the symptoms.
4. Maintain a simplified drug dictionary that would be open to public.
