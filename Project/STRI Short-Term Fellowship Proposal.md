---
up: "[[Chapter 2 - Predicting Regrowth in Panama]]"
stardate: Mar 25th 2024
update: Mar 26th 2024
---
>[!summary] Key points
>- Introduce the importance of forest regrowth and how there are not enough models being made with land use in consideration
>- Introduce the previous regeneration studies for Panama
>	- regeneration potential for the canal
>	- regeneration for the country
>	- need to build long-term land use map for Panama
>- Introduce how the model could be built for Panama
>- Mention Agua Salud and Jeff Hall's expertise as assistance for the model to be built.
>Modelos de regeneração  
  

## 1500 word statement

1) A description of the research you plan to undertake at the Smithsonian Institution, including the methodology to be utilized

2) The importance of the work, both in relation to the broader discipline and to your own scholarly goals.

3) Justification for conducting your research at the Smithsonian and utilization of research facilities and resources.


**Aim 1 – Modelling Forest Regrowth in the Amazon.** I am building a semi-mechanistic growth model based on the well-established Chapman-Richards3 growth curve (Fig. 1). Using a space-for-time chronosequence, we fit the growth rate and asymptote by incorporating (1) environmental descriptors such as water deficit and soil type, (2) fire history (time since last burn, number of burns), (3) land use type within 33 years of history, and (4) distance to nearest mature forest. I am currently expanding the model from a small area within the ‘arc of deforestation’ to the entire basin and investigating different model configurations. **Impact:** With open access remote sensing data, we can provide predictions for the entire basin, creating an open-source product that can be used by the Brazilian government. By improving our current ability to predict the regrowth potential of deforested land with diverse histories, we can make better informed decisions when establishing new protected areas and planning carbon sequestration strategies.

**Aim 2 – Expanding the regrowth model to Central America.** Costa Rica and Panama are small countries with disproportionate ecological significance, as biodiversity hotspots18 with vibrant research communities and extensive data availability. Additionally, they contain many secondary forests due to conservation initiatives and rural-urban migrations19,20 and exhibit different socioecological contexts from the Amazon basin, including higher elevation and large extents of coffee farming21. This makes them prime candidates for the first expansion of the model outside Brazil. I am acquiring training data for land use classification in Panama and Costa Rica using Random Forest, a machine learning tool that was applied successfully in Brazil by the MAPBIOMAS project. This work is a collaboration with Dr. Javier Sanchez-Galan, a computer scientist from Panama, and Elizabeth Goltz, a remote sensing specialist from Brazil. **Impact:** This allows for an evaluation of the model’s performance in varied settings, allowing for future studies to be conducted in other research-intensive countries and improving carbon sequestration projections across the Neotropics.

**Aim 3 – Incorporating biodiversity metrics into the model, exploring the relationship between biodiversity and biomass.** A continuous debate revolves around whether more biodiverse regions also have higher carbon sequestration rates. This is especially relevant when studying Neotropical forests, which host some of the largest biodiversity and carbon reserves22 in the world. The S2BaK species distribution model23, developed in the Leung lab, describes the probability of presence of over 6,000 native and invasive plants across Panama and Costa Rica, while correcting biases in the biodiversity data collection process. This offers an insight into the species composition of the seed bank that supplies secondary forests, allowing for an investigation of its effect on regrowth trajectories. I will incorporate alpha diversity, as well as probability of presence of nitrogen fixers, lianas, and invasive grasses into the model, investigating their effect on predictive power. I hypothesize that invasive grasses and lianas will have a negative effect on growth rates, while legumes will encourage growth; most nitrogen in secondary Panamanian forests comes from fixation done in the first 12 years of succession13, although they may also slow down recovery by outcompeting late-successional non-fixers in impoverished soils12. **Impact:** Not only does this expansion of the model offer the possibility of further reducing unexplained variability, but it also contributes to a question that has been puzzling community ecologists for decades. In case biodiversity does not improve model predictions, the results would support the argument that biodiversity and biomass are not necessarily directly related11.

**Outcomes – My thesis will contribute to both basic ecology and applied ecosystem management.** I aim to improve the predictive power of current forest regrowth models using state-of-the-art remote sensing products, generating large-scale predictions to support informed decision-making on conservation and carbon sequestration. I also explore the biodiversity-biomass relationship in some of the most biodiverse countries in the world, and foster partnerships across Latin America and Québec to address an urgent global issue.

## Abstract

> A non-technical abstract of not more than 250 words.

Given the pressing climate crisis, regenerating deforested land has become an urgent matter. Secondary forests make up over half of tropical forests, and approximately one-third of the regrowth in the Neotropics is occurring on soil previously abandoned by agriculture. Different land use practices have been shown to greatly affect soil fertility, subsequently influencing regrowth rates on previously exhausted farmland. The surrounding landscape also plays a pivotal role in forest recovery, as the size and biodiversity of surrounding mature forests directly dictate the availability and functional composition of seeds dispersed to the depleted areas. However, these factors remain unexplored by regrowth models, which have focused on environmental predictors. Accurately estimating carbon accumulation is of utmost importance to policymaking, the establishment of protected areas, and climate projections.

My research focuses on **improving our current estimates of carbon accumulation in Neotropical secondary forests while exploring the effects of land use history and biodiversity**. By leveraging remotely sensed land use maps encompassing 33 years of history and global carbon storage data, I am building a semi-mechanistic statistical model to predict forest regrowth given environmental and anthropogenic predictors. The model has been preliminarily implemented in a region of the deforestation arc and is now being scaled up to the entire Brazilian Amazon. Subsequently, the **model will be applied in Panama and Costa Rica**, two data-rich biodiversity hotspots. In collaboration with Latin American scientists, I am expanding to Central America the machine learning-based land use classification method that was applied to Brazil, generating new land use history maps. This explores the applicability of the model to different socioecological scenarios from its initial training. This can inform decision-making in other countries and opens the possibility for future research in the Neotropics.

This research generates large-scale predictions of secondary forest growth and sheds light into the impact of biodiversity on biomass. By addressing the complexities that encompass the regeneration of deforested land, this project contributes to **more efficient conservation strategies and sustainable land use policies in the Neotropical region**.

## Literature

- [[Bardino 2023 - Landscape context importance for predicting forest transition success in central Panama]]

- [[Sinacore 2023 - Mixed success for carbon payments and subsidies in support of forest restoration in the neotropics]]