# gorkha_quake
Predict the level of damage to buildings caused by the 2015 Gorkha earthquake in Nepal based on the data collected through surveys by Kathmandu Living labs and the Central Bureau of Statistics.
## Problem description
We're trying to predict the ordinal variable ___damage_grade___, which represents a level of damage to the building that was hit by the earthquake. There are 3 grades of the damage:
* 1 represents low damage
* 2 represents a medium amount of damage
* 3 represents almost complete destruction
## Features
The dataset mainly consists of information on the buildings' structure and their legal ownership. Each row in the dataset represents a specific building in the region that was hit by Gorkha earthquake.

There are 39 columns in this dataset, where the __building_id__ column is a unique and random identifier. The remaining 38 features are described in the section below. Categorical variables have been obfuscated random lowercase ascii characters. The appearance of the same character in distinct columns does not imply the same original value.
## Description
* _geo_level_1_id, geo_level_2_id, geo_level_3_id_ (type: int): geographic region in which building exists, from largest (level 1) to most specific sub-region (level 3). Possible values: level 1: 0-30, level 2: 0-1427, level 3: 0-12567.
* _count_floors_pre_eq_ (type: int): number of floors in the building before the earthquake.
* _age_ (type: int): age of the building in years.
* _area_percentage_ (type: int): normalized area of the building footprint.
* _height_percentage_ (type: int): normalized height of the building footprint.
* _land_surface_condition_ (type: categorical): surface condition of the land where the building was built. Possible values: n, o, t.
* _foundation_type_ (type: categorical): type of foundation used while building. Possible values: h, i, r, u, w.
* _roof_type_ (type: categorical): type of roof used while building. Possible values: n, q, x.
* _ground_floor_type_ (type: categorical): type of the ground floor. Possible values: f, m, v, x, z.
* _other_floor_type_ (type: categorical): type of constructions used in higher than the ground * * _floors_ (except of roof). Possible values: j, q, s, x.
* _position_ (type: categorical): position of the building. Possible values: j, o, s, t.
* _plan_configuration_ (type: categorical): building plan configuration. Possible values: a, c, d, f, m, n, o, q, s, u.
* _has_superstructure_adobe_mud_ (type: binary): flag variable that indicates if the superstructure was made of Adobe/Mud.
* _has_superstructure_mud_mortar_stone_ (type: binary): flag variable that indicates if the superstructure was made of Mud Mortar - Stone.
* _has_superstructure_stone_flag_ (type: binary): flag variable that indicates if the superstructure was made of Stone.
* _has_superstructure_cement_mortar_stone_ (type: binary): flag variable that indicates if the superstructure was made of Cement Mortar - Stone.
* _has_superstructure_mud_mortar_brick_ (type: binary): flag variable that indicates if the superstructure was made of Mud Mortar - Brick.
* _has_superstructure_cement_mortar_brick_ (type: binary): flag variable that indicates if the superstructure was made of Cement Mortar - Brick.
* _has_superstructure_timber_ (type: binary): flag variable that indicates if the superstructure was made of Timber.
* _has_superstructure_bamboo_ (type: binary): flag variable that indicates if the superstructure was made of Bamboo.
* _has_superstructure_rc_non_engineered_ (type: binary): flag variable that indicates if the superstructure was made of non-engineered reinforced concrete.
* _has_superstructure_rc_engineered_ (type: binary): flag variable that indicates if the superstructure was made of engineered reinforced concrete.
* _has_superstructure_other_ (type: binary): flag variable that indicates if the superstructure was made of any other material.
* _legal_ownership_status_ (type: categorical): legal ownership status of the land where building was built. Possible values: a, r, v, w.
* _count_families_ (type: int): number of families that live in the building.
* _has_secondary_use_ (type: binary): flag variable that indicates if the building was used for any secondary purpose.
* _has_secondary_use_agriculture_ (type: binary): flag variable that indicates if the building was used for agricultural purposes.
* _has_secondary_use_hotel_ (type: binary): flag variable that indicates if the building was used as a hotel.
* _has_secondary_use_rental_ (type: binary): flag variable that indicates if the building was used for rental purposes.
* _has_secondary_use_institution_ (type: binary): flag variable that indicates if the building was used as a location of any institution.
* _has_secondary_use_school_ (type: binary): flag variable that indicates if the building was used as a school.
* _has_secondary_use_industry_ (type: binary): flag variable that indicates if the building was used for industrial purposes.
* _has_secondary_use_health_post_ (type: binary): flag variable that indicates if the building was used as a health post.
* _has_secondary_use_gov_office_ (type: binary): flag variable that indicates if the building was used fas a government office.
* _has_secondary_use_use_police_ (type: binary): flag variable that indicates if the building was used as a police station.
* _has_secondary_use_other_ (type: binary): flag variable that indicates if the building was secondarily used for other purposes.
# Performance metric
We are predicting the level of damage from 1 to 3. The level of damage is an ordinal variable meaning that ordering is important. This can be viewed as a classification or an ordinal regression problem. (Ordinal regression is sometimes described as an problem somewhere in between classification and regression.)

To measure the performance of our algorithms, we'll use the F1 score which balances the precision and recall of a classifier. Traditionally, the __F1 score__ is used to evaluate performance on a binary classifier, but since we have three possible labels we will use a variant called the __micro averaged F1 score__.

In Python, you can easily calculate this loss using `sklearn.metrics.f1_score` with the keyword argument `average='micro`


