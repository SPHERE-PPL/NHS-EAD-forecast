# SPHERE-PPL Forecasting Contest - NHS Acute Patient Harm Forecasting


## Introduction

This competition focuses on forecasting severe patient harm resulting from delays in admitting patients from the Emergency Department (ED). Delays occur when a patient has been deemed to require hospital admission but no beds are immediately available.

Recent research in the Bristol NHS healthcare system has shown that every four hours of ED admission delay is associated with an 8% increase in the odds of 30-day mortality (Howlett et al., 2026). Applied to recent data, this equates to an estimated 25 deaths per month that could be considered avoidable if there were no ED admission delays.

The aim of the competition is to develop an algorithm capable of predicting the number of avoidable deaths over the next ten days using near-real-time data. The winning model is intended for daily implementation in the Bristol NHS, providing managers with advance warning to enable pre-emptive action.

All data used in this project are drawn from real-world hospital records.


## Data

### Development dataset

The target outcome is daily estimated avoidable deaths, pre-calculated from ED admission delays and patient attributes across the Bristol NHS healthcare system, with no missing data.

The 220 candidate explanatory variables vary in time frequency of recording, from every day to every 15 minutes. Some have records for every time-point within the 16 March 2023 to 30 September 2025 period whilst others have only partial recordings and missing data-points. 

For any winning model to be integrated into NHS systems and deployed operationally, it must be developed using only the data provided. Therefore integrating external datasets is not allowed as part of this contest. 

A glossary and data summary are provided in the Appendix.


### Assessment dataset

The assessment dataset will have the same format as the development dataset, containing the target variable and 220 candidate explanatory variables over the period from 1 October 2025 to 17 February 2026; in the current development dataset, this period is represented by dummy values (-9999).

Note: You must have Git Large File Storage (Git LFS) installed in order to access the dataset.


## Contest Participation

### Joining the contest & Getting Started

In order to join the contest, you will need to fork or download the repo.

To fork the repo, simply press the "fork" button, which can be found at the top of this github page. A step-by-step guide can be found [here](https://scribehow.com/shared/Forking_a_SPHERE-PPL_Forecasting_Contest_Repository_on_GitHub__o_bLCyQlTsO0o5YCmGsk8Q).

To download the data without a github account, click the code box dropdown and download a zip of the data directly to your computer.


### Rules

-   The algorithm must be coded in either R or Python.
-   The computational running time to produce one set of 10-day forecasts must be under one hour on a standard desktop computer.
-   All entries must be loaded into a public Github repo.
-   All entries must follow the submission formats outlined below.
-   All entries must include a max 1000 word report to accompany the forecast analyses. This can be as a separate PDF/hmtl or incorporated into a quarto/jupyter notebook.
-   Participants must submit their final algorithms by 5 June 2026. 
-   The assessment dataset will be released on the 6 June 2026, upon which competitors must apply their submitted algorithms in generating forecasts over the assessment period from October 2025 to February 2026.
-   The final deadline for participants to submit their forecasts is 4 July 2026. Final submissions will be compared with those made prior to the release of the assessment dataset to verify that the algorithms have remained consistent.


### How to Win!

There are 140 days within the 1 October 2025 to 17 February 2026 range of the assessment dataset, meaning there are 131 sliding 10-day forecast periods (e.g., 1–10 Oct 2025 to 7–17 Feb 2026). 

Competitors must use their submitted algorithm to generate forecasts for each day in all 131 periods. Forecast accuracy will be evaluated using Mean Squared Error (MSE) over the 1–5-day and 6–10-day horizons, as defined below:

**MSE for days 1–5:**
MSE₁–₅d = (1 / (173 × 5)) × Σₚ₌₁¹⁷³ Σ𝑑₌₁⁵ (Yₚ,𝑑 - Ŷₚ,𝑑)²

**MSE for days 6–10:**
MSE₆–₁₀d = (1 / (173 × 5)) × Σₚ₌₁¹⁷³ Σ𝑑₌₆¹⁰ (Yₚ,𝑑 - Ŷₚ,𝑑)²

Here, Yₚ,𝑑 is the observed value and Ŷₚ,𝑑 is the forecast for day d within period p. For example, Y₄,₃ corresponds to 6 Oct 2025 (the third day of the fourth period), and note that Y₄,₃ = Y₁,₆ = Y₂,₅ = Y₃,₄.

Forecasts for days D+1 to D+10 may use only data available up to midday on day D.

Because the target variable has a three-day reporting lag, any algorithms using past values of the target variable can only use data before three days past. Specifically, if today is day D (Saturday) then only data up to and including day D-3 (Wednesday) can be used. This relates only to the target outcome variable. 

The algorithm may be recalibrated using new data from the assessment dataset when generating forecasts. While the submitted code cannot change, model structures or parameters may be dynamically updated based solely on the new data applied through the existing code.

Awards will be given across two categories:

1. One prize will be given for the lowest MSE_1to5d. 

2. One prize will be given for the lowest MSE_6to10d.

All winning teams will be assessed by the competition authors to ensure that the reported MSEs can be replicated with the submitted models, and to check all above restrictions are satisfied.

The winners will be selected by the SPHERE-PPL Team and will be invited to present their forecasts at the next Annual Meeting, with travel covered by the project.


### How to Submit

If you forked the repo, congratulations, you have almost entered the contest! Make sure to update your repo with your results! Forecasts and reports should be saved into the submission folder, matching the template found within. We will run the [Forecast AggregatoR](https://github.com/SPHERE-PPL/Forecast-AggregatoR) the day following the close of the contest and your repo will be collated with the entries.

If you did not fork the repo, please send an email to [info\@sphere-ppl.org](mailto:info@sphere-ppl.org) with a link to your public github repo where your forecast and report are stored. These will then be collated with the other entries.

Please raise any questions or matters of clarification on the aforementioned GitHub page as an ‘issue’. These will be answered and all competitors will be able to see the response.


### Beyond the Contest

The competition authors would be pleased to co-author an academic paper covering the implementation of the algorithm. This can include model development, or that may be covered in a separate paper that the winning team are welcome to independently author.


## Connect with the Community

You can join our Zulip [here](https://sphereppl.zulipchat.com/join/olwtpi7g3wbyh5mxv4uwipaw/) and check out our events page to see the next online catch-up.


## License

![CC-BYNCSA-4](https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png)

Unless otherwise noted, the content in this repository is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-nc-sa/4.0/).

For the data sets in the *data/* folder, please see [*data/README.md*](data/README.md) for the applicable copyrights and licenses.
