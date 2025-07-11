# Social-Media-Engagement-Analysis
## Project Background
In the dynamic digital landscape, social media platforms like Instagram, LinkedIn, Facebook, and Twitter are pivotal for businesses to enhance brand visibility, engage with diverse audiences, and achieve marketing objectives. With the proliferation of social media activity, businesses generate vast amounts of data on user interactions, content performance, and campaign outcomes. The challenge lies in transforming this data into actionable insights to optimize strategies, allocate resources effectively, and maintain a competitive edge in a crowded market.

This project was undertaken to develop a Power BI report that analyzes social media performance metrics, focusing on engagement, impressions, and content effectiveness across platforms. The report leverages a comprehensive dataset capturing key metrics such as `Post_ID`, `Platform`, `Post_Date`, `Content_Type`, `Likes`, `Shares`, `Comments`, `Impressions`, `Click_Through_Rate`, `Campaign_ID`, `Hashtag_Count`, and `Engagement_Score`. By providing an interactive dashboard, the report empowers businesses to make data-driven decisions to enhance their social media presence and achieve strategic goals.

**Key Insights and Recommendations Focused on**:

- **Engagement Metrics by Platform**: Analysis of likes, shares, and comments across Instagram, LinkedIn, Facebook, and Twitter to identify top-performing platforms and tailor content strategies to maximize audience interaction.
- **Impression Distribution by Platform**: Evaluation of how impressions are distributed across platforms to understand reach and prioritize channels that deliver the highest visibility.
- **Performance Summary by Platform**: Comprehensive overview of engagement, impressions, and other metrics (e.g., click-through rates) by platform to assess overall effectiveness and guide resource allocation.
- **Engagement by Content Type Across Platforms**: Examination of how content types (e.g., Image, Video, Text, Carousel) perform on each platform to identify high-impact formats and optimize content creation.
- **Engagement Score vs. Hashtag Count**: Analysis of the relationship between hashtag usage and engagement scores to determine optimal hashtag strategies for enhancing discoverability and interaction.
- **Engagement Breakdown by Content Type**: Detailed assessment of engagement scores by content type to inform content planning and prioritize formats that drive the highest engagement.

An interactive Power BI dashboard was developed to visualize these focus areas, offering dynamic filters and visuals (e.g., clustered bar charts, pie charts, scatter charts, treemaps) to explore platform performance, content trends, and hashtag effectiveness.

### Data Structure & Initial Checks

The dataset forms the backbone of the Social Media Performance Report, structured to support detailed analysis of engagement and reach across platforms.

**Table Columns**:
- **Post_ID**: Unique identifier for each post (text), ensuring traceability and preventing duplication in analysis.
- **Platform**: Social media platform (e.g., Instagram, LinkedIn, Facebook, Twitter; categorical), enabling segmentation by channel.
- **Post_Date**: Date of post publication (date), used for temporal analysis of engagement and impressions.
- **Content_Type**: Type of content posted (e.g., Image, Video, Text, Carousel; categorical), critical for assessing content performance.
- **Likes**: Number of likes received (numeric), reflecting audience approval and engagement.
- **Shares**: Number of shares or retweets (numeric), indicating content virality and reach amplification.
- **Comments**: Number of comments (numeric), measuring discussion depth and audience interaction.
- **Impressions**: Total views of the post (numeric), representing overall reach.
- **Click_Through_Rate**: Ratio of clicks to impressions (decimal), assessing content effectiveness in driving actions.
- **Campaign_ID**: Identifier for associated marketing campaign (text), supporting campaign-specific analysis.
- **Hashtag_Count**: Number of hashtags used (numeric), key for analyzing discoverability and engagement trends.
- **Engagement_Score**: Weighted sum of likes, shares, and comments (e.g., `Likes * 1 + Shares * 2 + Comments * 1.5`; numeric), providing a composite engagement metric.

**Key Early Checks**:
- **Data Type Validation**: Confirmed appropriate data types: `Post_ID` and `Campaign_ID` as text, `Platform` and `Content_Type` as categorical, `Post_Date` as date, `Likes`, `Shares`, `Comments`, `Impressions`, and `Hashtag_Count` as whole numbers, and `Click_Through_Rate` and `Engagement_Score` as decimals.
- **Missing or Null Values**: Checked for missing data in critical columns (e.g., `Impressions`, `Likes`, `Engagement_Score`). Handled minimal missing values by filling numeric fields with zeros or excluding incomplete records where necessary.
- **Duplicate Records**: Verified `Post_ID` uniqueness to eliminate duplicate posts that could skew engagement or impression metrics, removing duplicates in Power Query if found.
- **Categorical Consistency**: Ensured `Platform` (e.g., only “Instagram,” not “Insta”) and `Content_Type` values were standardized to support accurate filtering and grouping.
- **Outlier Detection**: Inspected numeric fields (e.g., `Impressions`, `Hashtag_Count`, `Engagement_Score`) for outliers that might indicate data errors or bot activity, flagging them for review.
- **Engagement_Score Validation**: If pre-calculated, verified `Engagement_Score` aligned with the weighted formula (e.g., `Likes * 1 + Shares * 2 + Comments * 1.5`). If absent, prepared to create it as a DAX measure in Power BI.
- **Date Consistency**: Ensured `Post_Date` was uniformly formatted and covered the relevant campaign period for accurate temporal analysis.


# Executive Summary
## Overview of Findings
Instagram is the top-performing platform, while Facebook struggles to keep pace. Impression share is balanced across platforms **(±2.15% difference)**, with Instagram holding a slight edge.  Twitter’s text/image content drives the highest engagement. Video is critical for Facebook/Instagram success. LinkedIn consistently underperforms across all content types.  Instagram’s text/image and Twitter’s carousel/video are highest-performing, reflecting platform-specific content preferences.  More hashtags drive higher engagement, but Instagram achieves disproportionate returns. Carousel and image content drive nearly identical engagement **(25.5% combined)**, outperforming video and text by **+1.54%**.
