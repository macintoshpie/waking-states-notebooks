# Waking States Study Analysis Notebooks
These are some notebooks I wrote to assist in data processing and merging for a study at the [Furman Sleep Lab](http://www.furmansleeplab.com/). They are part of a much larger data processing pipeline I designed, so there's some missing bits.  

Descriptions of Notebooks:  
## Twin Event Processing
Takes a microsoft word doc containing event triggers, exported from our EEG recording software, and checks the sequence of events, corrects the events if necessary, calculates the inter event intervals (for data quality checking), and calculates the latency in milliseconds for use in our EEG analysis software, BrainVision Analyzer.  
## Pupil and SART Processing
Processes a file containing eye tracking data as well SART (an attention task) data. Looking at the velocity profile, pupil size samples are marked as good or bad - bad samples are removed and interpolated. The script then compares the quality of the right and left eye recordings and decides which to use and then zscores the data. The pupil data is transformed into trials, where the baseline pupil size (the pupil size right before a stimulus trial) is calculated. After all of the processing, the end result is a file that contains analyses of pupil size during a trial, the response time of the participant, the type of stimulus presented, as well as a few other things.  
## EEG Processing  
Once the EEG data has gone through artifact rejection, and all of the processing is applied to the trials, the result is a collection of files with frequency band information for each trial as well as another file which indicates whether or not the trial was marked as artifact/usable. This script merges this data into a single dataset.  
## Final Merger  
