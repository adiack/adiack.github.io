---
layout: post
title:  "Google Release Open Buildings V3"
---

# Mapping the world with remote sensing

Our Google Research team recently released  [Open Buildings V3](https://sites.research.google/open-buildings/). The updated dataset includes over  **1.8 billion** building detections across Latin America, the Caribbean, Africa, South, and Southeast Asia. We ran our AI model on  **58M km2**  of the Earth's surface covering  **over half of the world**  in terms of population.The dataset is free to use under the  [Creative Commons Attribution (CCBY-4.0)](https://creativecommons.org/licenses/by/4.0/)  and  [Open Data Commons Open Database License (ODbL V1.0)](https://opendatacommons.org/licenses/odbl/1-0/)  licenses.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQHg5CWOZ9kq7g/article-inline_image-shrink_1000_1488/0/1689985561697?e=1697068800&v=beta&t=gk4h7JsalufHf5jyWEL4D-Csk5Tq4L0RWxwXk4fAWgI)

Open Buildings V3 in Google Earth Engine

  

The project was originally focused on improving  [mapping knowledge in Africa](https://blog.google/around-the-globe/google-africa/using-ai-to-map-africas-buildings/), with the goal of supporting development and other social good activities. We received great  [feedback](https://blog.google/around-the-globe/google-africa/how-mapping-the-worlds-buildings-makes-a-difference/)  from a variety of organizations, including UN agencies, nonprofits, and academics, who have been using Open Buildings and the dataset has since been expanded to other regions of the world.

In addition to Open buildings datasets, the team's work has led to major improvements to Google Maps. As  [featured by Sundar Pichai in Google IO 2022,](https://www.youtube.com/live/PeUXBvRExic?feature=share&t=414)  our team increased the number of buildings on Google Maps in Africa 5x, from 60m to 300m.

  

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQHcGTQ_Twfm0g/article-inline_image-shrink_1000_1488/0/1689984443015?e=1697068800&v=beta&t=iLduJYH3pBqv5y-HYBJpt_zivKP9gBVqxmmj9hVm6sc)

The dataset is based on AI processing of satellite imagery. This can sometimes lead to challenges in detecting buildings that are not well demarcated, or that are confused with vegetation or other natural structures. However, the dataset includes a degree of confidence from the model for each detection, which users can filter on. There is more information available in the  [FaQ section of the Open Buildings website](https://sites.research.google/open-buildings/#faq).

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQFz7HdMUk9wIQ/article-inline_image-shrink_1500_2232/0/1689983347021?e=1697068800&v=beta&t=QeocZKqXyacSh2qhPL-sk90xA0Mkkirw2tbY5RTn3N4)

False positives on natural features (glacier and rocks), contiguous buildings without clear delineation, shifted footprint due to high rise buildings

This versions come with improved precision and recall from V2 on the building detections.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQEDtwJnJtuf1Q/article-inline_image-shrink_1000_1488/0/1689983614525?e=1697068800&v=beta&t=maacUelW4A4011vWJjndVoLNXNF4_cyQflAb1pHnh44)

Precision, recall, and score threshold curves

  

For each building detected, the dataset provides the shape, size, location, and a Google  [PlusCode](https://maps.google.com/pluscodes/).

The dataset can be  [downloaded](https://sites.research.google/open-buildings/#download)  in CSV format (178GB), visualized in  [Google Earth Engine](https://code.earthengine.google.com/?scriptPath=Examples%3ADatasets%2FGOOGLE%2FGOOGLE_Research_open-buildings_v3_polygons)  or other GIS tools. We also provide a sample Spatial analysis Google Colab  [notebook](https://colab.research.google.com/github/google-research/google-research/blob/master/building_detection/open_buildings_spatial_analysis_examples.ipynb)  to get started on experiment such as calculating the proximity of health facilities.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQGliXT_G7sDPA/article-inline_image-shrink_1000_1488/0/1689988382741?e=1697068800&v=beta&t=nvMpaohlqu0KQDmUMDf9LkimB-Sk9KGL5PpN17B2WzY)

Jamaica Mean buidling size (m2), Kingston with the highest

  

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQEuETSs5PlUDg/article-inline_image-shrink_1000_1488/0/1689983001544?e=1697068800&v=beta&t=vMWKKrTobNTexIlvL135RUh440Zs35nlT61obxMhTTw)

Port Au Prince, Haiti

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQGE4hdgAtWJBw/article-inline_image-shrink_1000_1488/0/1689986069537?e=1697068800&v=beta&t=dgcTXprTMRqOZ7uqVNtz43NTUkRdvmSNL_bjq9x1B_s)

The Caribean Islands

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQF6lnpBKGsSsQ/article-inline_image-shrink_1000_1488/0/1689988692185?e=1697068800&v=beta&t=lH7acVIZx9uhlbHOzVgS-Iabld8jxUYxQxCxFyz-oV4)

Buenos Aires, Argentina

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQF_ysr7dbpMbw/article-inline_image-shrink_1000_1488/0/1690413559001?e=1697068800&v=beta&t=mwYIZgy89KNu2WZZ1H3tecTSfKxMJH9p0mie1iFZuzs)

Mexico City

  

It’s a big milestone for the team and I am proud of the progress made. Please see the technical report for more information on how this dataset was generated.

[**Open Buildings Site**](https://sites.research.google/open-buildings)

[**Google Earth Engine Catalog**](https://developers.google.com/earth-engine/datasets/catalog/GOOGLE_Research_open-buildings_v3_polygons)

[**Technical Blog**](https://ai.googleblog.com/2021/07/mapping-africas-buildings-with.html)

[**Paper**](https://arxiv.org/abs/2107.12283)

**Update (26/07/23):**  Chris Holmes wrote a blog where he shares his exploration of geospatial data using the Google Open Buildings dataset.

Chris also has a public repository with tools to export Open Buildings data into Cloud Native Geospatial format.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQE9maCwM1fkXw/article-inline_image-shrink_1500_2232/0/1690414814585?e=1697068800&v=beta&t=jq4bV71wB6IWSE0CLFGvlhtebbGzXJYor1leC50o-i0)

  

Acknowledgments: W. Sirko, S. Kashubin, M. Ritter, A. Annkah, Y.S.E. Bouchareb, Y. Dauphin, D. Keysers, M. Neumann, M. Cisse, J.A. Quinn, O. Bousquet, A. Korme, K. Sapkota, M. Hassen, E. Brempong, J. Marcos. S. Nevo, J. Hickey, A. Hassidim, Y. Matias (and many more people)
