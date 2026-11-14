# Google Play Store Data Analytics Project

**Author:** Shubham Shah  
**Project Type:** Data Analytics / Business Intelligence  
**Primary Tool:** Microsoft Power BI

## 1. Project Overview

This project analyzes Google Play Store application listings to understand app-market performance, category demand, user ratings, engagement, pricing, app size, content ratings, and app update patterns.

The work uses the supplied Google Play Store dataset and presents the analysis through a five-page interactive Power BI dashboard. A project report and presentation accompany the dashboard to explain the business problem, findings, limitations, and recommendations.

## 2. Business Problem

The Google Play Store contains applications across many categories, with different levels of popularity, ratings, review activity, prices, and technical requirements. App developers and business teams need evidence to understand where demand is concentrated and how application characteristics relate to performance.

The project addresses questions such as:

- Which app categories and genres have the strongest install performance?
- How are app ratings distributed, and how do ratings differ between free and paid apps?
- How do installs, reviews, app size, and price relate to one another?
- Which content-rating groups are most common?
- What can the recorded last-updated dates tell us about the dataset's update pattern?

The intended stakeholders include app developers, product managers, marketing teams, senior management, app users, advertisers, and platform or technology partners.

## 3. Project Objectives

- Explore the distribution of apps across categories and genres.
- Identify categories with high total installs and high average installs per app.
- Compare free and paid apps by share, ratings, reviews, price, and size.
- Examine ratings and review volume as measures of user feedback and engagement.
- Explore app-size and price patterns in relation to performance.
- Review content-rating distribution and recorded last-updated dates.
- Translate the analysis into practical business recommendations.

## 4. Dataset

**File:** `googleplaystore.csv`

The supplied dataset contains **10,841 rows before cleaning** and 13 fields:

| Field | Description |
|---|---|
| App | Application name |
| Category | Application category |
| Rating | Average user rating (0–5 scale) |
| Reviews | Number of user reviews |
| Size | Application size |
| Installs | Install range shown in the source |
| Type | Free or Paid |
| Price | Application price, where applicable |
| Content Rating | Intended audience / content age rating |
| Genres | Application genre |
| Last Updated | Recorded date of the app's last update |
| Current Ver | Current application version |
| Android Ver | Minimum Android version required |

The source includes missing values, duplicate records, text-formatted numeric fields, install ranges, and app sizes expressed in MB, KB, or as `Varies with device`.

## 5. Tools and Technologies

- **Microsoft Power BI** — interactive dashboard and data visualization.
- **Power Query** — data cleaning and transformation.
- **DAX** — measures and KPI calculations.
- **Microsoft Excel / CSV** — source-data inspection and dataset handling.
- **GitHub** — project storage and documentation.

## 6. Data Preparation and Analysis Approach

The project report identifies the following preparation and validation tasks:

1. Inspect missing values and duplicate app records.
2. Convert `Reviews` to a numeric field.
3. Clean `Installs` by removing formatting characters such as commas and plus signs before numeric analysis.
4. Clean `Price` by removing currency symbols and converting it to a numeric field.
5. Standardize app size to a consistent MB value; convert KB values and treat `Varies with device` as missing rather than zero.
6. Convert `Last Updated` to a date field and derive the year for the update-year visual.
7. Standardize `Type` values as Free or Paid.
8. Handle missing ratings explicitly and exclude or correct invalid ratings outside the 0–5 scale. The raw source includes an anomalous rating value of 19.
9. Check that dashboard measures use the intended aggregation, such as count, distinct count, sum, or average.

Duplicate handling and aggregation rules should be documented when reproducing totals, because duplicate rows and install-range approximations can affect the results.

## 7. Power BI Dashboard Pages

The report contains five pages:

1. **Executive Overview** — headline KPIs, app mix, category installs, top apps, and rating distribution.
2. **Category & Genre Analysis** — category and genre comparisons, installs, average installs, ratings, app counts, and review activity.
3. **Ratings & User Engagement** — rating distribution, free-versus-paid rating comparison, and highly reviewed apps.
4. **Pricing & App Performance** — paid-app price and rating patterns, app-size comparisons, install relationship, content ratings, and last-updated year.
5. **Key Insights & Business Recommendations** — summary of the main findings and suggested business actions.

Category, Type, and Content Rating slicers can be used to explore selected segments.

## 8. Key Findings from the Dashboard

The figures below are the approximate values reported in the supplied project report and presentation. They are dashboard outputs and should be interpreted in light of the data limitations described later.

- Approximately **10K apps** are displayed.
- Displayed total installs are approximately **147 billion**.
- Displayed average rating is **4.19**.
- Displayed average reviews are approximately **405.55K**.
- Free apps account for approximately **92.60%** of apps; paid apps account for approximately **7.39%**.
- Game (**31.5bn**) and Communication (**24.2bn**) lead the displayed category install comparison, followed by Social (**12.5bn**), Productivity (**12.5bn**), and Tools (**11.5bn**).
- Communication has the highest displayed average installs per app (about **66M**), followed by Social (about **45M**) and Video Players (about **36M**).
- Events, Education, and Art & Design appear among the highest average-rating categories, at around **4.4**.
- The displayed average rating is about **4.3 for paid apps** and **4.2 for free apps**.
- The app-size comparison reports averages of about **21.5 MB for free apps** and **19.2 MB for paid apps**.
- The recorded last-updated chart peaks in **2018**, with approximately **6.9K apps** shown for that year.

## 9. Challenges and Data Considerations

The project materials identify several practical data-analysis challenges:

- **Missing and duplicate records:** Missing values and duplicate app entries need explicit treatment to avoid misleading counts and totals.
- **Mixed data formats:** Installs, prices, reviews, sizes, and dates require cleaning and type conversion before analysis.
- **Install ranges:** The source lists install bands such as `1,000+`, rather than exact download counts. Converting these bands to numeric values and summing them produces an approximation, not an exact number of downloads.
- **Inconsistent app sizes:** Sizes are recorded in different units, and some values are `Varies with device`.
- **Invalid and missing ratings:** The raw data includes missing ratings and an anomalous value of 19, although the rating scale is 0–5.
- **Choosing correct aggregations:** Counts, distinct counts, sums, and averages answer different questions and must be selected carefully.
- **Visual validation:** The project report flags an `Average App Size` visual on the Ratings & User Engagement page whose displayed scale (around 0.44M for Free) conflicts with the MB-scale averages on the Pricing page. This visual should be checked against the intended field and aggregation before relying on it.

## 10. Business Insights

### Free apps dominate the catalogue
The dashboard shows that free apps make up the large majority of listings. This indicates that free-to-download apps are the prevailing model in this dataset, although the dashboard alone does not establish which model is more profitable.

### Install demand is concentrated in a few categories
Game and Communication lead the category install comparison. These categories are useful areas for further market and competitor research.

### Paid apps show a slightly higher average rating
The displayed paid-app average rating is approximately 4.3, compared with 4.2 for free apps. This is a descriptive difference, not evidence that charging users causes higher satisfaction. The paid-app share is also much smaller.

### Review volume indicates activity, not sentiment
Apps such as Instagram and Facebook have very large review counts. A high review count indicates substantial user feedback activity; without review text, it does not show whether that feedback is positive or negative.

### App size alone does not explain installs
The app-size-versus-installs scatter plot is widely dispersed. The analysis does not show a clear simple relationship in which app size alone explains install performance.

### The update-year chart describes a historical snapshot
The displayed peak in 2018 reflects the dates recorded in this dataset. It should not be interpreted as current Google Play Store update activity or as a complete history of app releases.

## 11. Recommendations

1. **Research high-install categories:** Study Game and Communication apps to understand user needs, product features, onboarding, retention, and competitive positioning.
2. **Test monetization models:** Since free apps dominate the dataset, consider testing a freemium approach with ads, subscriptions, or optional premium upgrades. Evaluate conversion, retention, and revenue rather than assuming free is always best.
3. **Monitor quality with context:** Track ratings alongside review counts, installs, crashes, and retention. Use a minimum review-count threshold when benchmarking highly rated apps.
4. **Build a review-feedback process:** Classify recurring user complaints, prioritize high-impact issues, and communicate fixes through release notes. A separate review-text dataset would be needed for sentiment analysis.
5. **Optimize app size and performance:** Consider asset compression, modular downloads, and removal of unused resources. Evaluate changes against install conversion, crash rates, and retention.
6. **Plan maintenance using richer release data:** Schedule updates based on user feedback and product needs. Collect multiple release dates per app if update intervals are to be measured.
7. **Segment marketing appropriately:** Use category and content-rating segments to align campaigns with intended audiences and age-appropriate requirements.

## 12. Limitations

- The dataset is a historical snapshot and does not represent current Google Play Store conditions.
- Install figures are ranges in the source. Numeric totals derived from those ranges are approximate.
- Only one `Last Updated` date is supplied per app. The dataset cannot calculate the true average time between successive updates.
- Review text is not included, so review sentiment and recurring text themes cannot be analyzed from this file alone.
- Comparisons and relationships shown in the dashboard are descriptive and do not establish causation.
- The app-size visual flagged in the project report requires validation before its value is used as a confirmed result.

## 13. Repository Contents

The uploaded project folder contains the following files:

```text
Google-Play-Store-Data-Analytics-main/
├── Google_PlayStore_Analytic_Report.pbix
├── Google_Play_Store_Analytics_Project_Presentation.pptx
├── Google_Play_Store_Analytics_Project_Report.docx
├── Problem Statement_Google_Playstore.docx
├── googleplaystore.csv
├── Screenshot 2026-11-14 104025.png
├── Screenshot 2026-11-14 104046.png
├── Screenshot 2026-11-14 104113.png
├── Screenshot 2026-11-14 104139.png
├── Screenshot 2026-11-14 104159.png
└── README.md
```

The screenshots are included as separate dashboard image files. Their current filenames are retained from the supplied project folder.

## 14. Conclusion

This project demonstrates the use of Power BI, Power Query, and DAX to analyze Google Play Store application data and communicate findings through an interactive dashboard. The analysis highlights the dominance of free apps in the dataset, the concentration of installs in Game and Communication, differences in displayed ratings between free and paid apps, and the need to interpret app size and update patterns carefully.

The report also documents data-quality issues and limitations so that business recommendations are based on what the dataset can support.

## 15. Author

**Shubham Shah**

**Project:** Google Play Store Data Analytics  
**Tools:** Microsoft Power BI, Power Query, DAX, Microsoft Excel / CSV
