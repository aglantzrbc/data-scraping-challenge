# Data Scraping Challenge

## data-scraping-challenge
Glantz Adam Bootcamp RUT-VIRT-DATA-PT-04-2023-U-LOLC-MWTH - Module 11 Data Scraping Challenge

## TABLE OF CONTENTS

1. Project Description
   - Task: Scrape Titles and Preview Text from Mars News
   - Task: Scrape and Analyze Mars Weather Data
2. Installation
3. Contributing
4. Acknowledgements
5. Licenses

### 1. PROJECT DESCRIPTION

This project consists of two related technical tasks related to the exploration of Mars. First, the author was instructed to **scrape the titles and preview text from the article entries in [edX's](https://www.edx.org/) _[Mars News](https://static.bc-edx.com/data/web/mars_news/index.html)_ website**. After this, the author was told to **scrape temperature and related data from edX's [_Mars Temperature Data_](https://static.bc-edx.com/data/web/mars_facts/temperature.html) website and analyze it to answer several questions about natural time-related processes on Mars**. *Coding was guided by the DRY ("don't repeat yourself") principle.*

- [Task: Scrape Titles and Preview Text from *Mars News*](https://courses.bootcampspot.com/courses/3337/assignments/54002?module_item_id=961399)

**FILE:** part_1_mars_news.ipynb

The *Mars News* website was visited with the assistance of the [Splinter](https://splinter.readthedocs.io/en/latest/) library in Python and the site's code was examined using [Google Chrome DevTools](https://developer.chrome.com/docs/devtools/) in preparation for data scaping. The purpose of the examination was to discover HTML coding elements, such as a particular tag type, or a class or id, that could be use to isolate elements of interest for data scraping. Data scraping itself commenced using the [BeautifulSoup](https://realpython.com/beautiful-soup-web-scraper-python/) library to extract the *header* and *summary* elements in the HTML markup of the site's articles using unique class values. These elements, shorn of their markup, were associated with dictionaries as the keys *title* and *preview*, respectively, and the dictionaries were appended to a list. The list was then printed out, as shown below in **Figure 1**, for easy reference of all the website's article text.

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/51171e03-0b84-4e12-b117-09f776fee8f6)

**Figure 1** | *Jupyter Notebook output of the articles from* Mars News *as a list of dictionaries, with the keys "title" and "preview"*

- [Task: Scrape and Analyze Mars Weather Data](https://courses.bootcampspot.com/courses/3337/assignments/54002?module_item_id=961399)

**FILE:** part_2_mars_weather.ipynb

Similarly to the first task, this task started with The *Mars Temperature Data* website visited with the assistance of the Splinter library in Python and the site's code was examined using Google Chrome DevTools in preparation for data scaping. As before, the purpose of the examination was to discover HTML coding elements, such as a particular tag type, or a class or id, that could be use to isolate elements of interest for data scraping. Data scraping itself commenced using the BeautifulSoup library to extract the relevant column headers and the data associated with them by using a unique class value. These elements, shorn of their markup, were tabulated into a DataFrame.

Definitions of the column headers are in **Figure 2** and a sampling of the DataFrame is in **Table 1**.

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/a99a47ec-2f5a-4d12-9457-6ed836e0c049)

**Figure 2** | *Definitions of the column headers in the* Mars Temperature Data *webpage*

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/5048eaac-cfd1-446a-aebe-6886f6ab6bc8)

**Table 2** | *Sampling of the resulting DataFrame of values for each column header*

After the column data types were cast into correct categories, the following questions werre addressed:

1. *How many months are there on Mars?* **Answer: 12 months**. See **Figure 3**, below.

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/ed7ff136-b210-4a9e-8c4e-0109a3d50f0d)

**Table 3** | *Counts of Martian days (sols) by month, with the answer to the first question highlighted at the bottom*

2. *How many sols worth of data are there?* **Answer: 1867 sols**. This was obtained by a simple count of the number of sols in the dataset.
   
3. *What is the average low temperature by month?* See **Table 4** and **Figure 4**, below. Temperature measurements are in Celsius.

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/c990b4d3-9295-486e-b30f-ada6772aed88)

**Table 4** | *Average minimum temperature on Mars per month in Celsius*

- *The coldest month on Mars is: month 3*
- *The hottest month on Mars is: month 8*

![mars_average_temp_by_month](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/e874566c-fd89-44f2-b4ce-70826347e2de)

**Figure 4** | *Months corresponding to the minimum and maximum temperatures on Mars, with the extremes annotated*

### 2. INSTALLATION

- Climate data analysis and exploration file: **sqlalchemy-challenge_climate.ipynb**
- Climate app file: **sqlalchemy-challenge_app.py**

- The [GitHub repository](https://github.com/aglantzrbc/sqlalchemy-challenge) containing all project files is publicly accessible.
- The assignment details and starter code are proprietary and located on the [Rutgers University](https://www.rutgers.edu/) ([edX](https://www.edx.org/)) Bootcamp Spot [Module 10 SQLAlchemy Challenge](https://courses.bootcampspot.com/courses/3337/assignments/54000?module_item_id=961336) page.
- All code source files are Python version 3.10.9. The data source is an [.sqlite file](https://www.sqlite.org/index.html). **It's assumed that a Resources subdirectory containing the hawaii.sqlite data file is in the same location as the code files. If this is not the case, the code won't run.**
- The first part of the project was coded in [Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/stable/) version 6.5.2, the second part in [VSCode](https://code.visualstudio.com/) version 1.79.2.

### 3. CONTRIBUTING

- [Glantz, Adam](https://www.linkedin.com/in/adam-glantz/): Annapolis, Maryland, USA, June 2023, email: adamglantz@yahoo.com

### 4. ACKNOWLEDGEMENTS

In addition to using the GitHub, Rutgers University (edX), Jupyter Notebook, and VSCode resources listed above, the author acquired query responses in OpenAI's [ChatGPT](https://chat.openai.com/) platform.

The author also consulted code and results from similar projects publicly accessible in [GitHub](https://github.com/) repositories and recoverable through [Google](https://www.google.com/) and comparable search engines:

- [Mehta, Pragati](https://www.linkedin.com/in/pragati-mehta-%E2%99%95-3b10823/): Pennington, New Jersey, USA, September 2018. [Hawaii-Climate-Analysis-using-SQLALCHEMY](https://github.com/PragatisGitHub/Hawaii-Climate-Analysis-using-SQLALCHEMY)
- [Thorpe, Margaret](https://www.linkedin.com/in/margaret-thorpe-datapm/): Trinidad, California, USA, May 2021. [sqlalchemy-challenge](https://github.com/MThorpester/sqlalchemy-challenge)
- [Yousuf, Bennet](https://www.linkedin.com/in/bennetyousuf/): Dallas, Texas, USA, June 2021. [sqlalchemy-challenge](https://github.com/bennetyousuf/sqlalchemy-challenge)

### 5. LICENSES

**N/A**


