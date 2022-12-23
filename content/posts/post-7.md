---
title: "How to test dark mode?"
description: "Here is how you can setup dark mode for Ezhil and test on various OS like iOS, Android, macOS and Windows 10."
date: 2018-03-18T12:13:38+05:30
mermaid: true
---

You can set dark mode as default by setting `params.mode` to `dark` in `config.toml` or set it to `auto` which will detect based on your OS and switch to dark mode. For more details [refer documentation](https://github.com/vividvilla/ezhil#configuration)

Here is how you can switch based on your OS

* [iOS](https://www.howtogeek.com/440078/how-to-enable-dark-mode-on-your-iphone-and-ipad/)
* [Android](https://9to5google.com/2018/12/17/android-dark-mode-theme-pie/)
* [macOS](https://support.apple.com/en-in/HT208976)
* [Windows 10](https://www.cnet.com/how-to/turn-on-the-dark-mode-in-windows-10/)


{{< mermaid align="left" theme="neutral" >}}
flowchart TB
    y("You") --> s{Subscribed to navendu.me?}
    s --> |Yes| a("You are awesome!")
    s --> |No| su[/"Subscribe to navendu.me"/] --> a
    click su href "/subscribe" _blank
{{< /mermaid >}}


```py 
# Example of making predictions
from math import sqrt

# calculate the Euclidean distance between two vectors
def euclidean_distance(row1, row2):
	distance = 0.0
	for i in range(len(row1)-1):
		distance += (row1[i] - row2[i])**2
	return sqrt(distance)

# Locate the most similar neighbors
def get_neighbors(train, test_row, num_neighbors):
	distances = list()
	for train_row in train:
		dist = euclidean_distance(test_row, train_row)
		distances.append((train_row, dist))
	distances.sort(key=lambda tup: tup[1])
	neighbors = list()
	for i in range(num_neighbors):
		neighbors.append(distances[i][0])
	return neighbors

# Make a classification prediction with neighbors
def predict_classification(train, test_row, num_neighbors):
	neighbors = get_neighbors(train, test_row, num_neighbors)
	output_values = [row[-1] for row in neighbors]
	prediction = max(set(output_values), key=output_values.count)
	return prediction

# Test distance function
dataset = [[2.7810836,2.550537003,0],
	[1.465489372,2.362125076,0],
	[3.396561688,4.400293529,0],
	[1.38807019,1.850220317,0],
	[3.06407232,3.005305973,0],
	[7.627531214,2.759262235,1],
	[5.332441248,2.088626775,1],
	[6.922596716,1.77106367,1],
	[8.675418651,-0.242068655,1],
	[7.673756466,3.508563011,1]]
prediction = predict_classification(dataset, dataset[0], 3)
print('Expected %d, Got %d.' % (dataset[0][-1], prediction))


```


SQL 

---- 

```SQL
CREATE TABLE time
(
time_code     INT,
order_date    DATE,
month_code    SMALLINT,
month_name    CHAR(10),
quarter_code  SMALLINT,
quarter_name  CHAR(10),
year INTEGER
);

```

----

```sql

CREATE TABLE geography 
(
district_code  SERIAL,
district_name  CHAR(15),
state_code     CHAR(2),
state_name     CHAR(18),
region         SMALLINT
);

CREATE TABLE product (
product_code   INTEGER,
product_name   CHAR(31),
vendor_code    CHAR(3),
vendor_name    CHAR(15),
product_line_code  SMALLINT,
product_line_name  CHAR(15)
);

```

-------

R script 

----- 

```R 
library(dplyr)
library(nycflights13)

not_cancelled <- flights %>% 
  filter(!is.na(dep_delay)█, !is.na(arr_delay))

not_cancelled %>% 
  group_by(year, month, day) %>% 
  summarise(mean = mean(dep_delay))
```

