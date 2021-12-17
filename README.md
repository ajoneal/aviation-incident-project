# Aviation Project

---

### Overview and Objectives

**Problem Statement**

The National Transportation Safety Board (NTSB) has collected data on aviation accidents since 1962. Though this information has long helped to guide safety protocols and regulations, the data remains underutilized in the prevention of future incidents. This is made evident by the insufficient and inconsistent decline in the number of general aviation fatalities in the first two decades of the 21st century. A shift in approach to data collection and analysis is necessary for ensuring greater safety for all those who fly.

**Guiding Question:**

What human, environmental, and engineered factors most influence the likelihood of fatalities or injuries during in-flight incidents?

**Executive Summary**

The featured project focused on the development and integration of advanced data science methods while identifying solutions of immediate social impact. We identified safety issues within the aviation industry as being of particular concern. Utilizing Natural Language Processing (NLP), Geographic Analysis, and Neural Networks, the team was able to isolate key attributes of general aviation accidents and their catalysts.

**Order of Notebooks**
1. *Json Data.ipynb* - scraping the data and saving into the dataset folder
2. *dataset folder* - all scraped data from NTSB site along with cleaned data
3. *Cleaning, Preprocessing, and EDA.ipynb* - cleaning of data, model preparation, and NLP EDA (cleaned dataframe saved to dataset folder)
4. *model folder* - contains the different models we used in attempt to predict whether an aviation incident would lead to a death or injury
5. *images folder* - contains all visualizations from EDA and modeling along with a Geomapping notebook that shows aviation incidents across the United States
6. *Aviation Incident Presentation.pdf* - stakeholder presentation of findings

---

### The Data

**The Data Problem**

The NTSB maintains a massive and continuous collection of aviation accident data. The depth and complexity presented in the information present both a challenge and opportunity in the ability for predictive models to promote industry-wide safety guidance.

**Selected Data for Analysis**

The data that guided the production of this analysis was produced by the National Transportation Safety Board (NTSB) and covers investigations between January 1, 2010, and January 1, 2021. [The NTSB aviation accident database](https://www.ntsb.gov/Pages/monthly.aspx) contains information from 1962 and later about civil aviation accidents and selected incidents within the United States, its territories and possessions, and in international waters.

**Data Cleaning**

Data Cleaning focuses on navigating raw data by addressing errors, missing values, and other inputs that challenge the professionalism, accuracy, and value of the following analysis.  The data collected by the NTSB had several issues and the cleaning process for this set of data was extensive.  After examining and cleaning much of this data, it became clear that the NTSB needs to come up with a better system for standardizing how they collect data to be able to better utilize the information they get.

**Data Dictionary**

|Feature|Type|Description|
|---|---|---|
|**has_safety_rec**|*bool*|Identifies incidents in which their results and investigations led to the development of industry-wide safety recommendations.|
|**probable_cause**|*object*|The synopsis contains information from the final report and includes the probable cause. Incidents with missing values are a result of NTSB not having primary investigation responsibility|
|**city**|*object*|Represents the location of the incident and/or the nearest city to which the event occured.|
|**country**|*object*|Represents the country/region where the event occured.|
|**date**|*object*|Time, Day, and Month when the incident was reported (UTC).|
|**state**|*object*|Represents the state/region where the event occured.|
|**event_type**|*object*|All investigations in the online aviation accident database are defined as either "Incident" and "Accident." An accident is defined as "an occurrence associated with the operation of an aircraft which takes place between the time any person boards the aircraft with the intention of flight and all such persons have disembarked, and in which any person suffers death or serious injury, or in which the aircraft receives substantial damage". An incident is defined as "an occurrence other than an accident, associated with the operation of an aircraft, which affects or could affect the safety of operations." The Safety Board investigates only selected incidents, including them in the database in the same form as accidents. Typically, incidents do not involve the level of injury or damage characteristic of an accident.|
|**airport_name**|*object*|Name of airport where plane departed from.|
|**analysis_narrative**|*object*|The synopsis contains information that guided the investigation and its findings.|
|**factual_narrative**|*object*|The synopsis contains information from the factual report..|
|**fatalities**|*float64*|Number of fatalities as result of the event.|
|**minor_injuries**|*float64*|Number of minor injuries as result of the event|
|**serious_injuries**|*float64*|Number of serious injuries as result of the event .|
|**flight_condition**|*object*|VMC stands for "visual meteorological conditions", while IMC is "instrument meteorological conditions". VMC conditions describe the weather conditions and situations in which a pilot can sufficiently and safely maintain visuals of all other aircraft and the terrain around them. IMC conditions describe a situation in which visibility and the weather require the pilot to rely on their instruments, and thus conduct an IFR flight.|
|**make**|*object*|Make of Airplane.|
|**model**|*object*|Model of Airplane.|
|**registration**|*object*|Registration number of aircraft. A leading "N" represents US-registered aircrafts.|
|**operator**|*object*|Operator of aircraft at time of event.|
|**owner**|*object*|Owner of aircraft involved.|
|**flight_operation**|*object*|Denotes the primary operation of the aircraft at time of event.|
|**sightseeing**|*object*|Identifies if flight was flow for sightseeing.|
|**second_pilot**|*object*|Identifies if aircraft had two pilots at time of event.|
|**death_and_injuries**|*object*|Total number of death and injuries as a result of the event|


**Exploratory Data Analysis**

Returning focus to the problem statement that guides the analysis, the featured EDA works to present and study a variety of statistical perspectives. The primary objective is to identify key trends/influences within the data that will serve both the predictive model and a meaningful solution.

During our EDA, we completed natural language processing on the probable cause, factual narrative, and the analysis narrative parts of each incidents.  We found even more errors in the data collection with 'x0d' (which is an escape character) showing up a lot in the data.  It was also very apparent that all incidents had on or a combination of human error, machine failure, or meteorological conditions that caused the accident.  However, when we narrowed it down to the incidents where there was a death or injury, we began to see more human error leading to the cause of the incident.

---

### Preprocessing and Modeling

After EDA, we completed the preprocessing & modeling of our data looking to discover trends for the incidents. Utilizing Neural Networks and a random forest model, we looked to predict whether or not an incident would lead to death or injury but had little success doing so.  This was due to the poor record collection by the NTSB.  After regularizing and trying multiple models that were only slightly better than our baseline scores, we came to the conclusion that the data was not sufficient enough to predict whether or not there would be an injury or death during an accident.

---

### Conclusions and Recommendations

Multiple conclusions were made after the project's analysis and modeling. First recognized is the need to immediately improve the quality of the data that is collected during investigations. In partnership with this is the broader recommendation that the NTSB maintains a stricter and more standardized approach to collecting and inputting data. Errors, missing values, and inconsistencies were abundant. As a result, attempts to understand and utilize this information was hindered, further challenging the ability to produce accurate and meaningful predictions. 

However, we were able to identify one key trend driving the majority of fatal aviation accidents. Human error among all other controls is was most often led to incidents possessing one or more casualties. In recognizing this, it is recommended that training and care of pilots face increase regulation and further research. 

---

### Presentation Link

[Aviation Incident Presentation](https://docs.google.com/presentation/d/1ObAkOawVFATINK1AxxU8l_YxlNvl8n9S/edit#slide=id.p8)