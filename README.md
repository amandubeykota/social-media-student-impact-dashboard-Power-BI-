# social-media-student-impact-dashboard-Power-BI-
Power BI dashboard analyzing social media usage patterns and their conflicts and impact on students' academic and personal life.

# Social Media & Student Life — Power BI Dashboard

An interactive 6-page Power BI report analyzing students' social media usage and its impact on academics, mental health, sleep, and personal relationships. Built on two related tables (student details and platform usage details) with dedicated DAX measures, bookmarks, and a drill-through student profile page.

> **Note:** GitHub cannot render `.pbix` files. Screenshots of each page are included below, and the report file (`student-social-media-impact.pbix`) can be downloaded and opened in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).

---

## Project Objective

Social media is deeply woven into student life, but heavy usage can come at a cost. This dashboard explores:

- How much time students spend on social platforms daily, and on which platforms
- Whether usage patterns relate to academic performance, sleep, and mental health
- How social media contributes to conflicts across different relationship statuses
- How these patterns differ by gender, age, academic level, and country

---

## Data Model

| Table | Description |
|---|---|
| **Student Details** | One row per student — age, gender, country, academic level, relationship status, sleep hours, mental health score, addiction score, conflicts over social media |
| **Platform Details** | Platform-level usage per student — most used platform, average daily usage hours, whether usage affects academic performance |
| **Measures Table** | Dedicated table holding all report-level DAX measures |

The two data tables are related on `Student_ID`. Derived fields include **Health Band** (banding of mental health scores) and **Conflict Level** (banding of conflict counts) to make the analysis readable for non-technical viewers.

### Key DAX Measures
- `Avg Usage Hours` — average daily social media usage across the filtered student population
- `Avg Sleep Hours` — average nightly sleep
- `% Affected Academically` — share of students reporting that social media affects their academic performance

---

## Report Pages

### 1. Executive Overview
KPI cards (total students, average usage hours, % affected academically, average sleep hours) alongside addiction score by academic level, average daily usage by age, and gender distribution — the one-glance summary page.

<!-- ![Executive Overview](screenshots/01_executive_overview.png) -->

### 2. Mental Health & Lifestyle
A country × health-band matrix, an addiction score vs mental health score scatter plot, and sleep hours across age — with a gender slicer to compare subpopulations.

<!-- ![Mental Health & Lifestyle](screenshots/02_mental_health.png) -->

### 3. Academic Impact
Average daily usage by academic level and academic performance impact broken down by platform, filterable by age.

<!-- ![Academic Impact](screenshots/03_academic_impact.png) -->

### 4. Relationships & Conflicts
Conflict level by relationship status, relationship status distribution, and a student-level table of addiction scores — filterable by country and academic level.

<!-- ![Relationships & Conflicts](screenshots/04_relationships_conflicts.png) -->

### 5. Interactive Story View
A bookmark-driven page: custom image buttons toggle between a **Gender View** and an **Academic Level View**, swapping the visible charts (usage and platform preference by the selected dimension) without leaving the page.

<!-- ![Interactive Story View](screenshots/05_story_view.png) -->

### 6. Student Profile (Drill-through)
Right-click any student in the report to drill through to an individual profile — gender, country, age, most used platform, usage hours, sleep, addiction score, mental health score, and conflicts — with a back button to return.

<!-- ![Student Profile Drill-through](screenshots/06_student_profile.png) -->

---

## Power BI Features Demonstrated

- **Data modeling** — two related tables joined on `Student_ID`, plus a separate measures table
- **DAX** — reusable measures for usage, sleep, and academic-impact KPIs
- **Bookmarks + action buttons** — interactive view switching with custom image buttons
- **Drill-through page** — student-level profile with a back navigation button
- **Slicers & cross-filtering** — gender, age, country, and academic-level filters
- **Visual variety** — KPI cards, bar/column, line, pie/donut, scatter, matrix, and table visuals
- **Derived columns / banding** — Health Band and Conflict Level groupings for readability

---

## How to Use

1. Download `student-social-media-impact.pbix` from this repository
2. Open it in Power BI Desktop (free download from Microsoft)
3. Use the slicers on each page to filter; on Page 5, click the image buttons to switch views; right-click a student anywhere to drill through to their profile

---

## Key Insights

- **High school students show the highest average addiction score** of any academic-level group in the dataset.
- **18-year-olds report the lowest average sleep and the highest average daily usage** (seen by comparing the age-based line charts on the Executive Overview and Mental Health & Lifestyle pages). This lines up with the first insight, since 18-year-olds in this dataset are predominantly still in high school — though 18 is a transitional age that can include early college students too, so this should be read as a pattern rather than a confirmed cause.
- **Instagram has the highest count of students reporting that social media affects their academic performance**, more than any other platform in the dataset. This points to Instagram as a platform worth watching for academic-impact interventions, though the data shows an association rather than a tested causal effect.

---

## Tools

`Power BI Desktop` · `DAX` · `Power Query`
