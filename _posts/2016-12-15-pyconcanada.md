---
layout: post
title: PyCon Canada Tutorial 2016
---
Earlier in November this year, I had the opportunity to help run a tutorial at [PyCon Canada](https://2016.pycon.ca), which is the Canadian version of [PyCon](https://us.pycon.org/2017/). PyCon is a gathering of the Python community, and filled with talks, tutorials and sprints. Unlike PyData, where there's a data focus, PyCon is much more diverse.

The tutorial was led by [Sourabh Mittal](https://ca.linkedin.com/in/sourabh-mittal-9b55537). Our tutorial was one of the six tutorials presented at PyCon Canada this year, and the only one that was sponsored (by our employer Capital One). The focus on the tutorial was building a web application that does optical character recognition (OCR) in the backend. Main technical specs were Flask (Python package) and [Tesseract](https://github.com/tesseract-ocr/tesseract) (OCR package written in C++).

Unfortunately, PyCon Canada does not video tape the tutorials, however, here is our [repo](https://github.com/srbhmitt/pycon-tutorial) if you want to want to check it out yourself! Notable mentions:

1. Sourabh's training of Flask with backend OCR is in the main folder (go through the main Jupyter notebook)
2. Tesseract allows training of new fonts that are not included in its default set of fonts, check out this [section](https://github.com/srbhmitt/pycon-tutorial#training-a-new-font-with-tesseract) to see how this is done. When I put this material together, Tesseract did not provide clear enough instructions for training for beginner users. Since then, Tesseract has updated their training instructions.
3. I also created a [web application](https://github.com/srbhmitt/pycon-tutorial/tree/master/application-example) that takes two file images with locations, does backend OCR processing on the images, and outputs current driving directions between the two locations with the help of Google Maps API:

![application output]({{ site.url }}/img/output.png)

Our hope was to teach different building blocks that would help to empower people to go on and create powerful applications.
