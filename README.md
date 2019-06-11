# FinalProject_stats418

This repo contains codes and summary for stats 418 final project. The goal is to predict how the box office for latest CMU movie, "The Avengers 4: Endgame", would perform from data webscrapped from The Numbers.com with all former MCU movies. 

The model developed takes "number of days passed" since May 26, 2019 as an input, and prints out a dataframe of daily gross and total gross from 05/26/2019 up until that day. 


# Deployment

To reproduce this API, first pull and download the files in this repository.

Open Terminal, navigate to the docker directory, **then run: `docker-compose up --build`**

Open a new terminal under the same directory and run the curl command: `curl http://localhost:5000/`
You should get a response: `server is up - nice job!`

To make a prediction of `box office` using `days`, run the following command as an example: 
`curl -H "Content-Type: application/json" -X POST -d '{"days":"1"}' "http://ec2-18-191-222-50.us-east-2.compute.amazonaws.com:5000/predict_endgame`

The return should be a data frame as      
`dgross            tgross`

`0 3868665.86566557  795931445.86566556`

`1 3249656.1819887   799181102.0476543` 

The predictor values can be changed and will result in different prediction returns.

**To stop your server running the API, type `ctrl-C`.** 
Check to see if you have any docker containers running using `docker container ls`, and stop them through `docker container kill <container-name>`.
