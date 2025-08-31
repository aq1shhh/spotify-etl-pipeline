\*\*\*COLAB

copy and run the python files with your spotify client and client secret which you will get by creating spotify developer account

and the credentials will be available in your profile, replace them in place of client id and client secret in the code

&nbsp;

RUN THE CODE\*\*\*



\*\*\*s3 IN AWS
Open AWS create s3 bucket titled spotify-etl-pipeline 
then click on the created link and create two folders raw\_data and transformed\_data

click on the raw data and create two more folders processed and to\_processed

revert and click on the transformed\_data and create three folders album\_data, artist\_data and song\_data


YOUR S3 job is complete\*\*\*\*





\*\*\*LAMBDA

then search for lambda and create four functions <spotify-api-data-extract> , <spotify-api-extract-function> , <spotify-transformation-function> , <spotify-transformation-load-function> , while creation choose runtime as latest python version 



open spotify-api-data-extract by clicking on it and scroll and replace the code with the spotify\_extractor.py file and add trigger that is eventbridge and schedule it for 1 minute , and add layer as spotipy.zip file which I uploaded.
then open spotify-transformation-load-function , and replace the lambda function code with lambda function.py and add layer as new pandass



process complete\*\*\*\*

\*\*\*IAM ROLE creation



search iam and create role , select aws account , then this account and select require external id and type 00000 for now , name the rule

anything you like , then add permission as s3fullaccess, 

then create role. The role gets created and copy the arn and paste it in notepad





\*\*SNOWFLAKE open in separate tab

create your worksheet and open and paste the code given in sql folder 

replace the  STORAGE\_AWS\_ROLE\_ARN in code with your arn which you copied in your notepad
 run the code till  DESC INTEGRATION spotify\_s3\_int;

&nbsp;and copy the property\_value of STORAGE\_AWS\_IAM\_USER\_ARN and replace it in iam role section in trust relationship.

run all your code
COMPLETED\*\*\*








