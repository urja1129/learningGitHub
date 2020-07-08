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
## Corpus950
Corpus950 is the collection of 950 research paper and relevant documents that were downloaded and stored in the system using `getpapers`. The following command was executed :

`getpapers -q "viral epidemics" -o dir_corpus950 -x -p -k 1000`

The command `getpapers` initiate the process and `-q` refers to the query which is to be searched. The query is entered in inverted commas as is done in `"viral epidemic"`. The next element is `-o` which refers to output directory and the parameter that follows it in the name of the directory which is `dir_corpus950` in our case. Then, `-x -p` corresponds to xml and pdf files to be included in our search and `-k 1000` limits our search to 1,000 files only. After successful completion of the command we get our Corpus-950 ready.

Sectioning of downloaded files will create a tree structure for us which will help in exploring the content of the file. Sectioning done using `section` function of `ami`.
The command executed will be :
`ami -p dir_corpus950 section`


## Dictionary
After all the files are downloaded and succesfully stored in our `dir_corpus950` directory, our next task is to generate a dictionary using `ami` tools. We will use the follwing command:

`ami -p dir_corpus950 search --dictionary drugs`

`ami` will initiate the ami function and `-p` will set the path to `dir_corpus950`. Then `search --dictionary drugs` will search drugs from the dictionary and create an html file consisting of the data in a tabular form.

## Goals
