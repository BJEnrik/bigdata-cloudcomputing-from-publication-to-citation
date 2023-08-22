![image.png](resources/banner.png)

<h1 style="background-color:#003b7f;color:#ffffff;padding:20px">Executive Summary</h1>

In today's competitive academic landscape, optimizing research efforts and ensuring the impact of scholarly work is crucial. However, a significant number of journal articles remain uncited and unnoticed, highlighting the need for a system to enhance research visibility and reach.

Our project aims to understand what makes a publication impactful and worthy of citation. By uncovering the factors that contribute to research impact, we can develop strategies to increase the visibility and recognition of scholarly articles.

We are driven by the need to address the challenges of research impact and bridge the gap between published research and its actual influence. Leveraging machine learning techniques and data analysis, we aim to develop a predictive model that can identify the factors influencing the citation and readership of scholarly articles. This model will help researchers and institutions prioritize their efforts by focusing on articles with a higher potential for citation and readership.

To achieve this, we are using the April 2023 Public Data File from Crossref, a comprehensive dataset containing scholarly metadata from various publications. This dataset provides standardized access to scholarly information for analysis and research purposes.

During the analysis, we compared the performance of three models: random forest, gradient boosting trees, and multilayer perceptrons. The gradient boosting trees model exhibited superior results, with a train accuracy of 84.92% and a test accuracy of 75.21%. This indicates the model's ability to generalize well to unseen data, instilling greater confidence in its predictions.

For researchers in stable fields, staying updated with emerging fields and exploring interdisciplinary collaborations can open new opportunities. Researchers seeking funding should encourage interdisciplinary collaborations, while those in the field of Data Science can leverage their expertise to contribute to the growing demand in the field.

In conclusion, our project addresses the challenges of research impact by developing a predictive model that identifies the factors influencing citation and readership. We provide valuable insights into the determinants of article impact, empowering researchers to make informed decisions about their publishing strategies. This leads to increased visibility, recognition, and wider dissemination of their work.

---

<h1 style="background-color:#003b7f;color:#ffffff;padding:20px">Problem Statement</h1>

Our project aims to address the significant challenge of low citation rates and limited readership for journal articles, which has far-reaching implications for the scholarly community and the broader research landscape. *What are the factors that contribute to higher citation rates and readership?* By answering this very question, our study has the potential to unlock the hidden value of research, optimize research efforts, and foster a more efficient and impactful research ecosystem. *How do these factors affect the policies when it comes to research? How can these factors empower researchers in facilitating collaboration and in accelerating advancement in knowledge, in any field of study?*

Overall, we want to answer this question: **What determines the impact and citation-worthiness of a research publication, crucial for a researcher's recognition and access to opportunities?**, in an attempt to address the challenge of low citation rates, limited readership, the implications of these to the scholarly community and research landscape, and the hidden value of research to drive changes in policies in terms of collaboration, knowledge sharing, and accelerated advancements.

---

<h1 style="background-color:#003b7f;color:#ffffff;padding:20px">Motivation</h1>

In today's highly competitive and multidisciplinary [[5]](https://direct.mit.edu/qss/article/1/2/730/96146/How-common-are-explicit-research-questions-in) academic landscape, where time and resources are scarce, it becomes crucial to optimize research efforts and ensure the impactful dissemination of scholarly work. Surprisingly, studies have shown that a significant portion of journal articles, approximately 90% [[1]](https://blogs.lse.ac.uk/impactofsocialsciences/2014/04/23/academic-papers-citation-rates-remler/)[[2]](https://www.smithsonianmag.com/smart-news/half-academic-studies-are-never-read-more-three-people-180950222/), remain uncited [[3]](https://www.insidehighered.com/news/2018/04/19/study-examines-research-never-receives-citation), while around 50% go largely unnoticed by anyone beyond their authors and editors. This alarming trend highlights the need for a robust and efficient system to enhance the visibility and reach of research outputs.

The motivation behind our project lies in addressing these challenges and bridging the gap between the vast amount of published research and its actual impact.

By leveraging machine learning techniques and data analysis, we aim to develop a predictive model that can identify the factors influencing the citation [[4]](https://journals.sagepub.com/doi/10.1177/2158244019829575) and readership of scholarly articles. This model will help researchers and institutions prioritize their efforts by focusing on articles with a higher potential for citation and readership. By providing valuable insights into the determinants of article impact, we hope to empower researchers to make informed decisions about their publishing strategies, ultimately leading to increased visibility, recognition, and the wider dissemination of their work.

---

<h1 style="background-color:#003b7f;color:#ffffff;padding:20px">Data Source</h1>

<span style="color:#003b7f; font-size:18px"><i>Original Data Source</i></span>

The original data source for the April 2023 Public Data File is [Crossref](https://www.crossref.org/).

Crossref is a non-profit organization that provides DOIs and comprehensive metadata for academic and scholarly content. They collaborate with publishers, institutions, and researchers to ensure the accurate and reliable dissemination of scholarly 

<span style="color:#003b7f; font-size:18px"><i>April 2023 Public Data File from Crossref</i></span>

The April 2023 Public Data File from Crossref is a comprehensive dataset that contains scholarly metadata from various publications. It includes bibliographic information such as titles, authors, publication dates, DOIs (Digital Object Identifiers), abstracts, and citation data. This dataset aims to provide researchers, developers, and stakeholders with standardized access to scholarly information for analysis and research purposes.

<span style="color:#003b7f; font-size:18px"><i>Download Details</i></span>

*The dataset can be downloaded from [Academic Torrents](https://academictorrents.com/details/d9e554f4f0c3047d9f49e448a7004f7aa1701b69).*

Academic Torrents is a platform dedicated to sharing and distributing large scientific datasets. It collaborates with researchers, institutions, and organizations to make academic data openly accessible, fostering data-driven research and promoting collaboration among scholars worldwide.

<span style="color:#003b7f; font-size:18px"><i>Crossref Unified Resource API</i></span>

There is also an available [Resource API](https://api.crossref.org) for the April 2023 Public Data File to allow for efficient retrieval and linking of scholarly metadata from a vast network of publications.

The API enables researchers to access and integrate the dataset seamlessly into their research workflows, facilitating data-driven analyses and investigations across a wide range of scholarly materials.

<span style="color:#003b7f; font-size:18px"><i>Dataset Summary</i></span>

- is a data file of the public elements from Crossref’s 143.5+ million metadata records.
- includes bibliographic information such as titles, authors, publication dates, DOIs, abstracts, and citation data.
- also includes details about the journal or publication venue, such as the journal name, ISSN (International Standard Serial Number), publisher, and volume/issue numbers.
- terms or phrases used to describe the main topics or subjects covered in the publication.
- information on whether the full text of the publication is freely accessible or requires a subscription or purchase.
- details about the funding sources that supported the research or publication.
- information about the licensing terms and usage rights associated with the publication.

<span style="color:#003b7f; font-size:18px"><i>AWS S3 Bucket</i></span>

The data was sourced from Academic Torrents and securely stored in an S3 bucket owned by Capstone Team One. Initially downloaded as JSON files, the data was subsequently transformed into parquet files, leveraging the benefits of its columnar format for optimized storage and analysis.

*Amazon Resource Name (ARN)*

```python
arn:aws:s3:::s3bucketemr-sydney
```
<br>

*AWS Region*

```python
ap-southeast-2
```
<br>

*AWS CLI Access (AWS Account Required)*

```python
aws s3 ls s3://s3bucketemr-sydney/
```
<br>

*AWS EMR*
![cluster.png](resources/cluster.png)
<div>
    <p style="font-size:10px;font-style:default;text-align:center">
        <b>Figure 1. AWS EMR Cluster.</b><br>
        <i>AWS EMR Cluster used for the development of this project.</i>
    </p>
</div>
<br>

<h2 style="color:#003b7f;">Raw Crossref Data</h2>

The raw Crossref dataset (see descriptions in Table 1) is a highly nested dataset with multiple layers of variables. In this representation, we will focus on the root variables, providing a glimpse into the structure of the dataset.

|<center>Variable Name</center>|<center>Data Type</center>|<center>Description</center>
|:---------------------|:-------|:---|
|DOI                   |string  |String representing the Digital Object Identifier for the research paper.
|ISBN                  |array   |Array of International Standard Book Numbers associated with the research paper.
|ISSN                  |array   |Array of International Standard Serial Numbers associated with the research paper.
|URL                   |string  |String representing the URL of the research paper.
|abstract              |string  |String containing the abstract or summary of the research paper.
|accepted              |struct  |Struct containing information about the acceptance status of the research paper.
|alternative-id        |array   |Array of alternative identifiers associated with the research paper.
|approved              |string  |Struct containing information about the approval status of the research paper.
|archive               |array   |Array of archive names where the research paper is stored.
|article-number        |string  |String representing the article number of the research paper.
|assertion             |array   |Array of assertions made in the research paper.
|author                |array   |Array of authors associated with the research paper.
|award                 |string  |String representing any award received by the research paper.
|award-start           |struct  |Struct containing information about the start of the award associated with the research paper.
|chair                 |array   |Array of chairs or committee members associated with the research paper.
|clinical-trial-number |array   |Array of clinical trial numbers related to the research paper.
|container-title       |array   |Array of container titles where the research paper is published.
|content-created       |struct  |Struct containing information about the content creation of the research paper.
|content-domain        |struct  |Struct containing information about the content domain of the research paper.
|content-updated       |struct  |Struct containing information about the content update of the research paper.
|created               |struct  |Struct containing information about the creation of the research paper.
|degree                |array   |Array of degrees associated with the research paper.
|deposited             |struct  |Struct containing information about the deposition of the research paper.
|description           |string  |String containing a description or additional details about the research paper.
|edition-number        |string  |String representing the edition number of the research paper.
|editor                |array   |Array of editors associated with the research paper.
|event                 |struct  |Struct containing information about the event associated with the research paper.
|funder                |array   |Array of funders or funding organizations associated with the research paper.
|group-title           |string  |String representing the group title of the research paper.
|indexed               |struct  |Struct containing information about the indexing of the research paper.
|institution           |array   |Array of institutions associated with the research paper.
|is-referenced-by-count|long    |Long representing the count of references made to the research paper.
|isbn-type             |array   |Array of ISBN types associated with the research paper.
|issn-type             |array   |Array of ISSN types associated with the research paper.
|issue                 |string  |String representing the issue number of the research paper.
|issued                |struct  |Struct containing information about the issuance of the research paper.
|journal-issue         |struct  |Struct containing information about the journal issue of the research paper.
|language              |string  |String representing the language of the research paper.
|license               |array   |Array of licenses associated with the research paper.
|link                  |array   |Array of links associated with the research paper.
|member                |string  |String representing the member or membership status associated with the research paper.
|original-title        |array   |Array of original titles associated with the research paper.
|page                  |string  |String representing the page numbers of the research paper.
|part-number           |string  |String representing the part number of the research paper.
|posted                |struct  |Struct containing information about the posting of the research paper.
|prefix                |string  |String representing the prefix associated with the research paper.
|project               |array   |Array of projects associated with the research paper.
|published             |struct  |Struct containing information about the publication of the research paper.
|published-online      |struct  |Struct containing information about the online publication of the research paper.
|published-other       |struct  |Struct containing information about other types of publication of the research paper.
|published-print       |struct  |Struct containing information about the print publication of the research paper.
|publisher             |string  |String representing the publisher of the research paper.
|publisher-location    |string  |String representing the location of the publisher of the research paper.
|reference             |array   |Array of references cited in the research paper.
|reference-count       |long    |Long representing the count of references in the research paper.
|references-count      |long    |Long representing the count of references associated with the research paper.
|relation              |struct  |Struct containing information about the relation or relationship of the research paper.
|resource              |struct  |Struct containing information about the resource associated with the research paper.
|review                |struct  |Struct containing information about the review process of the research paper.
|score                 |double  |Double representing the score or rating assigned to the research paper.
|short-container-title |array   |Array of abbreviated container titles where the research paper is published.
|short-title           |array   |Array of abbreviated titles associated with the research paper.
|source                |string  |String representing the source of the research paper.
|standards-body        |struct  |Struct containing information about the standards body associated with the research paper.
|subject               |array   |Array of subjects or topics associated with the research paper.
|subtitle              |array   |Array of subtitles associated with the research paper.
|subtype               |string  |String representing the subtype of the research paper.
|title                 |array   |Array of titles associated with the research paper.
|translator            |array   |Array of translators associated with the research paper.
|type                  |string  |String representing the type or category of the research paper.
|update-policy         |string  |String representing the update policy associated with the research paper.
|update-to             |array   |Array of updates associated with the research paper.
|volume                |string  |String representing the volume number of the research paper.

<br>
<div>
    <p style="font-size:10px;font-style:default;text-align:center">
        <b>Table 1. Crossref Raw Data Description.</b><br>
        <i>Raw Crossref dataset description.</i>
    </p>
</div>

<h2 style="color:#003b7f;">Final Crossref Data</h2>

The final Crossref dataset contains information related to research papers and their attributes. The dataset is structured as shown in Table 2.

|<center>Pillar</center>|<center>Variable Name</center>|<center>Data Type</center>|<center>Description</center>
|:--------------------------|:---------------------|:-------|:---|
|Diversity & Quality offered|title                 |string  |Title of the paper
|Diversity & Quality offered|title_token_length    |integer |Array of International Standard Book Numbers associated with the research paper.
|Diversity & Quality offered|type                  |string  |Type of publication
|Diversity & Quality offered|abstract              |string  |Abstract of the paper
|Diversity & Quality offered|subject_list          |array   |Domains/fields of the study
|Diversity & Quality offered|num_subjects          |integer |Number of domains/fields of the study
|Financial Resources        |num_funder_awards     |integer |Number of awarded funds
|Financial Resources        |num_funders           |integer |Number of funders
|Network/Connections        |institution_name      |string  |Name of the institution that the author is affiliated with
|Network/Connections        |institution_place     |string  |Location of the institution
|Network/Connections        |num_authors           |integer |Number of authors
|Network/Connections        |affiliation_list      |array   |Name of each affiliation
|Network/Connections        |num_affiliations      |integer |Number of affiliations the authors have based on affiliation_id
|Timeliness & Accessibility |published_year        |long    |Year when the paper was published
|Timeliness & Accessibility |published_month       |long    |Month when the paper was published
|Timeliness & Accessibility |published_day         |long    |Day when the paper was published
|Timeliness & Accessibility |issn_type             |string  |International Standard Book Number (ISBN): identifies a single, nonrecurring publication, such as an journal
|Opportunity                |is-referenced-by-count|long    |Number of times the paper was referenced by another
|Opportunity                |cited_pct             |double  |Citation percentage of the paper
|Opportunity                |opportunity_index     |integer |Targets, [0, 1]. 0: Upper quantile of citation_pct, 1: Lower quantile of citation_pct

<br>
<div>
    <p style="font-size:10px;font-style:default;text-align:center">
        <b>Table 2. Final Crossref Dataset Description.</b><br>
        <i>Project's final dataset description.</i>
    </p>
</div>

The final dataset for this project consists of four main pillars: <span style='color:#d54949'>**diversity and quality**</span>, <span style='color:#f3c953'>**financial resources**</span>, <span style='color:#515a59'>**network and connections**</span>, and <span style='color:#5fb0c5'>**timeliness and accessibility**</span>.

Under the <span style='color:#d54949'>**diversity and quality**</span> pillar, we have features related to the content of the publications, including the title, domains, subjects, and abstracts of the studies.

The <span style='color:#f3c953'>**financial resources**</span> pillar encompasses features related to funding, such as the amount of funds awarded for the study and the granting body or funding institution.

The <span style='color:#515a59'>**network and connections**</span>  pillar focuses on the affiliations associated with the study, including the authors, institutions, and locations involved.

The <span style='color:#5fb0c5'>**timeliness and accessibility**</span> pillar includes metadata about the publication, such as the publication date and the publication type.

Additionally, there is a group of features under the *opportunity* pillar, which serves as the target variable for this study. These features include the citations count, citations percentage, and the opportunity index, which will be discussed further in subsequent sections.

Overall, this dataset provides valuable information about the diversity and quality of research papers, financial resources allocated to them, network connections of the authors, timeliness and accessibility factors, and the opportunity level of the papers.

---

<h1 style="background-color:#003b7f;color:#ffffff;padding:20px">Assumptions and Design Constraints</h1>

<span style="color:#003b7f; font-size:18px"><i>Proportionality Assumption</i></span>
 - It is assumed that the proportionality of the target variable in the sampled data reflects the proportionality of the original data. This assumption allows for generalization of the model's performance on the entire dataset based on the sampled data.

 - <span style="color:#003b7f; font-size:18px"><i>Modularity</i></span>
- The machine learning pipeline is designed with modularity in mind. This allows for flexibility in modifying and reusing specific stages of the pipeline without running the entire pipeline repeatedly.

- <span style="color:#003b7f; font-size:18px"><i>Memory Efficiency</i></span>
- To mitigate potential memory errors, the pipeline is optimized to minimize unnecessary re-computation. By storing intermediate results in separate variables, such as the train_data and test_data, the pipeline can be executed without rerunning the entire process.

- <span style="color:#003b7f; font-size:18px"><i>Hyperparameter Tuning</i></span>
- Hyperparameter tuning is performed separately for each model. This approach promotes modularity and reduces the risk of memory errors by focusing on optimizing individual models rather than running all models as a single pipeline.

- <span style="color:#003b7f; font-size:18px"><i>Usable Features</i></span>
- Features are selected based on their relevance to the prediction task. The design ensures that each pillar is represented by at least two features, which helps capture the essence of each pillar in the analysis.

- <span style="color:#003b7f; font-size:18px"><i>Baseline Comparison</i></span>
- The proportional chance criterion (PCC) is established as a baseline to compare the model's performance. To consider the predictions as good, the accuracy of the model needs to exceed 1.25 times the PCC.

- <span style="color:#003b7f; font-size:18px"><i>Performance Evaluation</i></span>
- The performance of each model is evaluated using various metrics, including accuracy, precision, recall, and F1-score. These metrics provide insights into the model's predictive capabilities and its ability to correctly classify instances.

- <span style="color:#003b7f; font-size:18px"><i>Feature Importance</i></span>
- For tree-based models (random forest and gradient boosting trees), the feature importance is extracted to identify the most influential features. This analysis helps understand the contribution of each feature towards the model's predictions.

- <span style="color:#003b7f; font-size:18px"><i>Neural Network Model</i></span>
- A multilayer perceptron (MLP) model with two hidden layers is employed. Hyperparameter tuning is performed by varying parameters such as maxIter and blockSize to optimize the model's performance.

- <span style="color:#003b7f; font-size:18px"><i>Interpretability</i></span>
- The weights of the MLP model are extracted to provide feature importance, allowing for interpretability of the model's predictions.

- <span style="color:#003b7f; font-size:18px"><i>Comparison with Existing Models</i></span>
- The performance of the MLP model is compared against the results obtained from the random forest and gradient boosting trees models. This comparison helps assess whether the MLP model provides better accuracy and predictive capabilities.

These assumptions and design constraints provide the foundation for developing and evaluating the machine learning models. They consider memory efficiency, modularity, feature relevance, interpretability, and performance evaluation to ensure accurate and efficient predictions based on the provided information.

---

**Read of the Full Content from the given notebook.**
