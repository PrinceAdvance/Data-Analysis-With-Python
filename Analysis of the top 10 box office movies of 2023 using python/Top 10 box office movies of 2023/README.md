# Firt look at our data
1.First of all load the necessary libraries into the Jupiter notebook:
```Python
import pandas as pd
pd.plotting.register_matplotlib_converters()
import matplotlib.pyplot as plt
%matplotlib inline
import seaborn as sns
print("Setup Complete")
```
2. Then name the file path, like this:
```Python
movie_filepath = "/content/Movie project.xlsx"
```
3. We can load our data into a pandas data frame
```Python
movie_data = pd.read_excel(movie_filepath)
```
4. Since our data is not large we can proceed to check if everything was loaded correctly,
```Python
movie_data
```
5. Tadaa! we have all our loaded data:
```
| Rank | Release Group                               | Budget      | Worldwide   | Domestic   | %     | Foreign     | %.1   |
|------|---------------------------------------------|-------------|-------------|------------|-------|-------------|-------|
| 1    | Barbie                                      | 145000000   | 1445638421  | 636238421  | 0.440 | 809400000   | 0.560 |
| 2    | The Super Mario Bros. Movie                 | 100000000   | 1361956191  | 574934330  | 0.422 | 787021861   | 0.578 |
| 3    | Oppenheimer                                 | 100000000   | 957495070   | 328923070  | 0.344 | 628572000   | 0.656 |
| 4    | Guardians of the Galaxy Vol. 3              | 250000000   | 845555777   | 358995815  | 0.425 | 486559962   | 0.575 |
| 5    | Fast X                                      | 345000000   | 704875015   | 146126015  | 0.207 | 558749000   | 0.793 |
| 6    | Spider-Man: Across the Spider-Verse         | 100000000   | 690615475   | 381311319  | 0.552 | 309304156   | 0.448 |
| 7    | Wonka                                       | 125000000   | 588920684   | 206220684  | 0.350 | 382700000   | 0.650 |
| 8    | The Little Mermaid                          | 300000000   | 569626289   | 298172056  | 0.523 | 271454233   | 0.477 |
| 9    | Mission: Impossible - Dead Reckoning Part One | 290000000   | 567535383   | 172135383  | 0.303 | 395400000   | 0.697 |
| 10   | Elemental                                   | 200000000   | 496444308   | 154426697  | 0.311 | 342017611   | 0.689 |
```

# Exploratory Analysis

1. We can start our exploratory analysis by caling `.describe()` and we see the statistics of our data

2. We still need more information about our data,by calling `.info()` we find out the datatypes we have,null and non null values
```
| Column         | Non-Null Count  | Dtype   |
|----------------|------------------|---------|
| Rank           | 10 non-null      | int64   |
| Release Group  | 10 non-null      | object  |
| Budget         | 10 non-null      | int64   |
| Worldwide      | 10 non-null      | int64   |
| Domestic       | 10 non-null      | int64   |
| %              | 10 non-null      | float64 |
| Foreign        | 10 non-null      | int64   |
| %.1            | 10 non-null      | float64 |
```
Dtypes:
- float64(2), int64(5), object(1)
Memory Usage:
- 768.0+ bytes
#### Fortunately for us,our data is clean 

## What do we know about our data

1. We want to find out if the amount spent in production has an effect on revenue generated worldwide so, let's plot budget against revenue worldwide by using the code:
```Python
movie_data.plot(x="Release Group", y=["Worldwide", "Budget"], kind="bar")
plt.title("A chart showing the cost of production against worldwide box office for each movie")
```
![image](https://github.com/user-attachments/assets/441d42ed-4335-4ec8-9063-3b79979f36be)

2. Plotting a bar chart to show how movies fared worldwide and domestically
```Python
movie_data.plot(x="Release Group", y=["Domestic", "Foreign"], kind="bar")
```
![image](https://github.com/user-attachments/assets/6a3af23d-6aca-447a-9e36-099f79fc960f)





















