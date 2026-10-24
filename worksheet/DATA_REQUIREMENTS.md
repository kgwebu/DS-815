# Data and access requirements

The original folder contained notebooks only. External datasets, database access, and API credentials were not included. Obtain the materials below before assigning the dependent lessons. Use raw input data, not completed analyses or solution notebooks. Each notebook explains which variables depend on external inputs.

For file-based lessons, create a `data` folder beside the notebook and place that lesson's inputs there. Students should use paths relative to their notebook. Never distribute secrets inside notebooks. An instructor-provided raw JSON fixture can support offline API response-processing exercises; it does not replace the live authentication/request activities.

## Week 4: APIs and MySQL

- **Yelp:** Assigned official documentation/version, authorized search access, and an API key supplied separately, or a raw search-response JSON fixture. The response must include a business-record collection. Confirm its actual field names before assigning the extraction tasks.
- **Twitter:** Assigned API/client versions, accessible endpoint documentation, and authorized credentials supplied separately, or a raw post-response JSON fixture. The original workflow used legacy Twitter/Tweepy calls; no live compatibility is claimed here. Required post fields, where available: identifier, text, creation time, language; author information is optional. A fixture must include enough metadata to describe its search and collection date.
- **MySQL:** Reachable teaching database, read-only account, supported driver, and Customer_T schema. Supply host/database/user configuration separately from the password. For offline inspection only, a raw exported customer fixture may be used, with live query activities marked unavailable.

## Week 5: pandas

Supply these files in `Week_05_Pandas_and_Tidy_Data/data/`:

- `titles.csv`: id, title, type, release_year, age_certification, runtime, genres, production_countries, seasons, imdb_score. Additional fields beginning with imdb, ending with score, or containing db make the column-pattern exercises richer. Include enough rows for sampling and positional selection; 21 or more rows supports the full row-position activity. Use MOVIE/SHOW type labels or tell students the actual encoding. Ensure id identifies a title or explicitly document exceptions.
- `credits.csv`: id as the title foreign key, plus credited person name/identifier and role. Multiple credits per title are expected; document its observation unit.
- An instructor-selected JSON file containing tabular records for the JSON import task.
- An optional instructor-selected Excel file and sheet name for the Excel import extension. Students may need the appropriate Excel-reading dependency.
- An instructor-approved public tabular-data URL or its local downloaded equivalent for the URL-import task.

### Tidy-data inputs

Provide table1, table2, table3, table4a, table4b, and table5 as JSON or CSV, documenting the exact filenames. Use comparable country/year observations across the six tables:

| Input | Required layout |
| --- | --- |
| table1 | country, year, cases, population |
| table2 | country, year, type (cases or population), count |
| table3 | country, year, rate containing a cases/population pair separated by `/` |
| table4a | country and year-named columns containing case counts |
| table4b | country and year-named columns containing population |
| table5 | country, century, year (year part as text), rate containing cases/population |

The source notebook referenced [the BYU teaching data collection](https://github.com/byuidatascience/data4python4ds/tree/master/data-raw). Confirm the assigned files and schemas before class. No copy of that source is included. The case_rate definition in the worksheet is cases per 100,000 people.

## Week 7: visualization and Airbnb

Supply Boston detailed `listings.csv` and `reviews.csv` from the same snapshot. The source notebook referenced [Inside Airbnb](https://insideairbnb.com/get-the-data/). Record snapshot date and source, rather than relying on the old hard-coded 2022 download paths.

Listing fields: id, host_since, name, description, neighbourhood_cleansed, room_type, review_scores_rating, review_scores_accuracy, review_scores_cleanliness, review_scores_checkin, review_scores_communication, review_scores_location, review_scores_value, host_identity_verified, number_of_reviews, reviews_per_month, price, latitude, longitude, host_is_superhost, availability_365.

Review fields: id (the review identifier), listing_id (the listing foreign key), date. Check identifier uniqueness and the join relationship before assigning analyses. A listing snapshot's price is not a historical price series just because it has been joined to older review dates.

For the introductory Seaborn section, provide `tips.csv` with total_bill, tip, sex, smoker, day, time, or enable access to the Seaborn sample-data loader. For the optional word cloud, install the wordcloud package in the teaching environment.

## Week 7: Open Food Facts

Provide assigned [Open Food Facts API documentation](https://openfoodfacts.github.io/openfoodfacts-server/api/) and request/access instructions, or a saved raw product fixture. Record collection date and query categories. The worksheet uses chocolate, pizza, yogurt, chips, juice, and cereal, with at most 50 products per category. Confirm supported request limits before live collection.

Raw-to-analysis field names:

| Raw field | Analysis field |
| --- | --- |
| code (if available) | code |
| product_name | product_name |
| brands | brand |
| categories | categories |
| nutrition_grades | nutrition_grade |
| nutriscore_score | nutri_score |
| nova_group | nova_group |
| ingredients_text | ingredients |
| energy-kcal_100g | calories_100g |
| fat_100g | fat_100g |
| sugars_100g | sugar_100g |
| proteins_100g | protein_100g |
| salt_100g | salt_100g |
| countries_tags | countries |

Students create search_category during collection. Fields may be absent, and dependent tasks must be documented accordingly. TextBlob is required for the sentiment section; scores and labels are computed by students, not bundled as input.

## Additional practice: Spotify

Provide `universal_top_spotify_songs.csv` from the [source named in the original notebook](https://www.kaggle.com/datasets/asaniczka/top-spotify-songs-in-73-countries-daily-updated) or an instructor-approved equivalent. Record the actual snapshot, source, and field definitions.

Required for the full worksheet: a song identifier (for example spotify_id), name, artists, album_name, album_release_date, snapshot_date, country, is_explicit, daily_rank, daily_movement, weekly_movement, popularity, duration_ms, danceability, energy, loudness, tempo, key, valence. Some source snapshots may not have all audio fields. Confirm coverage before assigning the full project, or explicitly omit the dependent activities.

Students derive duration_minutes, release_year, release_month, release_day, release_day_of_week, and artist_popularity_score. Do not distribute completed versions of those derived features as answers. Repeated songs across countries and dates need a documented observation key and independence assessment before statistical testing.

## Software

Weeks 1–2 and the functions lesson use Python's standard library. Later lessons need the packages named in their setup sections: NumPy, pandas, requests, Matplotlib, Seaborn, and selected extensions (TextBlob, SciPy, wordcloud, a MySQL driver, and an Excel reader). Have the instructor install compatible versions for the chosen teaching environment. No package installation or live API/database operation was performed during the worksheet cleanup.
