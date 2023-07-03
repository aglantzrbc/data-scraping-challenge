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

This project consists of two related technical tasks related to the exploration of Mars. First, the author was instructed to **scrape the titles and preview text from the article entries in [edX's](https://www.edx.org/) _[Mars News](https://static.bc-edx.com/data/web/mars_news/index.html)_ website**. After this, the author was told to **scrape temperature and related data from edX's [_Mars Facts_](https://static.bc-edx.com/data/web/mars_facts/temperature.html) website and analyze it to answer several questions about natural time-related processes on Mars**. *Coding was guided by the DRY ("don't repeat yourself") principle.*

- [Task: Scrape Titles and Preview Text from *Mars News*](https://courses.bootcampspot.com/courses/3337/assignments/54002?module_item_id=961399)

**FILE:** part_1_mars_news.ipynb

The *Mars News* website was visited with the assistance of the [Splinter](https://splinter.readthedocs.io/en/latest/) library in Python and the site's code was examined using [Google Chrome DevTools](https://developer.chrome.com/docs/devtools/) in preparation for data scaping. The purpose of the examination was to discover HTML coding elements, such as a particular tag type, or a class or id, that could be use to isolate elements of interest for data scraping. Data scraping itself commenced using the [BeautifulSoup](https://realpython.com/beautiful-soup-web-scraper-python/) library to extract the *header* and *summary* elements in the HTML markup of the site's articles using unique class values. These elements, shorn of their markup, were associated with dictionaries as the keys *title* and *preview*, respectively, and the dictionaries were appended to a list. The list was then printed out, as shown below in **Figure 1**, for easy reference of all the website's article text.

![image](https://github.com/aglantzrbc/data-scraping-challenge/assets/127694342/51171e03-0b84-4e12-b117-09f776fee8f6)

**Figure 1** | *Jupyter Notebook output of the articles from* Mars News *as a list of dictionaries, with the keys "title" and "preview"*

Further insight was provided by summary statistics, which can be found in **Table 1** below.

**_Please note that the author's findings use a slightly lower volume than the table in the starter code (2015 vs. 2021, respectively) because he eliminated NA values before tabulating._**

![image](https://github.com/aglantzrbc/sqlalchemy-challenge/assets/127694342/78cde0e3-5219-47ab-bc96-54eb704e481d)

**Table 1** | *Summary statistics of the volume of weather station precipitation observations in Hawaii USA between 8/23/2016 through 8/23/2017, with null values dropped*

The most active weather station out of the nine by volume of observations was identified: *WAIHEE 837.5, HI US Station ID USC00519281*, with 2772 observations. **Figure 2** is a 12-bin histogram showing temperature observations ("tobs") for this weather station over a year. The plot is unipolar with temperatures most frequently in the mid-70s (Fahrenheit).

![Tobs](https://github.com/aglantzrbc/sqlalchemy-challenge/assets/127694342/5c11f138-43c1-4c81-9fa0-b64a2a687561)

**Figure 2** | *Histogram of temperature observations (tobs) from weather station ID USC0051928 between 8/23/2016 through 8/23/2017, with temperature in Fahrenheit*

- [Task: Scrape and Analyze Mars Weather Data](https://courses.bootcampspot.com/courses/3337/assignments/54002?module_item_id=961399)

**FILE:** part_2_mars_weather.ipynb

**_All the route links to follow assume the user runs the sqlalchemy-challenge_app.py code and employs an open port for Flask output._**

The flask library was employed to create an application object, which was then decorated to make [API routes](http://localhost:5000/).

**_Though establishing the "Measurement" and "Station" variable names in all lower case (i.e., "measurement" and "station") is ideal, the author didn't do this for the following reasons:_**

1. Keeping the "Station" variable upper-lower case prevents confusion with the function "station" and the attribute "Station.station", which occur toward the end of the Python code.
2. Keeping the "Measurement" variable upper-lower maintains consistency with the concurrent "Station" variable, described above.
3. It should be noted that the "Base" variable assigned with "automap_base()" was also kept in upper-lower case, because this is what the SQLAlchemy automap function expects.

The following **static API** routes were created besides the [welcome ("/") route](http://localhost:5000/).

- [Precipitation route](http://localhost:5000/api/v1.0/precipitation)

*This provides a JSON list of the last 12 months worth of precipitation data, using the date and precipitation volume keys.*

- [Stations route](http://localhost:5000/api/v1.0/stations)

*This provides a JSON list of the nine weather stations with sequence ID and station ID keys.*

- [Tobs route](http://localhost:5000/api/v1.0/tobs)

*This provides a JSON list of the last 12 months worth of temperature observations (tobs) data from the most active station, using the tobs value and date keys.*

A **dynamic API** route was also set up.

- Start-End route

*This is set up with the decoration "/api/v1.0/**[start]**/**[end]**", where [start] and [end] are to be replaced with start and end dates using the format: **YYYY-mm-dd**/**YYYY-mm-dd**.* Example using the author's default port: http://localhost:5000/api/v1.0/2016-08-23/2017-08-23. Date ranges outside the scope of actual dates occurring in the dataset will default to the earliest and latest dates in the data.
*If only one date is provided, the output will calculate from that date through the latest record in the dataset.*

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


