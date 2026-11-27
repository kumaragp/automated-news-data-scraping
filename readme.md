
# Automated News Data Scrapping

This program code is used to perform web scraping on Indonesian news websites in order to automatically extract news data. The data extracted typically includes the news source, news headline, URL, news category, and time of extraction. The news websites from which data is extracted are as follows:
- CNN
- KOMPAS

## Feature
- Interval data collection
- Connected to a cloud server
- Preprocessing using Spark
- Data visualization

## Teknologi
- Python
- Supabase
- Databricks Free Version
- Docker

## Installation Guide
To run the program code above, follow these steps in order to ensure that the web scraping process runs smoothly:

1. Clone Repository.
~~~ bash
git clone https://github.com/kumaragp/scraping-data.git
~~~

2. Make sure you've created a Supabase and Databricks account

3. Log in to Supabase and create a new project

4. Create a database table with the following configuration:

| Columns Name | Type     | Deffault Value  | Primary |
| :----------- | :------- | :-------------- | :------ |
| id           | int8     | NULL            |   II    |
| source       | text     | ''::text        |   IN    |
| title        | text     | NULL            | IN & IU |
| url          | text     | NULL            | IN & IU |
| category     | text     | NULL            |   IN    |
| timestamps   | timstamp | NULL            |   IN    |

  - **II = Is Identify**
  - **IU = Is Unique**
  - **IN = Is Nullable**

5. Create a new notebook in Databricks from the Workspace menu

6. Download visualization.ipynb and import it into the Databricks workspace

7. Run the command in the code editor's terminal to start the crawling process, then make sure the data is saved to Supabase cloud storage
~~~ bash
docker compose up --build
~~~
8. Download the following dictionary [NRC_LEXICON](https://drive.google.com/file/d/1P_KTZP7MQJH_4nSM-7u1bPI-n8Tx491I/view?usp=drive_link)

9. Once the download is complete, move the files to Data Ingestion (accessible via the Catalog / Data menu -> select the destination volume -> Upload to this volume, or via the Data Ingestion workflow that leads to Upload files to a volume) -> adjust the respective directories, then copy the path and place it in the **nrc_path** located in the Databricks shell

9. Once the data is available, select “Run All” in Databricks to run the entire program

## Results
#### Wordclouds

#### Term Frequency (TF)
| Kata    | Frekuensi | Proporsi | Persentase |
| :------ | :-------- | :------- | :--------- |
| rp      | 41        | 0.008579 | 0.86       |
| tahun   | 37        | 0.007742 | 0.77       |
| jakarta | 35        | 0.007324 | 0.73       |
| hari    | 32        | 0.006696 | 0.67       |
| rumah   | 27        | 0.005650 | 0.56       |			

## Authors

- [@kumaragp](https://github.com/kumaragp)
- [@anthonydewantoro](https://github.com/Anthony091104)