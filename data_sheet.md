# Datasheet

This study uses the the AIDS Clinical Trials Group Study 175 Dataset which contains healthcare statistics and categorical information about patients who have been diagnosed with AIDS. This dataset was initially published in 1996 [[1]](https://archive.ics.uci.edu/dataset/890/aids+clinical+trials+group+study+175).

## Motivation

The dataset was created to examine the performance of different types of AIDS treatments.

**The full list of contributors** to the collection of this dataset is given in the Appendix of the original research paper [[2]](https://www.nejm.org/doi/pdf/10.1056/NEJM199610103351501?articleTools=true).

**Data collection was funded by**
- AIDS Clinical Trials Group of the National Institute of Allergy and Infectious Diseases
- General Research Center units funded by the National Center for Research Resources

## Composition

- The dataset includes 2139 instances.

- The data represents health records of AIDS patients from the USA.

- The dataset is anonymised therefore, while it contains sensitive patient data (race, gender, sexual orientation, substance use), raises no GDPR concerns as individual patients cannot be identified.

- There is no missing data in the dataset.

### List of fields

| No | ID     | Integer | description                                          |
|---|---|---|---|
| 0    | pidnum | Integer | Patient ID                                          |
| 1    | cid   | Binary   | Censoring indicator (1 = failure, the patient died, 0 = censoring (stopped following))  |
| 2    | time  | Integer | Time to failure or censoring                        |
| 3    | trt  | Binary   | treatment indicator (0 = ZDV (zidovudine) only; 1 = ZDV + ddI (didanosine), 2 = ZDV + Zal (zalcitabine), 3 = ddI only)  |
| 4    | age  | Integer | Age (yrs) at baseline                             |
| 5    | wtkg  | Continuous | Weight (kg) at baseline                           |
| 6    | hemo  | Binary   | Hemophilia (0=no, 1=yes)                          |
| 7    | homo  | Binary   | Homosexual activity (0=no, 1=yes)                  |
| 8    | drugs | Binary   | History of IV drug use (0=no, 1=yes)               |
| 9    | karnof | Integer | Karnofsky score (on a scale of 0-100)               |
| 10   | oprior | Binary   | Non-ZDV antiretroviral therapy pre-175 (0=no, 1=yes)  |
| 11   | z30  | Binary   | ZDV in the 30 days prior to study (0=no, 1=yes)      |
| 12   | zprior | Binary   | ZDV prior to study (0=no, 1=yes)                     |
| 13   | preanti | Integer | Number of days days pre-study anti-retroviral therapy             |
| 14   | race  | Integer | Race (0=White, 1=Non-white background)                          |
| 15   | gender | Binary   | Gender (Sex) (0=Female, 1=Male)                                 |
| 16   | str2  | Binary   | Antiretroviral history (0=naive, 1=experienced)    |
| 17   | strat  | Integer | Antiretroviral history stratification (1='Antiretroviral Naive',2='> 1 but <= 52 weeks of prior antiretroviral therapy',3='> 52 weeks)  |
| 18   | symptom | Binary   | Symptomatic indicator (0=asymptomatic, 1=symptomatic)             |
| 19   | treat  | Binary   | Treatment indicator (0=ZDV only, 1=others)         |
| 20   | offtrt | Binary   | indicator of off-trt before 96+/-5 weeks (0=no,1=yes)  |
| 21   | cd40  | Integer | CD4 at baseline                                   |
| 22   | cd420 | Integer | CD4 at 20+/-5 weeks                                |
| 23   | cd80  | Integer | CD8 at baseline                                   |
| 24   | cd820 | Integer | CD8 at 20+/-5 weeks        

cid (whether the patient died) is the output field, all other fields are features.

Notes: 
**The Karnofsky Performance Status Scale (Karnofsky Score)** is a standard way of measuring the degree of patient well-being and activities of daily life in individuals with cancer or other diseases. It is scored from 0 to 100, with 100 being "perfect" health and 0 being death.

**CD4 and CD8** re types of glycoprotein molecules found on the surface of certain white blood cells, called T cells. They play a crucial role in the immune system's ability to identify and respond to different pathogens.

## Collection process

CTG 175 was a randomized, double-blind, placebo-controlled trial to compare monotherapy with zidovudine or didanosine with combination therapy with zidovudine and didanosine or zidovudine and zalcitabine in HIV-1–infected subjects with CD4 cell counts between 200 and 500 per cubic millimeter. The primary study end point was a 50 percent decline in the CD4 cell count, an event indicating progression to the acquired immunodeficiency syndrome (AIDS), or death. Secondary end points were an AIDS-defining event or death, death alone, and the occurrence of adverse events (signs, symptoms, or laboratory abnormalities) defined as severe or worse according to the ACTG grading scheme.

The dataset was collected pre November 1995 (study completion date) [[3]](https://clinicaltrials.gov/study/NCT00000625).

## Preprocessing/cleaning/labelling

- No information on this.
- Recommended splits are cross validation or a single train-test split [[1]](https://archive.ics.uci.edu/dataset/890/aids+clinical+trials+group+study+175).
 
## Uses

- The original use of this dataset was to inform a study on different AIDS treatments [[1]](https://archive.ics.uci.edu/dataset/890/aids+clinical+trials+group+study+175).

- Since the datset was collected, the available treatments for people with HIV evolved significantly. The study reflects on the state-of-the art in HIV treatment at the time. As such, the treatments used in this study might not be often used/considered anymore.

## Distribution

- It is freely available at [[1]](https://archive.ics.uci.edu/dataset/890/aids+clinical+trials+group+study+175)
- Also published at [[3]](https://clinicaltrials.gov/study/NCT00000625)
- Terms and conditions of use apply [[4]](https://classic.clinicaltrials.gov/ct2/about-site/terms-conditions#Use)
- The above including:
  In any publication or distribution of these data, you should:

    -Attribute the source of the data as ClinicalTrials.gov
    -Update the data such that they are current at all times
    -Clearly display the date the data were processed by ClinicalTrials.gov
    -State any modifications made to the content of the data, along with a complete description of the modifications

## Maintenance

- Current Responsible Party: National Institute of Allergy and Infectious Diseases (NIAID)