---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-26"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# Release notes

The following new features and changes to the service are available.
{: shortdesc}

## Changes
{: #changelog}

The following new features and changes to the service are available.

### 8 September 2017
{: #8september2017}

- **Beta Similarity Search and collections closed**: As of September 8, 2017, the beta period for Similarity Search is closed. For more information, see [Visual Recognition API – Similarity Search Update ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/blogs/bluemix/2017/08/visual-recognition-api-similarity-search-update/){: new_window}.

### 30 June 2017
{: #30june2017}

- **Improved tagging**: We increased the number of training images for the default classifier. That increase improve the ability to recognize accurately the overall ‘scene’ of an image. For details, see [Further Enhancements for General Tagging Feature ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/blogs/bluemix/2017/07/watson-visual-recognition-sees-enhancements-general-tagging-feature/){: new_window}
- **Additional languages**: The **Classify images** method now supports Korean, Italian, and German in addition to English, Arabic, Spanish, and Japanese.

    For details about the API call, see the **Classify an image** method in the [API reference ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/#classify_an_image){: new_window} External link icon.

### 16 May 2017
{: #16may2017}

- **New food classifier is available: Beta**

    A new beta food recognition model provides enhanced specificity and accuracy for images of food items. The **Classify an image** method allows you to add this new classifier, "food", to the `classifier_ids` parameter.

### 5 April 2017
{: #5april2017}

- **New {{site.data.keyword.visualrecognitionshort}} tool is available: Beta**

    A new beta feature, the {{site.data.keyword.visualrecognitionshort}} tool, is available at [http://visual-recognition-tooling.mybluemix.net/ ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://visual-recognition-tooling.mybluemix.net/){: new_window}. This tool helps you work more easily with the {{site.data.keyword.visualrecognitionshort}} service. By entering your Bluemix API key, you can use a GUI to access General Tagging and Face Detection features, as well as to seamlessly create, retrain, and delete custom classifiers associated with your API key, without needing to code.

### 8 March 2017
{: #8march2017}

- **Updated language support for general classifier tagging**

    The general classifier now returns tags in all supported languages.

- **Known issues**

    **FIXED 04-13-2017**: Repeatedly calling `GET /classifiers` while training or retraining is in progress, in order to check the status, can result in killing the training job. To workaround this issue, poll a new classifier's status using `GET /classifiers/{classifier_id}`. In other words, use the classifier `GET` for a single classifier ID, rather than `GET /classifiers`, which gets all classifiers, and can trigger this issue. Note that `GET /classifiers/{classifier_id}` is also faster.

### 15 December 2016
{: #15december2016}

- **Improved general classifier tagging**

    - The general classifier's deep learning algorithms have been updated. There is a significant improvement in tag quality for all languages, and a significant increase in the volume of English tags returned by the service. This high-quality tag output is also available when you create your own custom classifier.
    - Color tagging has been added. The service now returns the top one or two colors in the image.

- **Known issues**

    - Images submitted to the demo with EXIF metadata tags do not specify orientation (landscape versus portrait) correctly to the service. iPhone uploaded images may contain EXIF metadata tags. The workaround for this is to update your image metadata to not rely on EXIF metadata tags to specify the orientation of your image. Often, you can do this just by opening the image on your computer and saving it. For example, on a Mac, opening in Preview and then saving the image sets the correct orientation tags.
    - Sending images to the {{site.data.keyword.visualrecognitionshort}} service with [EXIF tag ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://en.wikipedia.org/wiki/Exif){: new_window} values of 8, 3 or 6 can add latency. The service rotates the pixels of the image to the encoded viewpoint. You can save time by pre-rotating your images, or by removing the EXIF headers if they are not important to your {{site.data.keyword.visualrecognitionshort}} task.

### 1 December 2016
{: #1december2016}

- **New pricing**

    IBM has lowered the pricing of custom classifiers on the {{site.data.keyword.visualrecognitionshort}} service and increased what's available on the free plan. For more information, see the [{{site.data.keyword.visualrecognitionshort}} pricing page](http://www.ibm.com/watson/developercloud/visual-recognition.html#pricing-block).

### 7 October 2016
{: #7october2016}

- **Face detection enhancements**

    The service has a new face-detection algorithm that improves the responses of the `GET` and `POST /v3/detect_faces` methods. The service adjusted the filtering of low-confidence age, name, and gender facial detections. As a result, more faces are found, and a larger range of confidences are returned.

### 8 September 2016
{: #8september2016}

- **Similarity Search BETA**

    Users can now upload their own collection of images, use an image to search that collection for similar images, and then the service returns the top 100 most similar images. Similarity search can be utilized for any purpose, and users can custom train the service on collections of up to 1 million images each. For more information on using the new similarity search functionality, see the [Tutorial](/docs/services/visual-recognition/tutorial-collections.html), and the [API reference ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/#collections){: new_window} pages.

- **Text recognition is now closed beta**

    The `POST` and `GET /v3/recognize_text` methods have gone back into closed beta. IBM looks forward to continuing to support BETA clients that use the service, with no current plans for another open beta.

### 1 August 2016

- **Introductory pricing ending**

    Custom classifier training and retraining, custom image classification, and custom classifier storage is no longer free. For information on the pricing, see the {{site.data.keyword.visualrecognitionshort}} service [pricing page](http://www.ibm.com/watson/developercloud/visual-recognition.html#pricing-block).

### 5 July 2016
{: #5july2016}

- **Updating custom classifiers**

    Custom classifiers are no longer limited to a fixed set of training data. A user can now update existing classifiers with new images, or add additional positive or negative example classifiers to an existing trained classifier. By supplying additional example images for Watson to learn from, the service can make a user's classifier more accurate. Custom classifiers can now learn over time, continuously getting better at understanding visual information.

- **Known issues**

    **FIXED 04-13-2017**: Users may get a 500 error code after 30 or 90 seconds when updating an existing classifier. Despite the error, there is a good chance that the retrain request completes successfully. Wait at least 2 minutes, and then check the status of the classifier by using the `GET classifiers/{classifier\_id}` method. If the status is "ready" and the "retrained" timestamp has been updated, the retraining request which generated the 500 code was successful. Otherwise, if the "retrained" timestamp has not been updated, there is an explanation added to the response which says why the retraining failed, and the service will revert the classifier to the version there was before the retrain request was issued.

### 20 May 2016
{: #20 may 2016}

This is the General Availability release of the {{site.data.keyword.visualrecognitionshort}} service. This release introduces Version 3 of the service, and is a breaking change. This release incorporates functionality from the AlchemyVision service, which has been deprecated.

Any custom classifiers that were created while the service was in Beta must be recreated in a GA instance of the service.

The following changes and updates were made to the {{site.data.keyword.visualrecognitionshort}} service:

- **Version date:** To utilize the features of this release, use `2016-05-20` as the value for the `version` parameter.
- **Classes and classifiers:** Single classifiers are now called "classes". In GA, a group of classes is called a "classifier".
- **Classification:** Use the `POST` or `GET /v3/classify` methods to quickly and accurately identify a variety of subjects and scenes with default classes.
- **Face detection:** Use the `POST` or `GET /v3/detect_faces` methods to detect faces in images and get information about them, such as where the face is located in the image and the estimated age range and gender for each face. The service can also identify many celebrities by name and can provide a knowledge graph so that you can perform interesting aggregations into higher-evel concepts.
- **Multi-faceted custom classifiers:** You can now create and train highly specialized classifiers that are defined by several classes. For example, you can create a "new\_red\_car" classifier that is defined by the classes "new\_cars" and "red\_cars". To learn more  about creating multi-faceted classifiers, see [Structure of the training data](/docs/services/visual-recognition/customizing.html#structure).
- **Asynchronous training:** Training of custom classifiers is now asynchronous, so training calls complete quickly while your custom classifier continues to learn in the background. To check on the training status of your custom classifier and find out when it is available for use, call the `GET /v3/classifiers/{classifier_id}` method and check the `status` response parameter.

### 2 December 2015
{: #2december2015}

The newest release of the {{site.data.keyword.visualrecognitionshort}} service is a breaking change that introduces a new version of the {{site.data.keyword.visualrecognitionshort}} API (v2). Version 1 of the {{site.data.keyword.visualrecognitionshort}} service is available for use until the service exits beta.

To immediately start using version 2 of the API, understand and update your code to reflect these changes:

- In version 1 of the service, you analyzed images by labels. In version 2 of the service, labels are called **classifiers**. Classifiers have a unique classifier ID indicated by the `classifier_id` parameter and a short name indicated by the `name` parameter.
- The `POST /v1/recognize` method for analyzing an image is now the [`POST /v2/classify` ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/#classify_an_image){: new_window} method. The `labels_to_check` parameter is renamed to `classifier_ids`.
- The `GET /v1/tag/labels` method for retrieving a list of labels in V1 is now the [`GET /v2/classifiers` ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/#retrieve_a_list_of_classifiers){: new_window} method for retrieving a list of classifiers.
- In addition to retrieving a list of classifiers, you can also retrieve details for a specific classifier with the new [`GET /v2/classifiers/{classifier_id}` ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/#retrieve_classifier_details){: new_window} method.
- Version 2 of the Beta {{site.data.keyword.visualrecognitionshort}} API enables you to create custom classifiers with the new [`POST /v2/classifiers` ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/#create_a_classifier){: new_window} method. To learn more about creating custom classifiers, see [Creating custom classifiers](/docs/services/visual-recognition/customizing.html).
- Version 2 of the Beta {{site.data.keyword.visualrecognitionshort}} API also enables you to delete custom classifiers with the new [`DELETE /v2/classifiers` ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/#delete_a_classifier){: new_window} method.
- Version 2 of the Beta {{site.data.keyword.visualrecognitionshort}} API requires the `version` parameter. Specify the release date of the version of the API you want to use in `MM-DD-YYYY` format.