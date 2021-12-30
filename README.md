# Web Scraping Job Postings from Indeed

[Indeed](https://indeed.com) is a website that helps connect employers and job seekers through job postings, company reviews, salary data, and more. Because the Indeed site is full of relevant data, organizations can extract job data from the Indeed API for analysis. Web scraping, which is the automatic extraction of data from a webpage, is the best tool for extracting data from Indeed quickly, cheaply, and securely. Through scraping Indeed, an organization can establish a competitive salary, gain understanding of employee sentiment and values, find great candidates, and build a realistic budget for hiring employees and outside contractors. Once extracted, the Scraping Robot API helps you export the data directly into your preferred analysis program. With useful job data and web scraping tools, your organization can make smart, data-driven choices for the future.

## Proposed Solution
I wanted to explore data science-related jobs posted to a variety of cities on indeed.com, a job aggregator that updates multiple times daily. I conducted my scraping using the “requests” and “BeautifulSoup” libraries in python to gather and parse information from indeed’s pages, before using the “pandas” library to assemble my data into a dataframe for further cleaning and analysis.

## Tools

*	Time Library
*	Pandas Library
* 	tqdm Library
*	Requests Library
*	BeautifulSoup Library
* 	Google Colab

## Examining the URL and Page structure

First, let’s look at a sample page from indeed.
Notice a few things about the way the URL is structured:

* “q=” begins the string for the “what” field on the page, separating search terms with “+” 
	
	- i.e. searching for "data+scientist" jobs
* When specifying salary, it will parse by commas in the salary figure, so the beginning of the salary will be preceded by %24 and then the number before the first comma, it will then be broken by %2C and continue with the rest of the number
	
	- i.e. "%2420%2C000" = $20,000
* “&l=” begins the string for city of interest, separating search terms with “+” if city is more than one word
	
	- i.e. "New+York"
* “&start=” notes the search result where you want to begin
	
	- i.e., start by looking at the 10th result

## Scraper Components

* Scrapping locations

	- Banha, cairo, Maadi ,Nasr City, Giza, Toukh, and Qalyub
* Scrappng job postions

	- Python developer, Data scientist, Data analyst, Data entry, Data engineer, and Database.

## Srapped features 
* Job Title
* Compony Location
* Compny Name
* Post date
* Job Summary
	
	Unfortunately, the entirety of the job summaries are not included in the HTML from a given indeed page, however, we can get some information about each job from what’s provided. Selenium is a suite of tools that could allow a web scraper to click through different links on a page to withdraw this information from the full job postings. However, I did not utilize selenium for this particular effort.
* Qualification Link
	
	This link take you to the job page.

## More Resources

* Running the project on [Colab](https://colab.research.google.com/drive/1-OEL5bNthtU2aNhiLYhf-jf6LyZV-x5P?usp=sharing)
* For Analysis of Web Scraped Job Data to Predict Relative Salaries visit [medium](https://medium.com/@msalmon00/analysis-of-web-scraped-job-data-to-predict-relative-salaries-c7237954184a)

