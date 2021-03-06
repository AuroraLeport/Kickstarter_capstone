# Springboard
# Kickstarter_capstone

INTRO: Kickstarter is an American public-benefit corporation, initiated in 2009, which has 
built a global crowdfunding platform focused on creativity. 
Kickstarter has reportedly received more than $1.9 billion in pledges from 9.4 million 
backers to fund 257,000 creative projects, such as films, music, stage shows, comics, 
journalism, video games, technology and food-related projects.

GOAL: Determine if a project will succeed or fail based on its given attributes. 
Success is defined as achieving the monetary goal needed, via backers, to launch its project 
in the time allotted by Kickstarter. Furthermore, I would like to
predict the percent likelihood of success or failure, based on a project's given attributes. 
The goal is to increase a new project's chance of success by recommending which attributes
their project should focus on. 

DATA: WeRobots (https://webrobots.io/kickstarter-datasets/) has crawled the 
Kickstarter.com website dumping all its data into multiple 100MB CSV files. Data has been 
periodically collected approximately once every month to two months since 2009. Each row in 
a CSV file represents a Kickstarter project, containing project attributes and outcome 
(success vs. fail).

As Kickstarter has had more project submissions during recent years, 2014 - 2016,
I have only analysed projects launched between these years in an attempt to avoid any 
confounds that time may place on my model. After filtering on the above criteria,

96,990 projects and corresponding attributes (~1000 MB) are analyzed in this project.

APPROACH: I have built a predictive model, using sklearn's logistic regression, 
determining the influence of the following attributes on a successful or failed outcome: 
    1. Blurb count - number of words used in the short description of the project
    2. Backer count - number of people who funded the project
    3. Goal in USD - amount of money needed to launch the project
    4. Project Category - Category the creative project falls into
    
Independent (X) variables: attributes (see above),
Dependent (y) variables: outcomes (i.e. success vs. fail)

In order to evaluate the success of my model, I used 10-fold cross-validation. Since the  
model performed well (90% accuracy), I used it to predict the probability of success vs. failure using 
live Kickstarter projects (i.e. projects whose outcome has not yet been determined). 
Once an outcome was determined for those projects, I then compared
my predicted outcome to the true outcome. Success rate of my model was determined by 
comparing the predicted outcome to the true outcome.

FINDINGS: My model predicted the outcome of 2700 Kickstarter projects with 83% accuracy. 
I have determined there to be a positive relationship between backer-count and rate of
success and a negative relationship between blurb count and success rate as well as
a negative relationship between monetary goal and success rate. 
The category of project does not influence the outcome much.

FUTURE RESEARCH: Future research should aim to understand the specific timeframe
that a particular amount of backers should be acquired to result in a successful outcome. 
Based on the trajectory of first week, can we predict final backer count?

3 concrete recommendations on how to use findings:

1. Client can use findings to modify their set goal amount.
2. Client can use findings to understand the number of backers they need to achieve
to be succesful.
3. Client can use findings to determine the number of words their blurb count should 
contain while still maintaining a successful outcome. 
