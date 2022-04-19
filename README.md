## Early Stage Skin Disese Detection

- **Objective**: Predictions of skin diseases in their early stages is today's need. For achieving this, We have multi-layered CNN-model with specifications as it was decided with random guesses and training experience.

## **ABSTRACT :**<br>

<div align="center">
<img src=
"https://user-images.githubusercontent.com/78396437/153776325-4abbaf74-0860-4bf0-92cc-79f310a82603.png" 
         alt="logo" 
         align="center" 
         width="400">
</div>

-  **Today skin diseases are one of the most common diseases, whose number has been increasing day by day. Mostly, people neglect skin diseases and treatment procedures.This neglectance at the initial stages proves pernicious. But even if people consult physicians, it is quite difficult for them to precisely detect skin diseases with high accuracy and precision. Especially when it comes to the diseases like Melanoma, Actinic Keratoses, Basal cell carcinoma, Benign keratosis, Dermatofibroma, Melanocytic nevi, etc.**

-  **Predictions of skin diseases in their early stages is today's need. For this, we have built a multi-layered Early Skin Disease Detection MobileNet CNN model(proposed as a deep learning model by Andrew Howard) having 91 layers in it.**

-  **We have used this model to classify images in following 9 classes:**

    - Actinic Keratoses
    - Basal cell carcinoma
    - Benign keratosis
    - Dermatofibroma
    - Melanoma
    - Melanocytic nevi
    - Vascular skin lesions
    - Normal Human Skin Patch
    - Un-Zoomed human images

- **The dataset for above 9 classes is prepared from following sources:**

    1. HAM-10000 for:

        - Actinic Keratoses
        - Basal cell carcinoma
        - Benign keratosis
        - Dermatofibroma
        - Melanoma
        - Melanocytic nevi
        - Vascular skin lesions

    2. ISIC 2019 for:

        - Actinic-Keratoses
        - Basal cell carcinoma
        - Benign keratosis
        - Dermatofibroma
        - Melanoma
        - Vascular skin lesions

    3. UTK-Face: For Un-Zoomed human images

    4. Normal Human Skin Patch images were custom datasets built using Un-Zoomed human images. We cropped these images around forehead, cheeks and throat of human babies.
 
##### **THIS DATA SET CAN BE FOUND**  [HERE](https://drive.google.com/drive/folders/1YjFmWfT0JnMJfDHxFWBdtHDjTdRckPtN?usp=sharing)

### **DESCRIPTION OF DISEASES**

<div align="center">
<img src=
"https://user-images.githubusercontent.com/78396437/153776727-7e5e1e2a-d3fc-49e5-b414-397ebda66d05.png" 
         alt="logo" 
         align="center" 
         width="500">
</div>

- **nv**<br>
    - Melanocytic nevi are benign neoplasms of melanocytes and appear in a myriad of variants, which all are included in our series. The variants may differ significantly from a dermatoscopic point of view.<br>

 
- **mel**<br>
    - Melanoma is a malignant neoplasm derived from melanocytes that may appear in different variants. If excised in an early stage it can be cured by simple surgical excision. Melanomas can be invasive or non-invasive (in situ). We included all variants of melanoma including melanoma in situ, but did exclude non-pigmented, subungual, ocular or mucosal melanoma.<br>*
 
 
- **bkl**<br>
    - "Benign keratosis" is a generic class that includes seborrheic ker- atoses ("senile wart"), solar lentigo - which can be regarded a flat variant of seborrheic keratosis - and lichen-planus like keratoses (LPLK), which corresponds to a seborrheic keratosis or a solar lentigo with inflammation and regression. The three subgroups may look different dermatoscop- ically, but we grouped them together because they are similar biologically and often reported under the same generic term histopathologically. From a dermatoscopic view, lichen planus-like keratoses are especially challeng- ing because they can show morphologic features mimicking melanoma and are often biopsied or excised for diagnostic reasons.<br>

- **bcc**<br>
    - Basal cell carcinoma is a common variant of epithelial skin cancer that rarely metastasizes but grows destructively if untreated. It appears in different morphologic variants (flat, nodular, pigmented, cystic, etc) , which are all included in this set.<br>
 
- **akiec**<br>
    - Actinic Keratoses (Solar Keratoses) and intraepithelial Carcinoma (Bowen’s disease) are common non-invasive, variants of squamous cell car- cinoma that can be treated locally without surgery. Some authors regard them as precursors of squamous cell carcinomas and not as actual carci- nomas. There is, however, agreement that these lesions may progress to invasive squamous cell carcinoma - which is usually not pigmented. Both neoplasms commonly show surface scaling and commonly are devoid of pigment. Actinic keratoses are more common on the face and Bowen’s disease is more common on other body sites. Because both types are in- duced by UV-light the surrounding skin is usually typified by severe sun damaged except in cases of Bowen’s disease that are caused by human papilloma virus infection and not by UV. Pigmented variants exists for Bowen’s disease and for actinic keratose. Both are included in this set.<br>

- **vasc**<br>
    - Vascular skin lesions in the dataset range from cherry angiomas to angiokeratomas and pyogenic granulomas. Hemorrhage is also included in this category.<br>

- **df**<br>
    - Dermatofibroma is a benign skin lesion regarded as either a benign proliferation or an inflammatory reaction to minimal trauma. It is brown often showing a central zone of fibrosis dermatoscopically.<br>


### **CHALLENGES :**

- **Data Preparation:**
    - As we all know, data preparation in any ML project is the most cumbersome part.Extracting and cleaning data from different sources and integrating them is a bit tricky.
    - I prepared data from mainly 4 different sources given here :
        1. ISIC 2019
        2. HAM_10000    
        3. PH2Dataset
        4. UTK-Face

- **Classification:**
    - Skin rashes of Melanoma and Melanocytic-nevi are almost similar. Differentiating between them using even through human conscious is very difficult.

<div align="center">
<img src=
"https://user-images.githubusercontent.com/78396437/153777472-1b351907-603e-488a-8395-42e48056d5e4.png" 
         alt="logo" 
         align="center" 
         width="400">
</div>

- **Storage:**
    - Storing such a big model also requires a lot of space.

### **SOLUTIONS:**

   - Instead of collecting normal human skin images from web. I used face images of UTK-Face Dataset and cropped it to create a custom skin dataset.

<div align="center">
<img src=
"https://user-images.githubusercontent.com/78396437/153777503-7b857955-1952-42ee-b618-39b5a2ab18bd.png" 
         alt="logo" 
         align="center" 
         width="400">
</div>


   - I used the simplest approach for training(not requiring any CSV file). I prepared subclasses in the training and validation directory on the name of my classes and directly used them for model training.

   - I removed majority of non-pigmented, subungual, ocular Melanoma which are similar to Melanocytic-nevi, to make Melanoma more differentiable.
Also we have stored the model in .json, h5 format uploaded on drive and GitHub for further use

### __NOTE:__ Skin_Disease.h5 is too big to upload(>100mb)

- To test model download it and paste it in this directory.
- Download it from [HERE](https://drive.google.com/file/d/1Zf9tcOUp3Hi8kgHBP2Zpw-jZJyrB3sty/view?usp=sharing)
