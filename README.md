# TwitterDataAnalysisVisualisation
This is a simple quick demo project to practice ```big data collection``` and ```visualisation```. It's a small practice to retrieve the followers of a target twitter account by a Python-based twitter API tool called [Tweepy](https://tweepy.readthedocs.io/en/latest/). Then visualise these social connections using a popular dynamic javascript called [d3js](https://d3js.org/).

To simplify the visualisation procedure (avoid local javascript setup), I used a publicly accessible platform called [observable](https://observablehq.com/) as a host for the visualisation results. Furthermore, the observable supports live codes, which you can edit your codes on the website and update the outcome visualisations. 

The simple demo visualisation can be found [here](https://observablehq.com/d/fcd695534e852304). Thanks for [Mike Bostock's demo](https://observablehq.com/@d3/force-directed-graph) and inspiration from [erikaris's post](http://erikaris.com/2018/08/21/using-d3-to-visualize-twitter-followers/). Feel free to fork and modify it with more eyes-catching d3js templates. Next, I'll demonstrate detailed steps on conducting this with a jupyter notebook provided.

## Retriving Twitter Account Followers using Tweepy
### Prerequisite
	- A twitter account to use API functions
	- Create your twitter APP to access it with token and keys, check [here](https://www.earthdatascience.org/courses/earth-analytics-python/using-apis-natural-language-processing-twitter/get-and-use-twitter-data-in-python/) for details.
	- Install Python (Tweepy package)[https://github.com/tweepy/tweepy]

### Using Tweepy API
	Since you've set things ready, you can use Tweepy API to:
	- Connect to your previously established twitter APP
	- Acquire the target account's followers' data
	- Save data into files for visualisation
	Please refer to the provided demo Jupyter Notebook for the sample codes and comments.


## Data Visualisation using d3js

### Find Desired d3js Template and Choose suitable Data Format
[Observable](https://observablehq.com/) provides various d3js template to visualise different types of data. It's recommended to make sure your visualisation aim and choose the right approach to explain your data by visualisation. 

Here, I use [Mike Bostock's demo](https://observablehq.com/@d3/force-directed-graph). Inside the d3js template, there is a line defining data source:
```data = d3.json("https://gist.githubusercontent.com/mbostock/4062045/raw/5916d145c8c048a6e3086915a6be464467391c62/miserables.json")```. It is actually the raw json file saved at [github gist](https://gist.github.com/). Therefore, you can use it to ```host``` your data file and pass the ```raw file link``` to replace the data source.

The motivation for this part is not only replacing data source but find the most effortless way to format your data acquired in the previous step and avoiding modifying the js codes. Therefore, the next step is direct to the original data file and adapt its format into our own data. 

The (original json file)[https://gist.githubusercontent.com/mbostock/4062045/raw/5916d145c8c048a6e3086915a6be464467391c62/miserables.json] uses simple dictionary-list format as: ```{[{}]}```. To be specific, a dictionary with keys: ```nodes``` and ```links```. Each of the two elements is a list with their child elements: ```node``` and ```link```. The ```node``` is interpreted as ```id``` and ```group``` while ```source```, ```target``` and ```value``` denote a ```link's``` start, end and weighted edge length respectively. 

### Formatting Data as Json 
The goal of this step is loading previously acquired source data and format it in the preferred way: {[{}]} json file. 
A Jupyter notebook will be updated (around 10 Oct 2019) to demenstrate the detailed process of transferring a sample csv file into the target json format.

### Plugin Formatted Data and Run
Paste your formatted data into the [gist](https://gist.github.com/) and generate an online source data. Then you can get the online address of the ```raw``` data. Replace the original data address with your freshly baked one. Click the ```run``` icon (right triangle) to update the visualisation and Eureka.