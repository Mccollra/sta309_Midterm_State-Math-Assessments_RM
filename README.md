# sta309_Midterm_State-Math-Assessments_RM
This is a dashboard focusing on economic disparities across children who have taken their state mathematics exam, specifically in Ohio

NOTE: You may need to install the "cowplot" package before running this code
    Code if you need it: install.packages("cowplot")

GOAL
I had no idea what I wanted to do with this data set, provided by the US Department of Education on 2020-2021 state math test achievement scores, until I saw what some of the categories represented. The first one that jumped out at me was "ECD" which meant "Economically Disadvantaged". I am not sure what exactly determines how a school district, state, or the US Department of Education labels a student as "Economically Disadvantaged" but I wanted to give it a shot. So I attempted to create a dashboard that explains how a childs economic upbringing might affect their state math test. 


PLAN
So, I got started with a chloropleth of the United States (well, 48 of them, sorry Alaska and Hawaii) and I filled each state on a spectrum of 0 to 1, based on the proportion of students they had that were labeled ECD. This took a lot of data wrangling, but eventually I was able to get each school district that had an ECD category and divide the number of ECD valid entries in each state by the states total number of valid math test entries. 

Next, I made a cholorpleth with the exact same scale and image, except this time for only the state of Ohio and its counties. This was easy after already making a US map. I followed it up with a boxplot, where I gave each of 300 some Ohio school districts (the ones that had an ECD category) a label of "Majority Economically Advantaged" or "Majority Economically Disadvantaged". Basically, if a schools proportion of ECD entries to all entries was over 0.50, it was labeled in the disadvantaged category. Making a box plot of these 2 groups next to each other shows what seems to be quite a large difference in the percentage of students that score at or above proficiency on the state math test or "PCTPROF". I decided to also include a boxplot including every Ohio districts PCTPROF so that there was a reference to what Ohio's general proficiency rate is. 

Lastly, I created a scatterplot with all Ohio school districts that had a valid ECD proportion or "PCT_ECD", and graphed the relationship between a schools "PCT_ECD" and its "PCTPROF". I also fitted multiple models to show the relationship between the two variables, and plotted the one I thought fit the data the best on the scatterplot. Lastly, to add some more dynamics and possible comparissons, I made the size of each point representative to that school districts total number of valid entries, and I gave each district a color based on the region of Ohio the county they are located in is in (Northeast, Northwest, Southeast, Southwest, Central) and also made a small cholorpleth next to the scatterplot that highlights the 5 different regions. 

For fun, I changed the color of Three Rivers Local School Districts dot to a yellow (Go Yellow Jackets!) to highlight the school I attended from kindergarten through 12th grade. 

Then, I made the dashboard that you can find in the png file labeled "sta309_Midterm-Dashboard.png"



CHALLENGES
There are a lot of wonky parts to this data set - probably because every state has different legislation, tests, school district designs, etc - which made this a very tough challenge at points. For example, for whatever reason, Illinois does not seem to separate its students into categories such as "Children With Disibilities", "Hispanic Children" or "Foster Children" like the other 48 contiguous states, because their number of valid entries in every category except "Male" and "Female" is the exact same as their total number of entries. This gave Illionois a rate of valid test entries by students with economic disadvantages of 100%. 2 other states are worth noting as well, Washignton, which did not have any data in the data set, and Oregon, who had about a 98% rate of entries by students with economic disadvantages. This was weird, because in Illinois case I was able to look at the data set and determine that Illinois didn't seem to categorize their children, but in the case of Oregon, many school districts did not have the exact same number of total and ECD valid entries. Another problem that emerged later in my work was the realization that not every school had a catergoy of ECD for their students. In Ohio, only aorund half of the school districts seemed to have an ECD category, which meant that I had to drop aaround half of the school districts because there was no way to get a valid ECD percentage. 
