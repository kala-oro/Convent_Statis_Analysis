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

![avatar](http://github.com/kala-oro/Convent_Statis_Analysis/Analysis of influential factors of song popularity/imag/scatter_plot.png)
