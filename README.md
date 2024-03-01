# cherry_blossom_prediction_2024


#Bird sighting data

Data was obtained by request through eBird.org, an online database of publically recorded bird observations.
However, data files were too large (combined size of 11.5 GB) to upload directly to GitHub.



#Instructions to obtain datasets

Must create an eBird account to make a request.
Datasets will be emailed if approved.

Datasets requested via eBird's Custom Download page:
https://ebird.org/data/download/ebd


Separate requests were made for each region using search:

#washingtondc: District of Columbia, United States (US)

#liestal: Basel-Landschaft, Switzerland (CH)

#kyoto: Kyoto, Japan (JP)

#vancouver: British Columbia, Canada (CA)

#newyorkcity: New York, New York, United States (US)

Date range: December 1, 1999 to February 16, 2024
All species were used.


#Managing datasets

After receiving the emails for each location, there will be a download link for a zip file. In the zip you'll find your requested dataset in .txt format, as well as the eBird data Terms of Use, a metadata document describing the data fields in your file, and a list of Important Bird Area codes and site names. Additional files could include unvetted data, if you requested those data with your download.


The file name for the data containing bird counts begins with 'ebd' followed by the region code.
Note that the sampling data is also titled similarly, so make sure to use the .txt file ending in 'smp_relJan-2024.txt'.
Another way to differentiate the files is by looking at the file size; the file with counts should be larger.


Example using Liestal data:


#Data containing counts: 'ebd_CH-BL_199912_202403_smp_relJan-2024.txt'


#Sampling data: 'ebd_CH-BL_199912_202403_smp_relJan-2024_sampling.txt'

After identifying the proper datasets, create a folder in your R project titled 'eBird'.
Copy the data containing counts into the 'eBird' folder.

The datasets were renamed according to their region codes to make reading easier:


#washingtondc: 'US_DC.txt'


#liestal: Basel-Landschaft, 'CH_BL.txt'


#kyoto: 'JP.txt'


#vancouver: 'CA_BC.txt'


#newyorkcity: 'US_NY.txt'




Now the data is ready for use!




Additional Notes


All of the eBird datasets are very large, so they cannot be viewed in R, nor can they be converted to CSV. Additionally, they may take a few minutes to read.


eBird does not have specific data for Liestal, and Basel-Landschaft was used instead since that is the canton (or "state") that Liestal resides in. Additionally, the county in which observations were recorded were not specified, so the entire region was used to represent Liestal.


While eBird does have data for the city of Kyoto, the data obtained using the search 'Kyoto, Japan (JP)' gives observations for Kyoto Prefecture (or "state"). I did not know there was a difference, so a filter by "COUNTY" was conducted in the R code to specify Kyoto city. If you would like to skip this step for your replication, you can instead use the search 'Kyoto, Kyoto, Japan (JP)' when making the eBird request; however, this would require editing the R code.


Similar to Liestal, there is no specified data for Vancouver that I know of in eBird, so the dataset for the entirety of British Columbia was downloaded. I mention this because this is an extremely large dataset (over 6 million rows) and may take around 30 minutes to read into R. To specify to Vancouver, I also used a "COUNTY" filter for "Metro Vancouver", as mention in the block comments of the code.






