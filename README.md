# HR Analytics: Employee Presence & Working Preferences

## Project Background
Working as a Data Analyst at **Recruiter Wings**, a software and data solutions company. The company operates on a hybrid service-based business model. 

In this role, I was tasked by the HR Manager to transition from manual Excel tracking to a data-driven automated dashboard. The core objective is to monitor employee presence, understand work-from-home (WFH) preferences, and track sick leave (SL) trends to optimize office space utilization and plan team engagement activities.

**Insights and recommendations are provided on the following key areas:**
* **Presence Insights:** Overall attendance trends and daily presence percentages.
* **Work From Home (WFH) Analysis:** Preference patterns for remote work.
* **Sick Leave Monitoring:** Tracking wellness trends and potential health "hot zones."
* **Strategic Capacity Planning:** Optimizing infrastructure and office resource costs.

---

* The Power Query M-codes used to transform and clean the data can be found here [[Link]].
* Targeted DAX measures regarding various business questions can be found here :
[Link to Queries](https://github.com/ayaankhan21/HR-Analytics/blob/main/DAX%20Queries.txt)

* An interactive Power BI dashboard used to report and explore HR trends can be found here 
![Dashboard Preview](https://github.com/ayaankhan21/HR-Analytics/blob/main/dashboard.JPG).

---

## Data Structure & Initial Checks
The company's primary attendance data was provided in an Excel workbook consisting of multiple sheets (April, May, June) and a reference key table. The combined dataset covers over 3 months of daily records.

* **Monthly Attendance Sheets:** Contains randomized employee names, codes, and daily attendance status.
* **Attendance Key Table:** A reference table defining codes (P = Present, WFH = Work from Home, SL = Sick Leave, HSL = Half Sick Leave, WO = Weekly Off, HO = Holiday).
* **Final Transformed Table:** A long-format table created via Power Query (Unpivoted) containing columns: `Employee Code`, `Name`, `Date`, `Attendance Value`, `WFH Count`, and `SL Count`.



---

## Executive Summary

### Overview of Findings
The analysis reveals that while overall presence remains stable around **91-93%**, there is a visible declining trend as the summer months approach, accompanied by a rise in remote work preferences. Stakeholders should note that **Fridays** are the most frequent WFH days (approx. 15%), while **Mondays** see the highest physical presence in the office. This suggests that "Hybrid-Friday" policies and "Monday-Engagement" events would align best with natural employee behavior.



---

## Insights Deep Dive

### Category 1: Presence Insights
* **Overall Attendance:** Presence percentage averaged between 91% and 93% across the three months analyzed.
* **Monthly Trend:** A slight decline in office presence was observed from April to June as WFH preferences increased.
* **Day-of-Week Peak:** Mondays consistently show the highest presence rates, making them the most productive days for in-office collaboration.
* **Holiday Impact:** Mid-week presence remains stable but dips significantly during public holidays or extended long weekends.



### Category 2: Work From Home (WFH) Analysis
* **Growing Preference:** WFH preference increased from 11% in May to 14.2% in June.
* **Friday Logic:** Friday is the "peak" remote work day, with roughly 15% of the workforce choosing to work from home.
* **Weekend Correlation:** A significant portion of the workforce prefers to combine WFH with the weekend, suggesting a desire for flexibility around travel.
* **Role-Based WFH:** Certain individual employees were identified with 100% WFH rates, indicating specific roles are already effectively fully remote.



### Category 3: Sick Leave (SL) Monitoring
* **Baseline Health:** Sick leave percentages remained low (approx. 1.10%) but showed a marginal upward trend toward June.
* **Wellness Trends:** No immediate "spikes" were detected, indicating a generally healthy workforce during the period.
* **Granular Tracking:** Tracking SL allowed HR to identify employees with 0% presence due to long-term leave or "Leave Without Pay" (HLWP).
* **Seasonality:** Data suggests that health-related absences may spike during specific seasonal transitions, which can now be monitored in real-time.



### Category 4: Operational Planning
* **Underutilization:** Office capacity is currently underutilized on Fridays due to high WFH volume.
* **Maintenance Scheduling:** Infrastructure maintenance (electricity, repairs) can be scheduled for Fridays to minimize disruption.
* **Data Integrity:** The "Matrix" view identified employees who may have left the company but were still appearing in attendance sheets with 0% presence.
* **Cost Efficiency:** Hybrid rotation planning could potentially save up to 20% on rental space costs by optimizing daily desk occupancy.

---

## Recommendations

Based on the insights above, I recommend the **HR and Operations teams** consider the following:

1. **Strategic Scheduling:** Schedule team-building lunches and collaborative meetings on **Mondays**, as this day has the highest natural office attendance.
2. **Hybrid Rotation:** Implement a **Rotational Hybrid Model** where specific teams take turns working from home to reduce the need for larger office rentals.
3. **Operational Maintenance:** Move major office maintenance and IT upgrades to **Fridays** to take advantage of the 15% lower occupancy.
4. **Capacity Planning:** Use the presence trends to plan software release cycles; avoid heavy deadlines during months where seasonality shows high absenteeism.
5. **Real-time Monitoring:** Set up **Data Alerts** in Power BI to notify HR via email if the presence percentage drops below a critical threshold (e.g., 70%).

---

## Assumptions and Caveats
* **Non-Working Days:** Attendance records with "Weekly Off" (WO) and "Holiday" (HO) were excluded from the total working days calculation to ensure accurate percentage metrics.
* **Weighted Values:** Half-day WFH (HWFH) or Half-day Sick Leave (HSL) were counted as **0.5** in the quantitative measures to reflect actual work hours accurately.
* **Data Gaps:** Data for the end of June contained some blank cells; these were filtered out to prevent trend lines from dropping to zero artificially.
* **Data Cleaning:** The "unpivoting" process in Power Query assumes that any non-date column headers in the source Excel (after Name/Code) are errors and were removed via "Remove Errors."




