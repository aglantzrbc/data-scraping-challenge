# Data Scraping Challenge

## data-scraping-challenge
Glantz Adam Bootcamp RUT-VIRT-DATA-PT-04-2023-U-LOLC-MWTH - Module 11 Data Scraping Challenge

## TABLE OF CONTENTS

1. Project Description
   - Task: Scrape Titles and Preview Text from *Mars News*
   - Task: Scrape and Analyze Mars Weather Data
2. Installation
3. Contributing
4. Acknowledgements
5. Licenses

### 1. PROJECT DESCRIPTION

This project consists of two technical tasks using [data scraping](https://en.wikipedia.org/wiki/Data_scraping) related to the exploration of Mars. First, the author was instructed to **scrape the titles and preview text from the article entries in [edX's](https://www.edx.org/) _[Mars News](https://static.bc-edx.com/data/web/mars_news/index.html)_ website**. After this, the author was told to **scrape temperature and related data from edX's [_Mars Temperature Data_](https://static.bc-edx.com/data/web/mars_facts/temperature.html) website and analyze it to answer several questions about natural time-related processes on Mars**. *Coding was guided by the [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) ("don't repeat yourself") principle.*

- [Task: Scrape Titles and Preview Text from *Mars News*](https://courses.bootcampspot.com/courses/3337/assignments/54002?module_item_id=961399)

**FILE:** part_1_mars_news.ipynb

The *Mars News* website was visited with the assistance of the [Splinter](https://splinter.readthedocs.io/en/latest/) library in Python and the site's code was examined using [Google Chrome DevTools](https://developer.chrome.com/docs/devtools/) in preparation for data scaping. The purpose of the examination was to discover HTML coding elements, such as a particular tag type, or a class or id, that could be use to isolate elements of interest for data scraping. Data scraping itself commenced using the [Beautiful Soup](https://realpython.com/beautiful-soup-web-scraper-python/) library to extract the *header* and *summary* elements in the HTML markup of the site's articles using unique class values. These elements, shorn of their markup, were associated with dictionaries as the keys *title* and *preview*, respectively, and the dictionaries were appended to a list. The list was then printed out, as shown below in **Figure 1**, for easy reference of all the website's article text.

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/51171e03-0b84-4e12-b117-09f776fee8f6)

**Figure 1** | *Jupyter Notebook output of the articles from* Mars News *as a list of dictionaries, with the keys "title" and "preview"*

- [Task: Scrape and Analyze Mars Weather Data](https://courses.bootcampspot.com/courses/3337/assignments/54002?module_item_id=961399)

**FILE:** part_2_mars_weather.ipynb

Similarly to the first task, this task started with The *Mars Temperature Data* website visited with the assistance of the Splinter library in Python and the site's code was examined using Google Chrome DevTools in preparation for data scaping. As before, the purpose of the examination was to discover HTML coding elements, such as a particular tag type, or a class or id, that could be use to isolate elements of interest for data scraping. Data scraping itself commenced using the Beautiful Soup library to extract the relevant column headers and the data associated with them by using a unique class value. These elements, shorn of their markup, were tabulated into a DataFrame.

Definitions of the column headers are in **Figure 2** and a sampling of the DataFrame is in **Table 1**.

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/a99a47ec-2f5a-4d12-9457-6ed836e0c049)

**Figure 2** | *Definitions of the column headers in the* Mars Temperature Data *webpage*

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/5048eaac-cfd1-446a-aebe-6886f6ab6bc8)

**Table 1** | *Sampling of the resulting DataFrame of values for each column header*

After the column data types were cast into correct categories, the following questions werre addressed:

1. *How many months are there on Mars?* **Answer: 12 months**. See **Figure 3**, below.

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/ed7ff136-b210-4a9e-8c4e-0109a3d50f0d)

**Figure 3** | *Counts of Martian days (sols) by month, with the answer to the first question highlighted at the bottom*

2. *How many sols worth of data are there?* **Answer: 1867 sols**. This datum was obtained by a simple count of the number of rows in the dataset.
   
3. *What is the average low temperature by month?* See **Table 2** and **Figure 4**, below. Temperature measurements are in Celsius (C).

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/c990b4d3-9295-486e-b30f-ada6772aed88)

**Table 2** | *Average minimum temperature on Mars per month in Celsius, as measured on the surface by the NASA rover* Curiosity

- *The coldest month on Mars is: month 3 (-83.307292 Celsius)*
- *The hottest month on Mars is: month 8 (-68.382979 Celsius)*

![mars_temp_extremes_by_month](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/3bf8f117-9d22-4cd7-a0f2-ca6351c2ea26)

**Figure 4** | *Months corresponding to the minimum and maximum temperatures on Mars in Celsius, as measured on the surface by the NASA rover* Curiosity, *with the extremes annotated*

4. *What is the average atmospheric pressure per Martian month?* See **Table 3** and **Figure 5**, below. Pressure measurements are in Pascals (Pa).

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/12808553-d308-4606-9187-0c0c79b50053)

**Table 3** | *Average pressure on Mars per month in Pascals, as measured on the surface by the NASA rover* Curiosity

- *The month with the lowest average atmospheri pressure on Mars is: month 6 (745.054422 Pascals)*
- *The month with the highest average atmospheric pressure on Mars is: month 9 (913.305970 Pascals)*

![mars_average_pressure_by_month](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/4bfd6f1e-3f25-4bc9-8671-eb75a1878f47)

**Figure 5** | *Months corresponding to the minimum and maximum atmospheric pressure on Mars in Pascals, as measured on the surface by the NASA rover* Curiosity, *with the extremes annotated*

5. *How many terrestrial (earth) days are there in a Martian year?* See **Figure 6** and **Figure 7**, below.

This questions was answered using three different inputs:

- The author's estimate from the highest minimum temperature data points from a full seasonal cycle in the middle of the **Figure 6** plot is: **1,375 - 700 = _675_ terrestrial days in a Martian year.** This is a match for what's indicated in the code comments.
- As noted in the code comments, as derived from an internet search, **the number of terrestrial days in a Martian year according to [NASA](https://solarsystem.nasa.gov/planets/mars/in-depth/#:~:text=Martian%20days%20are%20called%20sols,its%20orbit%20around%20the%20Sun) (which launched the *Curiosity* rover) is: _687_.**
- Using 24 hours as the typical duration a a terrestrial day, the code iteratively sums the number of sols, then divides the total by 24. **The number of terrestrial days in a Martian year according to this process: _694.291667_.** This is somewhat higher than what the author found through other means, but still within a +/- 25% range.


![mars_days_in_terrestrial_year](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/c28c146d-3955-4aac-9be9-2fe9ff621095)

**Figure 6** | *The number of terrestrial days vs. the minimum surface temperature in Celsius on Mars, as measured on the surface by the NASA rover* Curiosity, *with seasonal high temperature points in the middle of the plot noted*

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/eacb0116-c824-475d-bfe9-4cf560e925df)

**Figure 7** | *Code comments from the assignment instructions, for comparison with the author's findings, with the internet search finding highlighted*

### 2. INSTALLATION

- The file for the *Scrape Titles and Preview Text from* Mars News task: **part_1_mars_news.ipynb**
- The file for the *Scrape and Analyze Mars Weather Data* task: **part_2_mars_weather.ipynb**

- The [GitHub repository](https://github.com/aglantzrbc/data-scraping-challenge) containing all project files is publicly accessible.
- The *Resources* subdirectory contains the DataFrame *mars_weather_data_dataframe.csv* file requested by the instructions, as well as .png versions of all project plots. It is located in the same place as the code files.
- The assignment details and starter code are proprietary and located on the [Rutgers University](https://www.rutgers.edu/) [(edX)](https://www.edx.org/) Bootcamp Spot [Module 11 Data Scraping Challenge](https://courses.bootcampspot.com/courses/3337/assignments/54002?module_item_id=961399) webpage.
- Both source files use Python version 3.10.9. The project was coded in [Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/stable/) version 6.5.2.

### 3. CONTRIBUTING

- [Glantz, Adam](https://www.linkedin.com/in/adam-glantz/): Annapolis, Maryland, USA, June 2023, email: adamglantz@yahoo.com

### 4. ACKNOWLEDGEMENTS

In addition to using the GitHub, Rutgers University (edX), and Jupyter Notebook resources listed above, the author acquired query responses in OpenAI's [ChatGPT](https://chat.openai.com/) 3.5 platform and the [VSCode GitHub Copilot](https://github.com/features/copilot) app.

The author also consulted code and results from similar projects publicly accessible in [GitHub](https://github.com/) repositories and recoverable through [Google](https://www.google.com/) and comparable search engines:

- [Abdelrahman, Ahmed](https://www.linkedin.com/in/ahmadhha/): Mississauga, Ontario, Canada, January 2023. [scraping_and_analysis-challenge](https://github.com/Ahmadhha/scraping_and_analysis-challenge)
- [Guturi, Bharat](https://www.linkedin.com/in/bharat-guturi/): Perth, Western Australia, Australia, February 2023. [Mars-weather-data-scraping-and-analysis](https://github.com/BharatGuturi/Mars-weather-data-scraping-and-analysis)

### 5. LICENSES

**N/A**


