# Analysis-of-police-shootings-in-USA

The shootings in the USA have increased almost exponentially in recent years. The data that we collected has information about the shooting from the year 2015 until the latest week in all counties of the USA. The data collected from the dataset are geographical locations of shootings, armed status of the victim, flee status, weapon carried by the victim, name, place (county, state, city), date, race, etc. From the above-mentioned information, we planned on solving the answer to the questions as follows.
1) Aretherebodycamrecordingsoftheshootings?
2) Howmanyindividualswerecarryingalethalweapon?
3) Howmanyarmedpeopledidnotfleeduringthescene.Couldtheyhavepossiblybeendangerousto
the police? Could that be one among the factors that led to the shooting?
4) Whatarethetopmoststateswhereshootingiscommon?
5) Whatistheagegrouptheyfallunder?
6) Can the manner of death be predicted based on other variables? Does every variable influence the
prediction made by the model?

FINDINGS
1) It was found from the dataset that very few shootings had coverage from bodycam. Out of 1235 shootings from California (which stands first for most common states for shooting) 994 didn’t have body cam data. Likewise, the top 6 states with the most shootings are also the states that have the most shootings without body cam data.
2) Thenumberofarmedpeoplefromthedatasetwasfoundtobe7205.
3) Around4077peoplewhowerearmeddidnottrytofleebeforebeingshot.Thispossiblysuggeststhat
the police had a reason to shoot them, having realized that they were armed. But this does not entirely suggest that they were a threat to the police. Hence, the bodycam fitted onto police can be used to classify the people into harmful or not. This could justify the police’s shooting.
4) ThetopthreestatesforshootingsareCalifornia,Arizona,andColorado.Thiswasfoundbyperforming a few clustering algorithms along with the pattern. The pattern of shooting in these 3 states are unique to their own.
5) Victims were of a wide range of age groups starting from 15 with a maximum of 91. However, the victims who were shot in states of California, Arizona, and Colorado were found to be from age 24 until 50.
6) Yes,thevariables(age,race,gender,armedstatus,flee,threatandmentalillness)havebeenusedto predict the manner of death. Where gender, armed status, flee, threat and mental illness having higher absolute coefficient value contributed to the model’s prediction, age and race did not.
In conclusion, this analysis indicates that armed and non-fleeing suspects pose a greater perceived threat to police which may have been the most important factor for shooting but not race or age. This analysis and reason justify most of the shootings by police.


Appendix A: METHOD
Data Collection: The fatal police shooting data was collected from the Washington Post, which contained details about the person shot, his name, the place of the incident, race, armed status, flee-status, city, county, state, date, age, mental health status, body camera, gender, etc. This information about the victim is very helpful in understanding the pattern of the shooting.
The link to the website is given below: https://www.washingtonpost.com/graphics/investigations/police- shootings-database/
This data was then imported into the Jupyter notebook in Anaconda and used for further analysis.
Variable Creation:
1) Bodycamerasisavariablefromthedatasetaredeviceswornbypoliceofficerstorecordinteractions
and events from the officer's perspective.
2) Thelatitudeandlongitude(othertwovariables)informationfromthedatasetwasextensivelyusedto
understand the shootings in the states of the USA. Longitude and latitude are a pair of numbers (coordinates) used to describe a position on the plane of a geographic coordinate system to give the exact location where the shooting happened.
3) ‘flee_status’and‘armed_with’arethevariableswhichcontaininformationaboutpeoplewhoescaped the crime scene who possess weapons.
4) Apart from these, variables like race contains the race of the victim that was shot (Hispanic, Asian, Black, White, etc.).
Data Cleaning and Preprocessing:
The aim was to find the location where the maximum number of the population was armed. Hence, the following were dropped:
1) Duplicates
2) Nullvaluesfromspecificcolumnslikerace,gender,age,armedstatus,flee,threatandmentalillness.
3) Categorized the armed status column into binary and removed all the unarmed population from the
dataset, which was replaced as 1. The categories in the weapons like guns, vehicles, blunt objects, knives, and replicas were all considered armed and were replaced to 0. The rest of the unarmed and undetermined were all replaced by 1.
4) Removed all populations that fled from the scene that was present in the dataset which were in categories like car, foot, other, and Nan.
5) Nowthedatasetwasbroughtdownto4077rowsand19columnsfrom8796rows.

Analytical Methods:
1) K-meansclustering-Theoptimalvalueofkreducestheeffectofthenoiseontheclassificationhence
the elbow method was used to get the optimal number of clusters for clustering.
2) DBSCAN (Density-Based Spatial Clustering of Applications with Noise)- DBSCAN takes in only two variables, namely epsilon and the minimum number of samples. Epsilon represents the radius of the cluster, while the minimum number of points that can be under the radius area. The points and the background are represented as a plot using the Altair library. DBSCAN clustering was performed on the dataset to analyze the density of datapoints in particular regions of the states and understand the
patterns of the shootings.
3) LogisticRegression-LogisticRegressionisastatisticalmethodforbinaryclassification,whichmeans
it predicts the likelihood of an occurrence belonging to a specific category or class. These values are
typically coded as 0 and 1.
4) inourmodelclass0–shot,class1-shotandtasered.
