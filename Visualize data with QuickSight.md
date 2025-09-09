<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Visualize data with QuickSight

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-analytics-quicksight)

**Author:** Lutendo Matshidze  
**Email:** lupreshie@gmail.com

---

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-analytics-quicksight_6c7f7ef0)

---

## Introducing Today's Project!

In this project, I will demonstrate how to use Amazon QuickSight to analyze Netflix data and generate visualizations and insights. I'm doing this project to learn how to use cloud data services for data analysis.

### Tools and concepts

Services I used were QuickSight and S3. Key concepts I learnt include the manifest.json files, data visualization techniques (e.g charts, filters and how to performa data refresh).

### Project reflection

This project took me approximately 2 hours including demo time. The most challenging part was signing up for Quicksight because of region selection and understanding how a manifest.json file works . It was most rewarding to generating the pdf of my finished visualization.

After this project, I plan to work on Day 3 of the AWS beginners challenge. I will start this project on tomorrow.

---

## Upload project files into S3

S3 is used in this project to store two files, which are manifest.json, which tells Quicksight about the structure and format of the data we are analyzing and netflix_titles.csv, which is the raw data we are analyzing.

I edited the manifest.json file by updating the S3 URL that corresponds to our datasets file location. It’s important to edit this file because it's how Quicksight will find and analyze the data . If I didn't update this file, Quicksight would not know the location of the datasets. This will cause errors.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-analytics-quicksight_3c3cd85a)

---

## Create QuickSight account

Creating a QuickSight account cost $0 as I signed up for the 30-day free trial. Make sure you uncheck an add-on in the sign-up section called "Add Pixel-Perfect Reports" so you don't get charged.

Creating an account took me about 5 minutes including setting up our S3 buckets sections.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-analytics-quicksight_f4ab4214)

---

## Download the Dataset

I connected the S3 bucket to QuickSight by visiting the Datasets page. There were so many options for data sources I could connect to (databases and external tools/platforms like Salesforce), and I selected Amazon S3.

The manifest.json file was important in this step because it tells QuickSight how to read the data - in this case, it tells QuickSight that we are uploading a CSV file (spreadsheet) and the delimeter (i.e. commas) so that QuickSight knows how to break up the data for analysis. Otherwise, QuickSight might get confused!

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-analytics-quicksight_6f874996)

---

## My first visualization

To create visualizations on QuickSight, I simply have to click on data fields/labels i.e release_year and QuickSight will automatically generate a graphic that best suites that type of data. You can also drag data labels into sections like 'Group by' or 'y-axis' to determine how our graphic should treat the data.

The chart/graph shown here is a breakdown of the release years of the content inside Netflix i.e How many TV/shows/movies were released on xyz year. You can see that there is a total of 8800+ content pieces, and 2019 is the year with the most amount of content released.

I created this graph by clicking the 'release_year' data label and changing the automatically generated chart from a bar chart to donut chart.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-analytics-quicksight_aff3aad7)

---

## Using filters

Filters are useful for narrowing down our data to the subset that everyone want to focus on and in this case we could use our filters to focus on specific categories that we want to analyze. We also used filters to look at content with the released year from 2015 and beyond.

This visualization is a breakdown of TV shows and movies that belong on one of three categories i.e Action & Adventure, TV Comedies and Thrillers. Here I added a filter based on the "listed_on" data label i.e only thhese three categories could pass the filter.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-analytics-quicksight_c32248c5)

---

## Setting up a dashboard

As a finishing touch, I updated the titles of the charts in our dashboard so that they are easily readable. The default name would simply mention the data labels e.g released_year but the new titles communicate the purpose of the chart clearly.

Did you know you could export your dashboard as PDFs too? I did this by selecting PUBLISH and then GENERATE PDF on the top right hand corner of our website analysis.

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-analytics-quicksight_6c7f7ef0)

---

## Refreshing source data

In this project's extension, I downloaded fresh data that's different from my original dataset because it had rows and rows of empty country data. Analysing incomplete data brings the risk of generating inaccurate insights which leads to the wrong business decisions which costs the company time ,effort and money.

Once I downloaded new data, I had to update my S3 bucket because it is still storing the previous version of the data (i.e the ones with the countries missing). I also uploaded a new manifest.json file that points to our updated dataset's name. Just make sure that Quicksight is now pulling the latest version of data.

I initally couldn't see my updated data in QuickSight, so I had to visit the dataset in the dataset's page and performa full refresh of our data...

![Image](http://learn.nextwork.org/charmed_beige_timid_seahorse/uploads/aws-analytics-quicksight_86415f4e3)

---

---
