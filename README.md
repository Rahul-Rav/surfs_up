# surfs_up

### Overview
We are planning to open up a surfboard and icre cream shop in Hawaii and are looking to gain the support of an investor. When we present our plan to the investory, he raises concern about the weather. He provides us with a weather data set and asks us to run an analysis for the island that we plan to open our new business in, the island of Oahu. Using SQLAlchemy and the SQLite databse, we analyze the weather data to hopefully receive financial backing from the investor.

### Results
![temp_june](https://user-images.githubusercontent.com/95504135/155895650-8624427c-7fae-4a7e-9cda-3fb424ff6566.png)
![temp_december](https://user-images.githubusercontent.com/95504135/155895655-686f735a-420b-4729-8153-19a7e291c439.png)
* The most drastic potential difference between the months of June and December is the likelihood that temperatures may drop to 56° in December.
* December temperatures vary more in comparison to June temperatures which stay fairly consistent throughout the month, though they are both still fairly consistent.
* The maximum temperature in December is 83° whereas June's max temperature is 85°.

### Summary
After analyzing the data, we can see that there aren't too many major differences in the consistency of the weather patterns in Oahu within the months of June and December. Yes, the lowest temperature recorded in December was 56°, but when looking at the rest of the data for the month, it should not be a major factor on the investment decision. Our initial analysis shows that weather not drastically changing between the two months should have us consider performing additional queries.

* ### Additional Query 1 (June)
june_precipitation = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) ==6).all()
list(june_precipitation)

* ### Additional Query 2 (December)
december_precipitation = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) ==12).all()
list(december_precipitation)

![precipitation_june](https://user-images.githubusercontent.com/95504135/155898337-c600c4fb-cd0b-4cea-80f3-ade0d7542d74.png)
![precipitation_december](https://user-images.githubusercontent.com/95504135/155898341-90942943-5b90-4d9c-b7a0-902251d9b492.png)

With addition of these two queries, we can analyze the precipitation in Oahu for the months of June and December, which is another important factor when considering the opening of a business such as a surf shop. We can see that in addition of temperatures being colder in December, it rains more in December as well. Since this is a winter month, slowdown in business is to be expected, though neither the temperature and precipitation is that drastically different from the June data.
