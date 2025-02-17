---
id: image_similarity_search.md
title: Image Similarity Search
---

# Image Similarity Search 

{{fragments/translation_needed.md}}

This tutorial demonstrates how to use Milvus, the open-source vector database, to build a reverse image search system.
- [Open Jupyter notebook](https://github.com/milvus-io/bootcamp/blob/master/solutions/reverse_image_search/reverse_image_search.ipynb)
- [Quick deploy](https://github.com/milvus-io/bootcamp/blob/master/solutions/reverse_image_search/quick_deploy)
- [Try online demo](https://zilliz.com/milvus-demos/reverse-image-search)
The ML model and third-party software used include:
- YOLOv3
- ResNet-50
- MySQL

</br>

Major search engines like Google already give users the option to search by image. Additionally, e-commerce platforms have realized the benefits this functionality offers online shoppers, with Amazon incorporating image search into its smartphone applications.

</br>

In this tutorial, you will learn how to build a reverse image search system that can detect image patterns and return similar images to the one you upload. To build such an image similarity search system, download PASCAL VOC image set which contains 17125 images of 20 categories. Alternatively, you can prepare your own image datasets. Use YOLOv3 for object detection and ResNet-50 for image feature extraction. After going through the two ML models, images are converted into 256-dimensional vectors. Then store the vectors in Milvus and a unique ID for each vector is automatically generated by Milvus. MySQL is then used to map the vector IDs to the images in the dataset. Whenever you upload a new image to the image search system, it will be converted into a new vector and compared against the vectors previously stored in Milvus. Milvus then returns the IDs of the most similar vectors and you can query the corresponding images in MySQL.

</br>

![image_search](../../../assets/image_search.png "Workflow of a reverse image search system.")

![image_search_demo](../../../assets/image_search_demo.jpeg "Demo of a reverse image search system.")
