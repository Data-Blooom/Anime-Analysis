# 🌸 Anime Analysis Dashboard

## 📌 Project Overview

**Anime Blossom** is an interactive Power BI dashboard designed to analyze audience behavior, content popularity, and rating patterns across the anime industry.

Using over **12,000 anime titles** and more than **6 million user ratings**, this project uncovers insights into genre preferences, content types, community engagement, and the relationship between popularity and user satisfaction.

---

## 🎯 Business Objective

The goal of this project is to answer key questions such as:

- Which genres attract the largest audiences?
- What content types receive the highest ratings?
- Which anime have the strongest communities?
- Is there a relationship between popularity and user ratings?

These insights can support decision-making for streaming platforms, content producers, and recommendation systems.

---

## 📂 Dataset Information

The project uses two datasets:

### `anime.csv`

Contains metadata for each anime title.

| Column | Description |
|--------|-------------|
| `anime_id` | Unique anime identifier |
| `name` | Anime title |
| `genre` | Anime genres |
| `type` | Content type (TV, Movie, OVA, etc.) |
| `episodes` | Number of episodes |
| `rating` | Average community rating |
| `members` | Number of community members |

### `rating.csv`

Contains user ratings for anime titles.

| Column | Description |
|--------|-------------|
| `user_id` | Unique user identifier |
| `anime_id` | Anime identifier |
| `rating` | User rating score |

### Dataset Size

- 📺 **12,294 Anime Titles**
- ⭐ **6M+ User Ratings**
- 👥 **73K+ Users**

---

## 🛠️ Data Cleaning & Transformation (ETL)

Data preparation was performed using **Power Query**.

### Cleaning Steps

- Removed invalid ratings (`rating = -1`)
- Handled missing values in `genre`, `type`, and `rating`
- Replaced `"Unknown"` values in `episodes`
- Converted data types for numerical analysis
- Split multiple genres into separate rows
- Removed unnecessary columns
- Optimized the data model for performance

---

## 🔗 Data Model

A one-to-many relationship was created between the two tables:

```text
anime[anime_id] (1) ─────── (*) rating[anime_id]
```

- Relationship Type: **One-to-Many**
- Cross Filter Direction: **Single**

---

## 📊 Key Performance Indicators (KPIs)

### Total Anime

```DAX
Total Anime =
DISTINCTCOUNT(anime[anime_id])
```

### Total Ratings

```DAX
Total Ratings =
COUNTROWS(rating)
```

### Average User Rating

```DAX
Avg User Rating =
AVERAGE(rating[rating])
```

### Average Members

```DAX
Avg Members =
AVERAGE(anime[members])
```

---

## 📈 Dashboard Visualizations

### 📌 Top Genres by Audience Size

Displays the genres with the largest communities based on total members.

**Visual Type:** Bar Chart

---

### 📌 Average Rating by Content Type

Compares average ratings across different anime formats.

**Visual Type:** Donut Chart

---

### 📌 Top Anime by Community Size

Highlights anime titles with the highest number of members.

**Visual Type:** Bar Chart

---

### 📌 Popularity vs Community Rating

Analyzes the relationship between audience size and average ratings.

**Visual Type:** Scatter Chart

- X-Axis → Members
- Y-Axis → Rating
- Bubble Size → Episodes

---

## 💡 Key Insights

- Action and Comedy genres attract the largest audiences.
- TV series maintain the highest average ratings.
- Highly popular anime do not always receive the highest ratings.
- Community size and user ratings show a positive but imperfect relationship.

---

## 🎨 Dashboard Theme

The dashboard design is inspired by **Japanese Sakura Blossoms**.

### Color Palette

| Element | Color |
|----------|-------|
| Background | `#F2EEE9` |
| Primary | `#E06C9F` |
| Secondary | `#C95D8A` |
| Accent 1 | `#F3A8C2` |
| Accent 2 | `#8FC9C5` |
| Accent 3 | `#B8A1D9` |
| Accent 4 | `#F4C77D` |
| Text | `#4A3F55` |

---

## 🚀 Tools & Technologies

- **Power BI**
- **Power Query**
- **DAX**

---

## 📷 Dashboard Preview


```markdown
![Dashboard Preview](Anime-Analysis/OutPut
/Anime_page-0001.jpg)
```

---

⭐ If you found this project interesting, consider giving it a star!
