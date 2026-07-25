## CRISP-DM
(==Cross-Industry Standard Process for Data Mining==)

The framework includes the following phases: business understanding, data understanding, data preparation, modeling, evaluation, and deployment. Learn more about each phase of the process and the associated tasks below.

![[Pasted image 20260717213141.png]]

## Use case

Identity account management experience was one of the areas where we had applied AI/ML models to identify the "next best action" for customers. Goal of the experience was to enable customers to self serve their account management needs including keeping their profile complete and correct, manage subscription preferences and attach additional products. The methodology described above will be very applicable for that problem. It started with identifying clearly the business objectives and clarifying what was important among the various outcomes that was possible. We then looked at the data available to help with the prediction. As we looked at data, the most relevant data was incomplete and led to conclusions that certain actions could not be predicted, due to quality of data. The next step was to find the right model - experimentation was essential to narrow between categorization models and recommendation models. Each selected approach went through a rigorous internal test and a controlled evaluation with customers before it was deployed at scale. As models were deployed, a number of business objectives had to be clarified e.g. prioritization of business outcomes between enabling profile completeness for login success vs improving cross-sell outcomes. This also emphasizes the feedback loops that are ingrained in the model and the iterative nature of the journey. One potential shortcoming is lack of guidance on team structure and roles. 

