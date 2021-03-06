# BigDataAssignments
##Hour of Day trips
Find number of trips based on hour of the day.

###### Scripts to find Hour of Day
*Get Hour from startTime field*

`> hourOfDay<-format(as.POSIXct(dtrips$starttime) ,format = "%H")`

*do group using table command*

`> groupByHour<-table(hourOfDay)`

###### Command
`> barplot((groupByHour), beside = TRUE, col = c("green", "black"),main="Hour of Day",ylab="Freq")`
 
![alt tag](https://github.com/JBaba/BigDataAssignments/blob/master/images/HourOfDay.png) 
 
## Day Of Week
Number Of trips for day of week.

###### Script
*Get Day name form date*

`> dayOfWeek<-(weekdays(as.Date(dateOfTrip,'%d-%m-%Y')))`

*Use data frame to convert vector*  

`> d<-data.frame(dayOfWeek)`

*Provide Order*

`> d$dayOfWeek<-factor(d$dayOfWeek,levels=c("Sunday", "Monday","Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"))`

*Create Group By variable*

`> groupByDayOfWeek<-table(d[order(d$dayOfWeek),])`

###### Command
`> barplot(groupByDayOfWeek,main="Day Of Week",ylab="Freq")`

![alt tag](https://github.com/JBaba/BigDataAssignments/blob/master/images/DayOfWeek.png) 
 
## Top Station trips
Find Stations who had highest and lowest number of trips.

## Scripts To Find Top 5 City
*Get Grouped values for all stations.*

`> groupByStation←table(dtrips$to_station_name)`

*Preapre Descending Order Vector* 

`> orderByFreqDesc=order(-groupByStation)`

*Apply Desc Order Function to our Stations.*

`> View(groupByStation[orderByFreqDesc])`

`> top5City <- c(groupByStation[orderByFreq][1:5])`

###### Command
`> barplot(top5City,main="Top 5 City Trips",ylab="Freq",ylim=c(0,20000))`

![alt tag](https://github.com/JBaba/BigDataAssignments/blob/master/images/Top5Station.png) 

## Scripts To Find Bottom 5 City

*Get Grouped values for all stations.*

`> groupByStation←table(dtrips$to_station_name)`

*Make Order Vector*

`> orderByFreq=order(groupByStation)`	
	
*Apply Order Function to our Stations.*

`> View(groupByStation[orderByFreq])`	

`> bottom5City <- c(groupByStation[orderByFreq][1:5])`

###### Command
`> barplot(bottom5City,main="Bottom 5 City Trips",ylab="Freq",ylim=c(0,100))`

![alt tag](https://github.com/JBaba/BigDataAssignments/blob/master/images/Bottom5Stations.png) 

## Trips Per Station
*Graph shows number of trips per stations.*
######Command
`> barplot(table(dtrips$to_station_name),ylab="Frequency",main="Frequency Per Station",xla="Station Name",ylim=c(0,20000))`

![alt tag](https://github.com/JBaba/BigDataAssignments/blob/master/images/FreqPerStation.png) 

## User Type Graph
*Graph shows Roughly equal number of Customer and Subscribers.*
###### Command
`> barplot(table(dtrips$usertype),ylab="Frequency",main="Types Of User",xla="UserType",ylim=c(0,500000))`

![alt tag](https://github.com/JBaba/BigDataAssignments/blob/master/images/TypesOfUser.png) 

## Gender Graph
*Almost half of the user do not provide their Gender information.*
###### Command
`> barplot(table(dtrips$gender),ylab="Frequency",main="Gender Of People",xla="Gender",ylim=c(0,500000))`
 
 ![alt tag](https://github.com/JBaba/BigDataAssignments/blob/master/images/Gender.png) 
 
##Month
Number of trips in Month

###### Script
`> month <- format(as.POSIXct(dtrips$starttime) ,format = "%m")`

`> View(month)`

`> groupByMonth<-table(month)`

###### Command
`> barplot(groupByMonth,main="Month Trips",ylab="Freq")`

![alt tag](https://github.com/JBaba/BigDataAssignments/blob/master/images/MonthTrips.png) 

##Month & Seasons:
From Graph We can say that Most number of trips in Fall.

###### Script:
*Find Month*

`> dtrips$month<-months(as.Date(dtrips$starttime))`

*Find Season*

`> dtirps$season[dtrips$month=="January"] <- "Winter"`

`> dtrips$season[dtrips$month=="February"] <- "Winter"`

`> dtrips$season[dtrips$month=="March"] <- "Spring"`

`> dtrips$season[dtrips$month=="April"] <- "Spring"`

`> dtrips$season[dtrips$month=="May"] <- "Spring"`

`> dtrips$season[dtrips$month=="June"] <- "Summer"`

`> dtrips$season[dtrips$month=="July"] <- "Summer"`

`> dtrips$season[dtrips$month=="August"] <- "Summer"`

`> dtrips$season[dtrips$month=="September"] <- "Fall"`

`> dtrips$season[dtrips$month=="October"] <- "Fall"`

`> dtrips$season[dtrips$month=="November"] <- "Fall"`

`> dtrips$season[dtrips$month=="December"] <- "Winter"`

###### Command:
`> barplot(table(dtrips$season), main="Season")`
 
 ![alt tag](https://github.com/JBaba/BigDataAssignments/blob/master/images/Season.png) 
 
#### Following Command is used to remove exponential Number Format  
`> options(scipen = 999)`

#### Extra Commands Used
`timeOfTrip <- format(as.POSIXct(dtrips$starttime) ,format = "%H:%M")`

`dateOfTrip <- as.Date(dtrips$starttime)`


