<img src="https://github.com/prateekguptaiiitk/Resume_Classifier/blob/develop/SkyBits-logo-small.png" align="left" hspace="1" vspace="1" height="100" width="268">

# Resume Filtering Using Machine Learning

<p> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Resume filtering on the basis of Job Descriptions(JDs). It was a summer &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; internship project with <a href="http://sky-bits.com/">Skybits Technologies Pvt. Ltd.</a></p>

![Language](https://img.shields.io/badge/Language-Python3-blue.svg) [![GitHub License](https://img.shields.io/github/license/prateekguptaiiitk/Resume_Filtering.svg)](https://github.com/prateekguptaiiitk/Resume_Filtering/blob/develop/LICENSE) [![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fprateekguptaiiitk%2FResume_Filtering&count_bg=%23D1C941&title_bg=%23555555&icon=homebrew.svg&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com) [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/prateekguptaiiitk/Resume_Filtering/develop)

## Introduction

The main feature of the current project is that it searches the entire `resume` database to select and display the resumes which fit the best for the provided `job description(JD)`. This is, in its current form, achieved by assigning a score to each CV by intelligently comparing them against the corresponding Job Description. This reduces the window to a fraction of an original size of applicants. Resumes in the final window can be manually checked for further analysis. The project uses techniques in `Machine Learning` and `Natural Language Processing` to automate the process.

## Directory Structure

<pre>
.
├── Data
│   ├── CVs
│   ├── collectCV.py
│   └── jd.csv
├── Model
│   ├── Model_Training.ipynb
│   ├── Sentence_Extraction.ipynb
│   ├── paragraph_extraction_from_posts.ipynb
│   ├── sample_bitcoin.stackexchange_paras.txt
│   ├── sample_bitcoin.stackexchange_sentences.txt
├── Scoring
│   ├── CV_ranking.ipynb
│   ├── Using Spacy Model.ipynb
│   ├── With Word2Vec.ipynb
│   ├── context.jpg
│   └── prc_data.csv
└── Section Extraction
    ├── Section_Extraction.ipynb
    ├── convertDocxToText.py
    ├── convertPDFToText.py
    ├── extract.py
    └── get_jd.ipynb
    
</pre>

## Directory Details

## [Data](https://github.com/prateekguptaiiitk/Resume_Classifier/tree/develop/Data)

- **CVs :** Contains 250 extracted resumes in text format from [indeed.com](https://www.indeed.com)
- **collectCV.py :** Python script to automate the process of extracting CVs from indeed.com. While this program is running, every new text copied to clipboard is saved as a CV in **CVs/** directory in text format.
- **jd.csv :** CSV file containing cleaned job descriptions from Kaggle. Dataset can be found [here](https://www.kaggle.com/c/job-salary-prediction/data)

## [Model](https://github.com/prateekguptaiiitk/Resume_Classifier/tree/develop/Model)

- **Model_Training.ipynb :** Notebook to train the word2vec model using gensim. The model was saved in ```./model/``` subdirectory (locally). 
- **Sentence_Extraction.ipynb :** Notebook for extracting cleaned sentences from extracted paragraphs.
- **paragraph_extraction_from_posts.ipynb :** Notebook for extracting paragraphs from `Posts.xml`
- **sample_bitcoin.stackexchange_sentences.txt :** It is the `sentences.txt` (pure sentences) file for `bitcoin.stackexchange.com` subdirectory of the dataset. It was generated from the corresponding paras.txt generated earlier using the code in ***sentence_extraction_from_paras.txt.ipynb***. The process took around 12.5 hours to complete.
- **sample_bitcoin.stackexchange_paras.txt :** It is the `paras.txt` (paragraph in html tags) file for ```bitcoin.stackexchange.com``` subdirectory of the dataset. It was generated from the ```Posts.xml``` using the code in ***paragraph_extraction_from_Posts.xml.ipynb***

## [Scoring](https://github.com/prateekguptaiiitk/Resume_Classifier/tree/develop/Scoring)

- **CV_ranking.ipynb :** Notebook for ranking the CVs according to JDs(Job Description)
- **Using Spacy Model.ipynb :** Demonstrates the need for a custom Word2Vector model rather than a general model trained otherwise. The similarity values generated by ``` en_core_web_md ``` spaCy model trained on Google News articles, do not reflect the `technological sharpness` required for the project.
- **With Word2Vec.ipynb :** Demonstrates how to use word2vec to get similar words by words and similar words by vector. It also implements sent2vec() function.  This function takes a sentence as a argument and returns a average vector for the sentence. Root Mean Square is used to average the vectors.  The advantage of this function is to use it to find similar words for phrases which makes more sense while searching for roles etc.

For example:
```
'web engineer' will give 'engineer' as a similar word
``` 
- **context.jpg :** Pie Chart showing the top three most frequent titles of `Job Descriptions`
- **prc_data.csv :** CSV file storing processed sections of different resumes.

## [Section Extraction](https://github.com/prateekguptaiiitk/Resume_Classifier/tree/develop/Section%20Extraction)

- **Section_Extraction.ipynb :** Notebook for extracting sections from different resumes.
- **convertDocxToText.py :** Python script for converting a `.docx` file to `.txt'.
- **convertPDFToText.py :** Python scrtpt for converting a `.pdf` file to `.txt`.
- **extract.py :** Python script for extracting compressed files in `7z`.
- **get_jd.ipynb :** Notebook for cleaning and extracting relevant portions of original jd.csv file from Kaggle.

## Author

<table>
<tr>
<td>
     <img src="https://avatars2.githubusercontent.com/u/29523950?s=400&u=878e242ca2c624eb45a62bf62ae580a370b7a0ae&v=4" width="180"/>
     
     Prateek Gupta

<p align="center">
<a href = "https://github.com/prateekguptaiiitk"><img src = "http://www.iconninja.com/files/241/825/211/round-collaboration-social-github-code-circle-network-icon.svg" width="36" height = "36"/></a>
<a href = "https://twitter.com/prateek_gupta21"><img src = "https://www.shareicon.net/download/2016/07/06/107115_media.svg" width="36" height="36"/></a>
<a href = "https://www.linkedin.com/in/prateekjpg/"><img src = "http://www.iconninja.com/files/863/607/751/network-linkedin-social-connection-circular-circle-media-icon.svg" width="36" height="36"/></a>
</p>
</td>
</tr> 
  </table>
