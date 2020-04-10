# czech-covid-db
I started this project on 19.3. 2020. I wanted to make a COVID-19 visualisation website of czech data,
but there wasn't a open dataset for CZ. I didn't want to manually write the numbers into a spreadsheet everyday,
so I came with a solution: make a [script](https://github.com/kukosek/czech-covid-db-wikipediaparser) that will check the [wikipedia page](https://cs.wikipedia.org/wiki/Pandemie_covidu-19_v_%C4%8Cesku)
in a regular time period. If it detects a change, it saves it as a record by appending a row to the CSV tables.  
### On 28.3., an [official open dataset](https://onemocneni-aktualne.mzcr.cz/api/v1/covid-19) was released
But it doesn't have everything as i would need. So I made a [new script](https://github.com/kukosek/czech-covid-db-multiparser) that parses data from wikipedia (into the repo root dir)
and also from the official page into new CSV tables in the uzis dir.
* Problem: They don't have a spreadsheet about recovered cases and deaths, only current numbers on the page.
  * Solution: Copy my records_deaths and records_recovered files that were updated by wikipedia's numbers into the uzis dir.
  Now check the [website](https://onemocneni-aktualne.mzcr.cz/covid-19)'s current numbers, and if they change,
  append a record to the CSV files (records_recovered_uzis.csv, records_deaths_uzis.csv)
* Problem: They have a JSON about every infected person, but I would need a records spreadsheet with numbers for
individual regions, individual import states and age groups
  * Solution: Parse the persons.json files and create new CSV files from it.
<a/>
records_tests_uzis.csv is the only file that is nearly the same as the original tests file from opendata.

## Used by
* [koronagrafy](https://github.com/kukosek/koronagrafy) - a page with chart visualisations and prediction of the pandemic

<!-- end of the list -->

*If you use this repository, feel free to create a issue mentioning your project. I will add your project here.*
