# Datasets referenced in "Human Wellbeing and Machine Learning"

Paper: Oparina, Kaiser, Gentile, Tkatchenko, Clark, De Neve, D'Ambrosio (2022), arXiv:2206.00574
https://arxiv.org/abs/2206.00574

The paper's Section 2.1 ("Data") uses three wellbeing survey datasets, all 2010–2018. None can be
downloaded directly via script — each has access restrictions.

## 1. German Socio-Economic Panel (SOEP)
- ~30,000 respondents/year, ~400 variables, in-person interviews
- Life satisfaction measured 0–10
- Access: requires a formal Data Use Agreement with DIW Berlin (data protection agreement, usually
  needs academic/institutional affiliation)
- Portal: https://www.diw.de/en/diw_01.c.601584.en/data_access.html

## 2. UK Household Longitudinal Study (UKHLS) / "Understanding Society"
- ~29,605–40,679 observations/year, 500+ variables, Waves 2–10 (2010–2018), in-person interviews
- Life satisfaction measured 1–7
- Access: UK Data Service, free registration + End User License (some variables need a Special
  Licence with additional approval)
- Portal: https://beta.ukdataservice.ac.uk/datacatalogue/studies/study?id=6614

## 3. US Gallup Daily Poll (Gallup World Poll / Gallup Daily Poll)
- Daily cross-sectional telephone surveys, 500–1,000 respondents/day, ~115,192–351,875/year,
  ~60 variables
- Wellbeing measured via Cantril Ladder of Life (0–10)
- Access: proprietary, commercial. Paper's acknowledgments explicitly thank "The Gallup
  Organization for providing access to their data for this research project" — even the authors
  had a special arrangement, not open access. Not publicly obtainable without a paid license
  agreement with Gallup.

## Notes
- No data-availability-statement URL or public repository was found in the paper for any of the
  three datasets.
- Replicating the paper exactly requires individually obtaining SOEP and UKHLS access (each tied to
  personal/institutional credentials) and, for Gallup, a commercial licensing arrangement — none of
  which can be completed on the user's behalf via automated download.
