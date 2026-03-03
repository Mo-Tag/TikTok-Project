# 🚀 TikTok Claims vs. Opinions: Exploratory Data Analysis

**Distinguishing Viral Misinformation from Authentic Expression — An EDA Portfolio Project**

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org)
[![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?style=flat-square&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![Seaborn](https://img.shields.io/badge/Seaborn-0.13+-FF6F00?style=flat-square&logo=seaborn&logoColor=white)](https://seaborn.pydata.org)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-11557c?style=flat-square&logo=matplotlib&logoColor=white)](https://matplotlib.org)
[![Tableau](https://img.shields.io/badge/Tableau-Public-1F77B4?style=flat-square&logo=tableau&logoColor=white)](https://public.tableau.com)

**Status**: Completed | **Portfolio Highlight** | **Google Advanced Data Analytics**

---

## 📌 Executive Summary (Ready for Leadership)

**Claim videos dominate TikTok’s attention economy.**

Despite nearly equal numbers of claim and opinion videos in the dataset, **claim videos account for the overwhelming majority of total views, likes, shares, and downloads**. Their median view count is **>100× higher** than opinion videos (501,555 vs. 4,953).

Authors who post claims are dramatically more likely to face bans or review — yet their content still achieves outsized reach. High-engagement metrics are a powerful early signal of claim status.

**Key takeaway for TikTok leadership**: Engagement velocity is not neutral. It is a strong proxy for content veracity. These insights directly inform the design of a robust claim-classification model and proactive moderation strategy.

Visualizations were deliberately crafted with **maximum accessibility** — high-contrast palettes, clear labeling, and simple layouts suitable for screen readers and stakeholders with visual impairments.

---

## 🎯 Business Problem & Impact

TikTok’s Data Science team needed clarity on what separates **claim videos** (potentially harmful/misleading) from **opinion videos** (personal viewpoints).  

This EDA delivers:
- Immediate, board-room-ready visualizations
- Quantified differences in engagement behavior
- Outlier transparency for modeling decisions
- A production-grade foundation for the next phase: predictive classification

**Business value**: Faster detection of harmful content, reduced manual review workload, and data-backed policy decisions.

---

## 📊 Dataset

- **File**: `tiktok_dataset.csv`
- **Size**: ~19,382 videos (exact shape confirmed via `.shape`)
- **Key Variables**:
  - `claim_status` (target: claim / opinion)
  - Engagement: `video_view_count`, `video_like_count`, `video_comment_count`, `video_share_count`, `video_download_count`
  - Content: `video_duration_sec`
  - Author: `author_ban_status`, `verified_status`

---

## 🛠️ Tools & Technologies

| Layer              | Tools                              |
|--------------------|------------------------------------|
| Data Manipulation  | pandas, NumPy                      |
| Visualization      | Matplotlib, Seaborn                |
| Interactive Dash   | Tableau Public                     |
| Framework          | PACE (Plan → Analyze → Construct → Execute) |
| Environment        | Jupyter Notebook, GitHub           |

---

## 🧭 Methodology — PACE Framework

**Plan**  
Defined success as “clear, accessible visuals that reveal claim/opinion distinctions and support modeling decisions.”

**Analyze**  
- Full data profiling (`.head()`, `.info()`, `.describe()`, `.shape`)
- Missing-value audit
- Data-type validation against Tableau Data Source

**Construct**  
Built 15+ publication-quality visualizations in Python + full Tableau dashboard.

**Execute**  
- Outlier detection using **median + 1.5×IQR** (robust for skewed social-media data)
- Statistical validation of insights
- Executive summary & stakeholder narrative

---

## 📈 Key Visualizations & Breakthrough Insights

### 1. Core Engagement Distributions (Python)
<img width="617" height="242" alt="image" src="https://github.com/user-attachments/assets/b71fd2cb-8a7b-412e-be85-9611c33b56d5" />

**All videos 5–60 seconds** — perfectly uniform distribution.

<img width="719" height="469" alt="image" src="https://github.com/user-attachments/assets/1ad103ca-5531-40fd-af26-c3cce797305b" />

**Highly right-skewed** — >50% of videos <100k views; long tail of viral hits.

<img width="836" height="581" alt="image" src="https://github.com/user-attachments/assets/7d889bf4-da47-405f-b134-b1eb91483cd8" />

Similar skew + right tail — classic viral behavior.

(Full set: comment, share, download counts all exhibit extreme right skew — **small number of videos drive the majority of platform activity**.)

### 2. Claim vs Opinion — The Smoking Gun
<img width="463" height="402" alt="image" src="https://github.com/user-attachments/assets/03c6d887-311e-4ebd-93fe-2759e5d8ae62" />

**Claims dominate total views** despite equal volume.

<img width="733" height="469" alt="image" src="https://github.com/user-attachments/assets/9513ea26-247e-4ead-8d91-4ce239e28efd" />

Banned & under-review authors average **many times** more views than active authors.

<img width="939" height="581" alt="image" src="https://github.com/user-attachments/assets/fc7bfdb3-1068-4173-a4a9-d3fb3013cd5c" />

Opinion authors are overwhelmingly active; claim authors show elevated ban/review rates.

<img width="939" height="581" alt="image" src="https://github.com/user-attachments/assets/c56bb5d5-8672-4f6c-9dd0-ca58d3b43da4" />

Verified users strongly prefer posting opinions.

### 3. Engagement Separation (Scatter)
<img width="850" height="548" alt="image" src="https://github.com/user-attachments/assets/5db0da3d-edbc-4749-89e2-d1b66ebc1f15" />

**Clear visual clustering** — claims occupy the high-engagement quadrant.

### 4. Outlier Analysis (Production-Grade)
```python
Number of outliers (median + 1.5×IQR):
• video_view_count:     2,343
• video_like_count:     3,468
• video_share_count:    3,732
• video_download_count: 3,733
• video_comment_count:  3,882
