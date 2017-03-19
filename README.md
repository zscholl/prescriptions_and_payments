# Prescriptions and Payments Data Analysis

This repository is a collection of Jupyter notebooks used during
data analysis of a relationship between the payments drug manufactuers
make to providers and the rates at which those providers prescribe their drugs.

Two random forests were trained, one with only information about the specialty
of the provider and the name of the drug, and the second was trained with information
on payments those providers recieved from drug and device manufacturers.

The latter model had a 7.5% decrease in the median error rate on test data, 
indicating that some predictive power was gained with the payment data.

See the final report pdf in this repository for additional details.


## Layout

This repository has an iPython notebook in the top-level directory that
contains general analysis and code from the project. There are three
other directories that each contain notebooks that were used for 
prediction, data wrangling, and exploration.


### Note

The code for this project is fragmented because the analysis was
fragmented. Each of the two main data files, the payments and 
the prescriptions, when processed in a Jupyter notebook consumed
close to 16GB of memory, making it difficult to analyze both
at the same time on common consumer hardware.

The random forest trained on data containing payment information
and the data wrangling of data with payment information were
performed on an AWS EC2 r4.16xlarge instance. The wrangling
took up more than 430GB of RAM during processing and with
63 in use cores the training took over 7 hours.

### Data Sources
[Payments](https://openpaymentsdata.cms.gov/)
[Prescription](https://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/Medicare-Provider-Charge-Data/PartD2014.html)
[NPPES](https://npiregistry.cms.hhs.gov)
