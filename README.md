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

Deliverables

Power BI [social media engagement analysis.pbix](https://github.com/Numb3rNinja/Social-Media-Engagement-Dashboard.git) file with the dashboard.

# Executive Summary
## Overview of Findings
Instagram is the top-performing platform, while Facebook struggles to keep pace. Impression share is balanced across platforms **(±2.15% difference)**, with Instagram holding a slight edge.  Twitter’s text/image content drives the highest engagement. Video is critical for Facebook/Instagram success. LinkedIn consistently underperforms across all content types.  Instagram’s text/image and Twitter’s carousel/video are highest-performing, reflecting platform-specific content preferences.  More hashtags drive higher engagement, but Instagram achieves disproportionate returns. Carousel and image content drive nearly identical engagement **(25.5% combined)**, outperforming video and text by **+1.54%**.
![Image](https://github.com/user-attachments/assets/d65e889e-2bc3-427a-9599-dadc505bcf90)
![Image](https://github.com/user-attachments/assets/ae58df92-6bab-49db-9431-c315c8a33810)

# Insights Deep-Dive
## Platform Comparison
Comparison of platforms by engagements reveals a clear heirarchy  of platform performance across likes, shares, and comments from 2019-2024. Instagram emerges as the undisputed leader, commanding the highest engagement volume in all three core metrics. With 6,759,942 total likes, Instagram outpaces its closest competitor (Twitter) by over 500,000 likes, establishing itself as the primary platform for audience endorsement. This dominance extends to sharing behavior, where Instagram’s 3,216,833 shares significantly exceed other platforms, suggesting superior content virality and resonance. Most notably, Instagram’s 1,958,363 comments dwarf Facebook’s count by nearly 170,000, indicating deeper audience investment and conversational engagement—a critical indicator of community strength.  

Twitter secures second place overall but demonstrates a distinct engagement profile. While its 6,250,522 likes position it as a strong alternative to Instagram for audience approval, its sharing (3,132,588) and commenting (1,852,235) metrics lag slightly behind LinkedIn despite Twitter’s larger user base. This divergence hints at Twitter’s role as a broadcast-friendly environment where content garners quick validation (likes) but stimulates less discussion or redistribution than Instagram. LinkedIn presents a compelling contrast as the dark horse performer. Though third in likes (5,988,131), it unexpectedly edges out Twitter in shares (3,194,460) and comments (1,876,469), revealing its underappreciated capacity for driving meaningful professional engagement and content circulation within niche communities.  

Facebook anchors the performance spectrum with concerning consistency. It trails in all three metrics—likes (5,897,096), shares (3,013,968), and comments (1,788,560)—despite historically receiving comparable resource allocation. The platform’s particularly weak comment volume (nearly 170k below Instagram) signals dwindling conversational relevance, while its last-place position in shares suggests declining content amplification efficiency. This underperformance is especially striking given Facebook’s massive global user base, implying fundamental misalignment between content strategy and audience expectations on the platform.  

These findings collectively paints Instagram as the engagement powerhouse, LinkedIn as a high-value niche player, Twitter as a validation-centric network, and Facebook as a platform requiring urgent strategic reevaluation to reverse its consistent engagement deficit.
 
![Image](https://github.com/user-attachments/assets/49b933a7-f12c-4ccc-b0f3-45e18b35391e)

## Impression by Platform
Analysis of the distribution of impression by platforms reveals near-identical impression shares across platforms (Instagram: 26.26%, LinkedIn: 25.25%, Twitter: 24.38%, Facebook: 24.11%) masks critical performance disparities when contextualized with engagement data. Instagram’s marginal impression lead (26.26% of 253.5M) becomes strategically significant when paired with its dominant engagement metrics – it converts visibility into 30% of total likes and 26% of shares despite only a 2.15% impression advantage over LinkedIn. This indicates superior algorithmic alignment and audience resonance, where content not only reaches eyes but triggers action. Conversely, Facebook’s 24.11% impression share (61.1M impressions) delivers disproportionately weak returns, generating the lowest likes (5.9M) and comments (1.79M) of all platforms. This suggests systemic issues in either audience targeting (reaching passive users) or content relevance (failing to engage despite visibility).  

LinkedIn’s 25.25% impression share (64M impressions) is particularly noteworthy given its niche professional user base. When combined with its second-place ranking in shares (3.19M) and comments (1.88M), it reveals an undervalued opportunity for B2B influence – impressions here likely reach higher-value decision-makers despite smaller absolute reach. Twitter’s middle-ground impression position (24.38% / 61.8M) aligns with its role as a “reactive” platform: adequate visibility fuels its strong like volume (6.25M) but doesn’t translate to proportional sharing or commenting, indicating users engage superficially amid fast-scrolling behavior.  
![Image](https://github.com/user-attachments/assets/ab7d6f6a-4a4e-43e0-843b-c263fa647996)

## Platform & Content Metrics
Platform and content metrics reveals a striking misalignment between platform strengths and content performance, with Twitter unexpectedly dominating the top tier. Twitter’s text-based content achieves an industry-leading 18.49% engagement rate – outperforming Instagram’s visually-focused platform by 0.78% despite Instagram’s algorithmic bias toward media. This anomaly suggests Twitter’s user base actively seeks substantive discussions, with text (18.49%), images (18.33%), and carousels (18.17%) all exceeding 18%. Notably, Twitter’s video content underperforms at 17.74%, revealing a platform-specific content paradox where static formats drive deeper engagement than motion media. Instagram demonstrates balanced but unexceptional performance, with video (18.10%) and images (18.06%) within 0.04% of each other, confirming its reputation as a visual-first but format-agnostic environment. Its text engagement (17.71%) lags significantly behind Twitter’s, exposing limitations in long-form storytelling on the platform.  

Facebook presents a tale of two strategies: its video content (18.16%) nearly matches Instagram’s peak performance, while carousels (16.73%) collapse to the table’s lowest rank – a devastating 1.43% gap versus its own video success. This divergence signals catastrophic creative misalignment, where Facebook’s algorithm and users reward snackable video but reject interactive carousels. LinkedIn’s uniform mediocrity is most concerning: all content types languish below 17.65%, with text (16.98%) nearly 1.5% behind Twitter’s equivalent. This consistent underperformance – despite LinkedIn’s 25.25% impression share – implies systemic audience disconnect or content sophistication mismatch.  
![Image](https://github.com/user-attachments/assets/9ae79cb3-35a5-44e8-8d01-0132ded4207d)

## Content Type Performance
Analysis of how each content type performs across all platforms reveals Instagram as the overall engagement leader with 11.94 million total interactions, driven by exceptional performance in both image content (3.17 million) and surprisingly, text posts (3.01 million) – an unusual strength for this visual-centric platform. Twitter follows closely with 11.24 million engagements, showing particular affinity for video (2.87 million) and carousel formats (2.92 million). LinkedIn demonstrates remarkable balance across all content types (ranging 2.67-2.85 million), with images being its strongest format. Facebook trails slightly at 10.70 million total engagements but shows a distinctive advantage with carousels (2.99 million), which generate 28% of its total engagement – the highest platform-content synergy in the dataset. 

**Notable patterns emerge when examining content-type performance:** Carousels thrive most on Facebook, images dominate on Instagram (achieving the single highest content-type engagement overall), videos perform most strongly on Twitter, and text content unexpectedly excels on Instagram despite the platform's visual nature. Facebook shows relative weakness in text engagement (2.34 million), while LinkedIn maintains consistent performance within a narrow 190K engagement range across all formats. Twitter's video leadership suggests its effectiveness for snackable video content, whereas Instagram's text anomaly indicates users engage deeply with captions and text-based storytelling. 
![Image](https://github.com/user-attachments/assets/16f31655-7f76-4334-aff9-c66877082042)

## Hashtags vs. Engagement
Examination of the relationship between Hashtag usage and Engagement score reveals a distinct and strong positive correlation between the number of hashtags used and the resulting engagement score across all four major social media platforms analyzed: Facebook, LinkedIn, Twitter, and Instagram. As the number of hashtags increases, so does the total engagement score, indicating hashtags are a significant driver of user interaction. Ranking the platforms clearly shows this relationship: Instagram, using the highest number of hashtags (12,466), achieved the highest engagement score (4,256,535.60), solidifying its position as the leader in both metrics. Twitter followed closely with 12,027 hashtags yielding 3,995,655.70 engagement, while LinkedIn, with 11,903 hashtags, generated 3,916,531.10 engagement. Facebook, using the fewest hashtags (11,474), resulted in the lowest engagement score (3,799,596.80).

Looking closer at the data, the marginal differences between Twitter and LinkedIn are notable. Despite only a 1% difference in hashtag count (12,027 vs. 11,903), Twitter slightly outperformed LinkedIn in engagement (3,995,655.70 vs. 3,916,531.10). This minor variance suggests platform-specific algorithms or audience behaviors may give Twitter a slight edge in translating hashtags into engagement. Instagram's performance stands out significantly. It achieved roughly 11% higher engagement than Facebook while using only about 8.6% more hashtags, indicating its algorithm or user base is substantially more responsive to hashtag-driven content. Conversely, Facebook's efficiency appears lower; despite using only about 3.4% fewer hashtags than LinkedIn, its engagement was about 3% lower, reinforcing the platform's known shift away from organic reach via public hashtags towards other mechanics like private groups and paid advertising.

The overarching implication is that hashtag volume acts as a major predictor of engagement across these platforms. However, the *return on investment* (engagement gained per hashtag) varies significantly by platform, with Instagram delivering the highest returns and Facebook the lowest. This underscores the critical need for platform-specific hashtag strategies. While the data strongly suggests using higher volumes of hashtags (12,000+) correlates with significantly higher engagement (3.9M+), several important caveats exist. The correlation observed doesn't prove causation; other factors like content quality, audience size, posting time, and content format heavily influence engagement. Furthermore, the absolute engagement scores are totals and not normalized for audience size (like followers), meaning platforms with larger inherent reach might show higher totals regardless of hashtag efficiency. The data also doesn't reflect the relevance, popularity, or quality of the specific hashtags used, which is crucial for optimization.
![Image](https://github.com/user-attachments/assets/2ef6f0fb-a6e3-4eea-89c8-070d11dcfef1)  

## Content Type Engagement
Breakdown of engagement scores by content type reveals an exceptionally balanced distribution of engagement across content formats, with Carousel (25.53%), Image (25.50%), and Video (25.01%) commanding nearly identical shares, separated by a remarkably narrow margin of just 0.52%. This near-perfect parity across the three primary visual formats is unusual and suggests that, within this specific context, the audience engages with Carousels, Images, and Videos almost equally. Collectively, these visual formats dominate, accounting for 75.04% of the total 44,929,167 engagements, significantly outperforming Text-only content (23.97%). This underscores a clear preference for multimedia experiences, though Text remains a substantial contributor. The minimal difference in performance implies that content quality, relevance, or messaging might be a stronger driver of engagement than the specific format choice itself. However, Carousel's slight lead could indicate a subtle preference for multi-frame storytelling or educational content. The viability of Text content, despite its lower share, suggests it still plays an important role, likely for concise updates or information delivery. 
![Image](https://github.com/user-attachments/assets/b1122d4a-1213-4e31-9471-22e84df045db)

# Recommendations
**LinkedIn: Leverage Hidden Value**  
Despite ranking third in likes (5.99M), LinkedIn’s unexpected leadership in shares (3.19M) and strong comments (1.88M) signals untapped potential. Shift focus from vanity metrics (likes) to *niche B2B content* that fuels professional dialogue and sharing. Pilot an employee advocacy program to amplify organic reach, targeting its high-engagement professional user base.  

**Twitter: Optimize for Efficiency**  
Twitter’s second-place likes (6.25M) but lagging shares/comments indicate its role as a "validation platform." Double down on *text and static images* (its 18.3%+ engagement rate formats) for quick-scrolling users. Reduce investment in video (17.74% engagement rate) and reallocate resources to Instagram/LinkedIn video instead.  

**Facebook: Strategic Intervention or Exit**  
Facebook’s consistent last-place performance (5.9M likes, 3.01M shares, 1.79M comments) demands urgent action:  
- **Test a 6-month pivot:** Focus exclusively on *video* (its sole strength: 18.16% engagement rate), sunsetting carousels (16.73%).  
- **If no improvement:** Deprioritize Facebook entirely, reallocating 70% of its budget to Instagram/Twitter and 30% to LinkedIn.  
- **Audience diagnosis:** Run sentiment analysis to determine if engagement gaps stem from irrelevant content or aging demographics.  

**Twitter: Monetize the Text-Image Nexus**  
Immediately shift 70% of video resources to text and static image production. Develop threaded thought-leadership series and data-rich infographics to exploit its 18.3%+ engagement sweet spot. Pilot “Twitter White Papers” – text-heavy carousels with downloadable assets – to bridge its carousel-video gap.  

**Instagram: Double Down on Video-Image Equilibrium**  
Maintain the 50/50 balance between video and image content but inject Twitter-inspired text tactics: overlay statistics on Reels, convert blog highlights into Stories text teasers. Abandon standalone text posts – repurpose them as video scripts or carousel captions.  

**Facebook: Surgical Format Correction**  
Terminate carousel production immediately (saving 23% creative resources). Redirect all savings to <60-second vertical videos optimized for sound-off viewing. Test “text-light” images (single statistic + minimal copy) to leverage its 17.85% image engagement without triggering carousel penalties.  

**LinkedIn: Content Sophistication Overhaul**  
Conduct audience research to diagnose why professional content underperforms. Pilot three fixes: 1) Convert text posts into video narration (e.g., “Slide breakdown with CEO commentary”), 2) Inject Twitter-grade data visualization into carousels, 3) Add “Industry Debate” prompts to all images. If engagement stays sub-17.5%, reduce posting frequency by 40% and focus on premium video/webinar content.  

**Instagram: Capitalize on Dominance**  
Reallocate 15-20% of Facebook’s budget to Instagram to amplify its proven strengths in driving likes (6.76M), shares (3.22M), and comments (1.96M). Prioritize *Reels and carousel content*—Instagram’s top-performing formats—to exploit its algorithm advantage. Launch interactive campaigns (polls, Q&As) to further boost comment volume, deepening community investment.  

**Expand Hashtag Volume**
- Increase Facebook hashtags by 15% (from 11,474 to 13,200) to match Instagram volume.
- Maintain Twitter/LinkedIn growth trajectory

**Instagram Hashtag Lab**
- Study high-efficiency hashtags (342 engagement/tag) for cross-platform replication.
- Develop hashtag clusters around top-performance content themes


