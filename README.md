# ResTest

Use the following API to retrieve sports results and sort into a table of results that are displayed
in the CLI. Each sport result contains several data and always includes the publication time.

Method: POST
Content-Type: application/json
Url: https://restest.free.beeceptor.com/results

Tasks:
- 1. Create python script that displays the sports results in reverse chronological order in the
CLI.
- 2. Add an argument to the script to display only certain types or events (e.g. f1Results)
- 3. Add an argument to set the locale (e.g. en)
- 4. How can you confirm the code works?
- 5. Bonus: Implement the rest call asynchronously
 
**Please refer fetchSportsResults.py for Task 1,2,3,5
Please refer below for Task 4**

**How can you confirm the code works?**
By executing the script.

Prerequisites
Python Installation: Ensure Python 3.12 is installed.

Dependencies Installation: 
pip install requests aiohttp python-dateutil fuzzywuzzy colorama

Execute the Script: 
  For Default locale:
  python fetchSportsResults.py
  
  For with locale:
  python fetchSportsResults.py --locale en_US.UTF-8
  
  #After script execution, user is displayed with available categories. User can choose the displayed categories(for only category related sorted result) or simply press enter(for sorted results of all categories).


**Additional Question**

**1. List the dependencies and reasoning for using them.**

   argparse : argparse is used for parsing command-line arguments. It allows the script to accept arguments from command line (--locale) and process them accordingly and helps configure the script's behavior based on user inputs.
    
   datetime : datetime provides classes for manipulating dates and times in Python. This ensures that dates are correctly displayed and sorted according to the specified locale.
   
   locale : locale is used in the script to set and retrieve locale-specific formatting for dates. This allows the script to display dates according to the user's locale preferences (--locale argument).
   
   asyncio : asyncio is used for writing asynchronous code using coroutines. It's used for fetching sports results asynchronously (fetch_sports_results_async function). This can improve performance by allowing concurrent execution of network requests without blocking the main thread.
   
   aiohttp : aiohttp is an asynchronous HTTP client/server framework for asyncio. It's used along with asyncio to make asynchronous HTTP requests (fetch_sports_results_async function). This allows the script to perform non-blocking HTTP requests.
   
  dateutil : dateutil is used for parsing a date formats making it easier to handle varied date formats.
  
  fuzzywuzzy: This library provides tools for fuzzy string matching. It's used in the prompt_user_for_category function to help users find the closest match to their input category. This is useful when users may not enter the exact category name but something close enough or when they make mistakes
  
  colorama: It prints colored text in the console, making it easier to highlight important messages or differentiate sections of output.
  
  time : It provides various time-related functions. In my script, it's used to measure and log the time for certain operations.
  
  logging : logging module is used to record log messages. 


**2. List the code not directly implemented for the project (Would be great as a comment in the project as well). This could also apply to code snippets you wrote but use in your personal projects.**
   Please refer to the script
   
**3. What portion of the code do you feel is most important for us to review more closely?**
  
   Fetching sports result
   
   Prompting User for Category with Fuzzy Search
   
   Sorting Results by Publication Date
   
   Displaying Results in CLI

**4. If you were to continue to develop the project, what are things you would add, change, or improve?**


   1. Implement Caching: Use an in-memory cache like Redis or a local cache mechanism to store the fetched results temporarily, reducing the need for frequent API calls and to improve performance.
   
   2. Input Validation: Validate user inputs more rigorously to prevent potential security issues or crashes.
   
   3. Filtering: Add more filtering options, allowing users to filter results by additional criteria such as date ranges, specific keywords.
   
   4. Data Processing: Improve the efficiency of data processing functions, especially if dealing with large datasets
   
**5. Anything else you want us to know while we review your project?**
   Design Decisions and Improvements:
   
   Async vs Sync: I would prefer to implement Sync Rest call since there is only one and I need to wait for the response to perform the operations. However I have implemented Async Rest call in the script thinking you might want to know my knowledge on implementing one. But in this scenario, I would prefer Sync.
   
   Fuzzy Matching for User Input: I have implemented this for category selection to enhance the user experience by allowing approximate matches.
   
   Command-Line Interface (CLI) Enhancements: I have used colorama to improve the CLI output with colors and better formatting. This makes the output more readable and visually appealing.


  
