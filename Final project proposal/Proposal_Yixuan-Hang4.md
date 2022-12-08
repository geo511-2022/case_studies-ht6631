Applying AI to identify spatial clustering of pedestrian activity and
street environment features
================
Yixuan Zhao & Hang Tian

# Introduction to problem/question

Encouraging walking activities is gaining increasing attention as a
significant strategy for improving public health and urban
revitalization.

There are plenty of research focusing on impact of the built environment
on physical activities; However, few have studied the mixed spatial
relationship and variation between pedestrian activities and urban
security environment, community quality of life and built environment
characteristics. The potential relationship between spatial patterns of
pedestrian activities, aggregation or dispersion, and environmental
features is critical, which will not only direct urban planners to focus
pedestrian safety issues, but also lead architects to consider providing
a comfortable walking experience around the city.

Under the topic of pedestrian activities and their dynamics, questions
addressing issues such as overcrowding and vehicle-pedestrian collision
mitigation have been thoroughly looked into while pedestrian activities
itself is rarely a focal point. Nowadays, with the advancement of remote
scanning technology, it has been used in many research topics including
intelligent transportation systems and public safety evacuation.
Therefore, monitoring pedestrian activities is becoming easier for
understanding complex collective behavior in social systems.

# Problem / Question

Our research hypothesis: (1) Violent crime has a negative impact on the
number of street pedestrians, while property crime is positively
correlated with the number of street pedestrians; (2) Different types of
pedestrian generators will have different impacts on pedestrians. We
believe that high-density catering and retail pedestrian generators and
perfect infrastructure will bring more pedestrians to the area; (3)
Neighborhoods with low social satisfaction and streets near
disadvantaged communities will not attract too many pedestrians.

In this research, we would look into how the urban environment affects
pedestrians’ willingness to walk in Buffalo. Moreover, quantifying this
relationship and create an estimating model using multiple sources of
related variables.

Our assumptions include:

1.  Commercial districts tend to attract more pedestrians, and more
    developed those areas are, more willingly people would walk around.

2.  Violent crimes would reduce the willingness of people walking
    around.

3.  People are more willing to walk on neighbourhoods with
    well-developed infrastructure

# Inspiring Examples

## Example 1

<https://www.tandfonline.com/doi/full/10.1080/13574800701816896>

    Walkable = close: A walkable environment involves a short distance to a destination, particularly where driving is inconvenient or people are without cars—this is the perspective in transportation planning. This definition has a great deal to do with an individual's cost-benefits calculation—are the costs of driving or taking transit great enough to provoke an individual to walk?

    Walkable = barrier-free: A walkable environment is traversable, without major barriers. Walkability can be refined to mean traversable to children, elderly, handicapped or those wearing high heels.

    Walkable = safe: A walkable environment is safe in terms of perceived crime or perceived traffic.

    Walkable = full of pedestrian infrastructure and destinations: A walkable environment visibly displays full pedestrian infrastructure such as sidewalks or separated trails, marked pedestrian crossings, street furniture and street trees.

    Walkable = upscale, leafy, or cosmopolitan: A walkable place is somewhere that the pedestrian environment is pleasant for upper middle-class professionals, who have other choices for getting around. This is the perspective in much popular and architectural commentary. Such places have several of the following dimensions: an area with coffee shops and interesting stores; a mix of housing types including apartments and condominiums; a grid street pattern and full pedestrian infrastructure including pleasant tree-lined or architecturally interesting streets; well-maintained or scenic green spaces with clear pedestrian paths; a lack of litter, graffiti and obviously down-and-out people. Finally, there should be transit or taxis in case interest lapses. This type of walking is not necessarily brisk.

## Example 2

<https://www.tandfonline.com/doi/abs/10.1080/10225706.2016.1185639>
<img src="https://www.researchgate.net/profile/Mahsa-Mansouri/publication/303531511/figure/fig1/AS:538908972204032@1505497319020/Structure-of-questionnaire-Source-Mansouri-2014.png" alt="A"/>

## Example 3

<https://www.tandfonline.com/doi/full/10.1080/13574809.2019.1592665>

    Visual proximity is crucial for the commercialization of buildings adjacent to transit stops. Commercialization around transit stops is closely associated with pedestrian movement (Figure 3a). The paths of arriving and departing passengers converge on and disperse from transit stops. Businesses tend to locate within the viewsheds and hearing ranges of pedestrians and transit passengers. If a person steps out alone from a bus or train, an individual viewshed opens (Figure 3a1). If an individual joins a group in movement, the vantage point can move across urban space. The mode of observing space emerges later as the urban space elongates and encompasses several vantage points, one for each member of the group (Figure 3a2). Transit and commercial activities form a virtuous circle. Transit, depending on the level of service, attracts crowds of passengers that are potential customers. More traffic and passengers attract more surrounding businesses. Established commercial storefronts and entrances to public buildings along pedestrian paths create a pattern of public spaces in visual proximity to transit stops (Figure 3a3).

<img src="https://www.tandfonline.com/na101/home/literatum/publisher/tandf/journals/content/cjud20/2020/cjud20.v025.i01/13574809.2019.1592665/20210721/images/medium/cjud_a_1592665_f0003_oc.jpg" alt="A"/>

## Example 4

[DOC](https://observatorio.dadep.gov.co/sites/default/files/documentos/in05_places_for_people.pdf)
\## Example 5 <https://link.springer.com/article/10.1057/jphp.2008.47>

    Both GIS and field observation data indicated that neighborhood conditions differed significantly between poor and nonpoor neighborhoods that were equally walkable. Nonpoor neighborhoods had better scores on most indicators related to aesthetics, safety, and pedestrian conveniences. These findings are consistent with previous work on disparities in neighborhood conditions,(5, 37) but to our knowledge this study is the first to demonstrate that these differences remained after controlling for the potentially confounding effect of neighborhood walkability. We also found differences between poor and nonpoor neighborhoods in features less commonly studied, such as pedestrian amenities and conveniences and sidewalk commercial activity. This study shows that low-income urban neighborhoods are less conducive to walking than they would appear to be if we considered only population density, land use mix, and other indicators of urban form. Taking account of neighborhood aesthetics and safety may help explain disparities in health between advantaged and disadvantaged populations.

# Proposed data sources

We may need data from multiple sources including:

**Dependent variable: pedestrain counts**

1.  Buffalo daily pedestrians count data

**We used Script to scrape data from pedestrian counting devices on
eight streets in Buffalo from 2005 to 2022 from the [Buffalo GBNRTC
Pedestrian Counting
Projec](https://gbnrtc.public.ms2soft.com/tcds/tsearch.asp?loc=Gbnrtc&mod=TCDS)**

**Independent variables that may related with pedestrian counts**

1.  New York state parcels data:

Link: <http://gis.ny.gov/parcels/>

3.  Buffalo city daily crime incidents data:

Link:
<https://data.buffalony.gov/Public-Safety/Crime-Incidents/d6g9-xbgu>

4.  Buffalo 311 service request calls:

Link:
<https://data.buffalony.gov/Quality-of-Life/311-Service-Requests/whkc-e5vr>

5.  Received Traffic Incident Calls in Buffalo:

Link:
<https://data.buffalony.gov/Public-Safety/Received-Traffic-Incident-Calls/6at3-hpb5>

**And infraustructure data including:** 6. Buffalo transportation
stations data:

Link:
<https://gis.erie.gov/server/rest/services/DSS/DSS_Funded_Agencies/MapServer>

7.  Buffalo fire Hydrants locations:

Link: <https://data.buffalony.gov/Public-Safety/Fire-Hydrants/2i8a-ybsk>

8.  Buffalo street trees data:

Link:
<https://data.buffalony.gov/Quality-of-Life/Tree-Inventory/n4ni-uuec>

9.  Buffalo traffic control devices data:

Link:
<https://data.ny.gov/Transportation/Traffic-Control-Device-Inventory/8fht-3ajj>

# Proposed methods

Building on previous work, this study uses Moran’s I and random forest
models to examine spatial patterns of pedestrian numbers, neighborhood
policing, neighborhood quality of life, and built environment
contributors across eight major streets in Buffalo, New York. A
combination of pedestrian generators, crime rates, and 311 community
service calls were included as independent variables to study the impact
of community policing environment, community quality of life, and built
environment characteristics on them. By using ‘ISLR2’ package, we are
able to run machine learning algorithms like random forest for our
project. Besides, for data processing and cleaning, we may need
‘tidyverse’, ‘dplyr’. Since there are no raster data used in this
project, we just need ‘sf’ for spatial data and related processing.

# Expected results

By the end of our project, we would first find which variables would be
highly correlated with pedestrian counts and conclude how urban
environment described by those variables collected would have an
influence on the willingness of people to walk. If the result indicates
strong relationships between, we could quantify this relationship and
estimate pedestrian numbers by training a machine learning model.

This research contributes to the understanding of the spatialpatterns of
pedestrian activities and geographically variable relationship between
the built environment and number of pedestrians. We believe this study
will help guide and focus the minds of policy makers and urban planners
to introduce street vibrancy by transforming the built environment to
improve the quality of life in communities.Rather than simply
identifying features of the built environment that affect pedestrian
activity, we are more interested in developing a contextual analysis
model for urban planners to use in their decision-making process. We
encourage planners and policy makers to consider the optimal number of
walking destinations to be more pedestrian friendly. Finally, we hope
that our efforts will help reshape the design thinking behind future
planning practices and policies.
