# Convent_Statis_Analysis
collect some analysis examples using R

# Song best-selling inference and marketing recommendations
Abstract: with the continuous improvement of China's residents' income level and quality of life, 
people put forward higher requirements for spiritual entertainment and other aspects.
There are many factors that influence whether a song is popular or not. 
In addition to the changes in the audience of today's consumer groups, 
the year of the song and some other characteristics of the song itself.
By using statistical methods to predict the playback times of a song, 
specific marketing and corresponding recommendations can be made for specific songs.

# I. introduction and description of data
The Dataset was collected from the Million Song Dataset, 
including the music playback times of 1019,
318 different users on Echo Nest and some basic information about the songs.
Set data source: https://labrosa.ee.columbia.edu/millionsong/.
This paper adopts the cleaned data set in the attachment, 
which contains the following variables:
As a result, we have become familiar with the Popularity of the SongID (SongID, Title: song name) 
and the album ID released on albumid7digital.com. 
ArtistName: album Duration (in seconds), 
key Signature: the tone of the song, 
Popularity of the songs, 
and Mode: the scale of the song is a 0-1 variable,
0 and 1 respectively represent the small scale and the major scale.
Tempo: music speed, song speed, 
Time Signature: the average number of beats per minute of a song,
Year:MusicBrainz song release Year, the missing data is recorded as 0, 
Count: music played by 1019318 different users in echo network.<p>
Qualitative variable: key Signature, mode, year<p>
Quantitative variables: Duration, Energy, Popularity, Loudness, Tempo, Time Sginature, Count<p>
The research mainly includes the following two questions:<p>
(1) explore the influence of different modes on songs.
The data set is used to explore whether there is a difference between small scale and major scale (0 and 1), 
and if so, what is the difference? Statistical modeling indicators include but are not limited to: 
Duration (Duration of the song), key Signature (tone), Energy (popularity of the song), Tempo (speed of the song) 
and Count (number of playback).<p>
(2) use the song information collected in the millions of song data sets to predict the Count of songs (number of playback)
through statistical modeling.<p>

# II. exploratory data analysis
Data cleaning: for the missing values in the data, the default value processing of the variables with default values
that have not been explained in the variable definition will be processed as the missing value removal case object.
After removing the default value, the sample size was reduced from 385256 to 309685.

Data visualization:

![avatar](https://github.com/kala-oro/Convent_Statis_Analysis/blob/master/Analysis%20of%20influential%20factors%20of%20song%20popularity/imag/scatter_plot.png?raw=true)

For the first part of the problem, we carried out difference analysis of each statistical variable under different Mode scales:

1. Levene test of homogeneity of variance:

|count	| Df	| F-value |	Pr(>F)	| energy | Df |	F-value |	Pr(>F)|
|- | :-: | :-: | :-: | :-: | :-: | :-: | :-|
|group|1|0.22|0.6383|group|1|105.6|0|
||309683||||309683|||

|duration	| Df	| F-value |	Pr(>F)	| loudness | Df |	F-value |	Pr(>F)|
|- | :-: | :-: | :-: | :-: | :-: | :-: | :-|
|group|1|234.22|0|group|1|13.26|0.0003|
||309683||||309683|||

|keySignature	| Df	| F-value |	Pr(>F)	| tempo | Df |	F-value |	Pr(>F)|
|- | :-: | :-: | :-: | :-: | :-: | :-: | :-|
|group|1|10.62|0.0011|group|1|1.99|0.1585|
||309683||||309683|||

|popularity	| Df	| F-value |	Pr(>F)	| timeSignature | Df |	F-value |	Pr(>F)|
|- | :-: | :-: | :-: | :-: | :-: | :-: | :-|
|group|1|61.65|0|group|1|106.56|0|
||309683||||309683|||

As can be seen, variables with homogeneity of variance include count, tempo;
Variables with uneven variance include energy, duration, loudness, keySignature, popularity and timeSignature.

Then, single-factor variance test was performed:

|count|F|num df|denom df|p_value|
|-:|:-:|:-:|:-:|:-|
||0.19|1.00|309683.00|0.66|

It can be seen that in the statistics, except that there is no significant difference in the count of songs of different mode scales, the other song properties (duration, keySignature, popularity, energy, loudness, tempo, timeSignature) are all significantly different.

What's the difference:

As for the statistical analysis values of duration, keySignature, popularity, energy, loudness, tempo, and timeSignature, we have grouped the data sets in accordance with different scales of mode.

When the scale mode was in small scale, the mean duration of duration songs was 257.68 seconds and the standard deviation was 116.09 seconds.The mean pitch and standard deviation of keySignature song are 6.27 and 3.55 respectively.Popularity artists had a mean score of 0.43 and a standard deviation of 0.10.Energy songs have a popularity of 0.47 and a standard deviation of 0.20;The loudness dness of the average sound track is -9.13 with a standard deviation of 4.76.Tempo songs have an average speed of 125.70, with a standard deviation of 35.15; timeSignature songs have an average number of beats per minute of 3.69, with a standard deviation of 1.15.

When the scale mode was in the major scale, the mean duration of duration songs was 241.79 seconds and the standard deviation was 109.44 seconds.The mean tone of keySignature song is 4.83, with a standard deviation of 3.51.Popularity artists had a mean score of 0.43 and a standard deviation of 0.10.The popularity of energy songs is 0.46 with a standard deviation of 0.21.The average loudness sound track is -9.28 with a standard deviation of 4.73.Tempo songs had an average speed of 125.16 and a standard deviation of 34.81;TimeSignature songs have an average of 3.62 beats per minute and a standard deviation of 1.18.

After visualization, it is shown as follows:

![avatar](https://github.com/kala-oro/Convent_Statis_Analysis/blob/master/Analysis%20of%20influential%20factors%20of%20song%20popularity/imag/barplot_swarp.png?raw=true)

As can be seen, the box graph of these variables is shown in the figure above, and some variables have more deviation values.
