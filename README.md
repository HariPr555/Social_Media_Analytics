# Social_Media_Analytics
A data-driven analysis of a YouTube channel focused on understanding video performance, user engagement, and content optimization. Utilizing Power BI, this project explores insights to drive channel growth through improved content strategies and audience interaction analysis.

![Youtubr_analytics](https://github.com/user-attachments/assets/388a3691-d57d-4c44-9b70-385d7a45a193)


# 1. Background
In today's competitive YouTube environment, creators need more than just content to succeed, they need actionable insights derived from data. For a relatively new channel like Loresowhat, data analysis is essential for understanding what resonates with the audience. By analyzing metrics such as views, engagement rates, and audience retention, data analysis provides clarity on which types of videos perform best, which durations drive the most interaction, and where there's room for improvement. This project can help the channel optimize its content strategy, leading to higher viewership, improved engagement, and faster growth.

# 2. Project Objectives
- To explore how different types of content perform, especially comparing Regular videos and Shorts.
- To identify the relationship between video length and views.
- To analyze engagement metrics such as likes, dislikes, comments, and their correlation with total views.
- To provide insights into content optimization based on video performance and audience interaction."'

# 3. Technical Stacks

Data Visualization Tool: Power BI

Data Source: CSV containing YouTube channel data

# 4. Data Understanding
The dataset contains 86 videos and consists of the following features:
- Category: The type of content (e.g., People & Blogs, Education).
- Video Type: Regular or Shorts.
- Views, Likes, Dislikes, Comments: Interaction metrics from users.
- Video Duration: Length of the videos in seconds.

# 5. Data Preprocessing

- **Remove Empty Columns and Rows**: Identify and remove any empty columns and rows.
- **Remove Duplicates**: Deduplication of data to avoid redundancy.
- **Rename Columns**: Ensure appropriate names are used for better analysis.
- **Change Data Types**: Ensure columns have appropriate data types (e.g., dates, numbers, text).
- **Handle null values**: Replaced null values with “Not Available”
- **Standardize Values**: Replaced and formatted values to maintain data consistency.
- **Split Columns**: Create new columns to generate hierarchy for trend and pattern analysis.
- **Feature Selection**: Selected relevant features and dropped the irrelevant columns.

# 6. Data Modelling

- Create Fact and Dimension Tables:
  - Fact Table: Youtube Data
  - Dimension Tables: Date
- Establish Relationship between Fact and Dimension Tables
- Data Formatting
- Generate Hierarchies
- DAX

# 7. DAX
**Calculated Measures**:
- Average Comments = AVERAGE('Youtube Data'[Comments])
- Average Dislikes = AVERAGE('Youtube Data'[Dislikes])
- Average Likes = AVERAGE('Youtube Data'[Likes])
- Average Video Duration = AVERAGE('Youtube Data'[Length (minutes)])
- Average View = AVERAGE('Youtube Data'[Views])
- Total Comments = SUM('Youtube Data'[Comments])
- Total Dislikes = sum('Youtube Data'[Dislikes])
- Total Likes = SUM('Youtube Data'[Likes])
- Total Views = SUM('Youtube Data'[Views])

**Calculated Columns**:
- Comment Engagement Rate = DIVIDE('Youtube Data'[Comments], 'Youtube Data'[Views], 0)
- Length (minutes) = 'Youtube Data'[ Length (seconds)]/60
- Like Engagement Rate = DIVIDE('Youtube Data'[Likes], 'Youtube Data'[Views], 0)
- Outliers = if(or('Youtube Data'[ Title]="The ONLY Data Analytics Portfolio Project You Need - Walkthrough",'Youtube Data'[ Title]="The harsh reality of a Data Analyst job #shorts"), "Yes", "No")
- Positive Engagement = DIVIDE('Youtube Data'[Likes]+'Youtube Data'[Comments], 'Youtube Data'[Views], 0)
- Video Type = IF('Youtube Data'[ Length (seconds)]>60, "Regular", "Shorts")

# 8. Report Visualization
- **Total Videos Uploaded by Category**
    - People & Blogs (76.74%) dominates the content landscape with 66 videos, while Education (23.26%) has 20 videos.
      
- **Positive Engagement by Video Type**
    - Regular Videos have a slightly higher engagement rate of 0.08 compared to Shorts with an engagement rate of 0.07.
      
- **Interaction Report by Video Type**
    - Regular Videos outperform Shorts in terms of average views, likes, and comments. For example, Regular Videos have an average of 3225 views per video, whereas Shorts have 1773 views on average.
    - The average video duration for Regular content is 10.20 minutes, whereas Shorts have an average duration of 0.72 minutes.
      
- **Total Videos Uploaded Over Time**
    - A significant increase in video uploads is observed from 2022 to 2023, with Regular videos seeing the largest growth (from 13 to 32 uploads).
  
- **Relationship Between Video Length and Views**
    - Regular videos with a duration of 5 to 15 minutes tend to generate higher views compared to Shorts. This suggests that users engage more with moderately long content.

# 9. Insights
- Regular videos consistently perform better in terms of views and engagement compared to Shorts.
- People & Blogs category drives the majority of content views and engagement, indicating a strong audience preference.
- The optimal video length for maximizing views is between 5 to 15 minutes, particularly for Regular content.
- Video duration has a direct impact on views, especially for Regular content. Shorts, despite their quick consumption nature, do not generate the same level of engagement.

# 10. Recommendations
- **Focus on Regular Content**: Since regular videos receive higher views and interaction, it is advisable to continue focusing on creating more regular content in the 5 to 15-minute range.
- **Optimize Shorts**: While Shorts have a lower engagement rate, they still attract quick views. A strategy of leveraging Shorts for audience retention while driving them to longer content can be effective.
- **Explore Content Categories**: Diversifying the content, especially in underrepresented categories like Education, could attract a broader audience.
- **Monitor Engagement Metrics**: Continuously track likes, dislikes, and comments to adapt content strategy based on user feedback.

# 11. Future Scope
- Analyze demographic data to understand the audience better.
- Implement machine learning models to predict video performance based on attributes like category, video length, and posting time.
