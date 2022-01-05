竞赛：https://www.drivendata.org/competitions/66/flu-shot-learning/

[参赛协议](./Flu Shot Learning 协议.md)

# Overview

**用人们分享的关于他们的背景、观点和健康行为的信息来预测人们是否接种了H1N1和季节性流感疫苗吗？**

这项电话调查询问受访者是否接种过H1N1和季节性流感疫苗，并询问有关他们自己的问题。这些额外的问题包括他们的社会，经济和人口背景，对疾病风险和疫苗有效性的看法，以及减轻传播的行为。更好地了解这些特征如何与个人疫苗接种模式相关联，可以为未来的公共卫生工作提供指导。



**练习赛，旨在让各级参与者都可以参加。**

==比赛结束日期：2022年11月30日==



# Problem description

## Labels

For this competition, there are two target variables:

- `h1n1_vaccine` - Whether respondent received H1N1 flu vaccine.
- `seasonal_vaccine` - Whether respondent received seasonal flu vaccine.

Both are binary variables: = No; = Yes. Some respondents didn't get either vaccine, others got only one, and some got both. This is formulated as a multilabel (and *not* multiclass) problem.`0``1`

## The features in this dataset

For this competition, there are two target variables:

- `h1n1_vaccine` - Whether respondent received H1N1 flu vaccine.
- `seasonal_vaccine` - Whether respondent received seasonal flu vaccine.

Both are binary variables: = No; = Yes. Some respondents didn't get either vaccine, others got only one, and some got both. This is formulated as a multilabel (and *not* multiclass) problem.`0``1`



## The features in this dataset

------

You are provided a dataset with 36 columns. The first column` respondent_id`is a unique and random identifier. The remaining 35 features are described below.

For all binary variables: `0` = No; `1` = Yes.

- `h1n1_concern` \- **Level** of concern about the H1N1 flu.
  
  - `0` = Not at all concerned; `1` = Not very concerned; `2` = Somewhat concerned; `3` = Very concerned

- `h1n1_knowledge` \- **Level** of knowledge about H1N1 flu.
  
  - `0` = No knowledge; `1` = A little knowledge; `2` = A lot of knowledge.

- `behavioral_antiviral_meds` - Has taken antiviral medications. (binary)

- `behavioral_avoidance` - Has avoided close contact with others with flu-like symptoms. (binary)

- `behavioral_face_mask` - Has bought a face mask. (binary)

- `behavioral_wash_hands` - Has frequently washed hands or used hand sanitizer. (binary)

- `behavioral_large_gatherings` - Has reduced time at large gatherings. (binary)

- `behavioral_outside_home` - Has reduced contact with people outside of own household. (binary)

- `behavioral_touch_face` - Has avoided touching eyes, nose, or mouth. (binary)

- `doctor_recc_h1n1` - H1N1 flu vaccine was recommended by doctor. (binary)

- `doctor_recc_seasonal` - Seasonal flu vaccine was recommended by doctor. (binary)

- `chronic_med_condition` - Has any of the following chronic medical conditions: asthma or an other lung condition, diabetes, a heart condition, a kidney condition, sickle cell anemia or other anemia, a neurological or neuromuscular condition, a liver condition, or a weakened immune system caused by a chronic illness or by medicines taken for a chronic illness. (binary)

- `child_under_6_months` - Has regular close contact with a child under the age of six months. (binary)

- `health_worker` - Is a healthcare worker. (binary)

- `health_insurance` - Has health insurance. (binary)

- `opinion_h1n1_vacc_effective`  \- Respondent's opinion about H1N1 vaccine effectiveness.
  
  - `1` = Not at all effective; `2` = Not very effective; `3` = Don't know; `4` = Somewhat effective; `5` = Very effective.

- `opinion_h1n1_risk` \- Respondent's opinion about risk of getting sick with H1N1 flu without vaccine.
  
  - `1` = Not at all effective; `2` = Not very effective; `3` = Don't know; `4` = Somewhat effective; `5` = Very effective.

- `opinion_h1n1_sick_from_vacc` \- Respondent's worry of getting sick from taking H1N1 vaccine.
  
  - `1` = Not at all worried; `2` = Not very worried; `3` = Don't know; `4` = Somewhat worried; `5` = Very worried.

- `opinion_seas_vacc_effective` \- Respondent's opinion about seasonal flu vaccine effectiveness.
  
  - `1` = Not at all effective; `2` = Not very effective; `3` = Don't know; `4` = Somewhat effective; `5` = Very effective.

- `opinion_seas_risk`
  
   \- Respondent's opinion about risk of getting sick with seasonal flu without vaccine.

  - `1` = Very Low; `2` = Somewhat low; `3` = Don't know; `4` = Somewhat high; `5` = Very high.

- `opinion_seas_sick_from_vacc`
  
   \- Respondent's worry of getting sick from taking seasonal flu vaccine.

  - `1` = Not at all worried; `2` = Not very worried; `3` = Don't know; `4` = Somewhat worried; `5` = Very worried.

- `age_group` - Age group of respondent.

- `education` - Self-reported education level.

- `race` - Race of respondent.

- `sex` - Sex of respondent.

- `income_poverty` - Household annual income of respondent with respect to 2008 Census poverty thresholds.

- `marital_status` - Marital status of respondent.

- `rent_or_own` - Housing situation of respondent.

- `employment_status` - Employment status of respondent.

- `hhs_geo_region` - Respondent's residence using a 10-region geographic classification defined by the U.S. Dept. of Health and Human Services. Values are represented as short random character strings.

- `census_msa` - Respondent's residence within metropolitan statistical areas (MSA) as defined by the U.S. Census.

- `household_adults` - Number of *other* adults in household, top-coded to 3.

- `household_children` - Number of children in household, top-coded to 3.

- `employment_industry` - Type of industry respondent is employed in. Values are represented as short random character strings.

- `employment_occupation` - Type of occupation of respondent. Values are represented as short random character strings.

## Performance metric

(ROC AUC) for each of the two target variables. The mean of these two scores will be the overall score.

In Python, you can calculate this using [`sklearn.metrics.roc_auc_score`](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_auc_score.html) for this multilabel setup with the default parameter.`average="macro"`

## Submission format

The first several lines of the file that you submit would look like:`.csv`

```
respondent_id,h1n1_vaccine,seasonal_vaccine
26707,0.5,0.7
26708,0.5,0.7
26709,0.5,0.7
26710,0.5,0.7
26711,0.5,0.7
```



## data

| File                                                         | Description                  |
| :----------------------------------------------------------- | :--------------------------- |
| [Submission Format](https://drivendata-prod.s3.amazonaws.com/data/66/public/submission_format.csv?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARVBOBDCYVI2LMPSY%2F20220105%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20220105T024331Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=ed01f2980cbe695a9f583bf2dbfa7fa614ea658dec58d0cd4a7000a25d0863e4) | Submission Format            |
| [Training Features](https://drivendata-prod.s3.amazonaws.com/data/66/public/training_set_features.csv?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARVBOBDCYVI2LMPSY%2F20220105%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20220105T024331Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=d325ff475da12f10de95a85133b4bb1e659ce6d19835a24f5baa980d3d33e7dd) | Training set features.       |
| [Training Labels](https://drivendata-prod.s3.amazonaws.com/data/66/public/training_set_labels.csv?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARVBOBDCYVI2LMPSY%2F20220105%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20220105T024331Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=dae139a74154125e704c7b43f4323e38888570efecbcd41fc3d05db9d0e8895a) | Labels for the training set. |
| [Test Features](https://drivendata-prod.s3.amazonaws.com/data/66/public/test_set_features.csv?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIARVBOBDCYVI2LMPSY%2F20220105%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20220105T024331Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=41ba5026ac507cc644ff2f09a90ae2435c29319c56bc77a88cf8905ce361ec85) | Test set features.           |



## Citing

If you publish work, please cite [the DrivenData platform paper](https://arxiv.org/abs/1606.07781).

