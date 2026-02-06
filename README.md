# SPHERE-PPL Environmental Forecasting Contest - NHS Estimated Avoidable Deaths

## Introduction[^readme-1]

This competition focuses on forecasting severe patient harm resulting from delays in admitting patients from the Emergency Department (ED). Delays occur when a patient has been deemed to require hospital admission but no beds are immediately available.

Recent research in the Bristol NHS healthcare system has shown that every four hours of ED admission delay is associated with an 8% increase in the odds of 30-day mortality. Applied to recent data, this equates to an estimated 25 deaths per month that could be considered avoidable if there were no ED admission delays.

The aim of the competition is to develop an algorithm capable of predicting the number of avoidable deaths over the next ten days using near-real-time data. The winning model is intended for daily implementation in the Bristol NHS, providing managers with advance warning to enable pre-emptive action.

All data used in this project are drawn from real-world hospital records.

## Forecasting Outputs

For this contest, we are looking to forecast Estimated Number of Avoidable Deaths across 1 - 10 day horizons. Forecasts and reports should be saved into the submission folder, matching the template found within.

## Joining the contest & Getting Started

In order to join the contest, you will need to fork or download the repo.

To fork the repo, simply press the "fork" button, which can be found at the top of this github page. A step-by-step guide can be found [here](https://scribehow.com/shared/Forking_a_SPHERE-PPL_Forecasting_Contest_Repository_on_GitHub__o_bLCyQlTsO0o5YCmGsk8Q).

To download the data without a github account, click the code box dropdown and download a zip of the data directly to your computer.

![Fork or Download](https://github.com/SPHERE-PPL/forecasting-contest-template/blob/main/contest_media/fork_button.png)


## Rules

-   Any coding languages are allowed but all analyses must be reproducible by the panel.
-   All entries must be loaded into a public Github repo.
-   All entries must follow the submission formats outlined below.
-   All entries must include a max 1000 word report to accompany the forecast analyses. This can be as a separate PDF/hmtl or incorporated into a quarto/jupyter notebook.
-   Participants must submit their final algorithms by 5 April 2026. 
-   The assessment dataset will be released on the 6 April 2026, upon which competitors must apply their submitted algorithms in generating forecasts over the assessment period from October 2025 to March 2026.
-   The final deadline for participants to submit their forecasts is 20 April 2026

## How to Win!

Awards will be given across two categories:

1. One prize will be given for the lowest MSE_1to5d. 

2. One prize will be given for the lowest MSE_6to10d.

All winning teams will be assessed by the competition authors to ensure that the reported MSEs can be replicated with the submitted models, and to check all above restrictions are satisfied.

The winners will be selected by the SPHERE-PPL Team and will be invited to present their forecasts at the next Annual Meeting, with travel covered by the project.

## How to Submit

If you forked the repo, congratulations, you have almost entered the contest! Make sure to update your repo with your results! We will run the [Forecast AggregatoR](https://github.com/SPHERE-PPL/Forecast-AggregatoR) the day following the close of the contest and your repo will be collated with the entries.

If you did not fork the repo, please send an email to [contest\@sphere-ppl.org](mailto:contest@sphere-ppl.org) with a link to your public github repo where your forecast and report are stored. These will then be collated with the other entries.

## Connect with the Community

You can join our Zulip [here](https://sphereppl.zulipchat.com/join/olwtpi7g3wbyh5mxv4uwipaw/) and check out our events page to see the next online catch-up.

## License

![CC-BYNCSA-4](https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png)

Unless otherwise noted, the content in this repository is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-nc-sa/4.0/).

For the data sets in the *data/* folder, please see [*data/README.md*](data/README.md) for the applicable copyrights and licenses.
