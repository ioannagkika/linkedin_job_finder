# LinkedIn Job Finder

## A few words about this project

The aim of the project is to build an analytics pipeline that shows what job openings are related to machine learning or AI. 

In more detail, we setup a worklfow with Weaviate, where we created a vector database of 123849 job postings. The data used to create the database is a subset of the [LinkedIn Job Postings (2023 - 2024)](https://www.kaggle.com/datasets/arshkon/linkedin-job-postings) from Kaggle. The dataset has 28 columns containing useful information regarding the job openings (e.g. the title of the job, the company, the skills required, the linkedin url etc.). We only included 5 of the columns in our database, namingly: company_name, title, skills_desc, description and job_posting_url. We also created and added a new column (merged_col) that had the company_name, title, skills_desc and description merged. This column (merged_col) is the one that was vectorized in our database using OpenAI's text-embedding-3-small model. 

We used Weaviate's Vector and Keyword search and searched for the terms: "Machine Learning AI", "Machine Learning", "Data Science", "Artificial Intelligence".The unique data that all of our searches output were then saved to a csv and we finally had 496 unique job offers related to ML or AI. 

## Instructions

1. Clone the repo locally or just download the current folder.

2. Download the [LinkedIn Job Postings (2023 - 2024)](https://www.kaggle.com/datasets/arshkon/linkedin-job-postings) from Kaggle and put them in the repo directory.

3. Create a [Weaviate](https://weaviate.io/) account and a free Sandbox cluster.

4. Set the WCD_URL, and WCD_API_KEY as enviornmental variables. 

5. Set the OpenAI's API key as environmental variable (you can follow OpenAI's guidelines [here](https://help.openai.com/en/articles/5112595-best-practices-for-api-key-safety))

6. Get into the repo directory, install the requirements with the command:

```bash
pip install -r requirements.txt
```

and then run the weaviate_notebook.ipynb

7. You are done! In case you want to close everything uncomment and run the final cell of the weaviate_notebook.ipynb.
