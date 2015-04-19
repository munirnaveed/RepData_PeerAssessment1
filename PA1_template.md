# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

```r
oloadData=read.csv("D:/Reproducible Research/repdata-data-activity/activity.csv")
loadData<-oloadData[complete.cases(oloadData),]
cleanData<-transform(loadData, date=as.Date(date))
```
## What is mean total number of steps taken per day?
![](PA1_template_files/figure-html/unnamed-chunk-2-1.png) 

```
## [1] 10766.19
```

```
## [1] 10765
```

## What is the average daily activity pattern?



```r
intervals<-unique(loadData[, "interval"])
stepsperinterval<-c(1:length(intervals))

for(i in 1: length(intervals))
{
   
   
   intervalData<-cleanData[cleanData$interval==intervals[i], "steps"]
   
   avgsteps<-mean(intervalData)
   
   stepsperinterval[i]<-avgsteps
}
```
![](PA1_template_files/figure-html/unnamed-chunk-4-1.png) 



## Imputing missing values


![](PA1_template_files/figure-html/scatterplot-1.png) 

```
## [1] 10766.19
```

```
## [1] 10765
```

## Are there differences in activity patterns between weekdays and weekends?
![](PA1_template_files/figure-html/unnamed-chunk-5-1.png) 
