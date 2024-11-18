# Face-Age-Regression
—————————————Written by Zavier 10/11/2024—————————————————-

Comp5318-Group-2-71
Our task: Age estimation: Predict the age of individuals in the images using machine learning techniques, such as convolutional neural networks (CNNs).

1. Please install the nbdime and nbstripout before use git push the ipynb, because the git cannot handle raw ipynb data since it is json file. The nbdime and nbstripout will help git recognize the ipynb file. Without it, the git push operation will destroy the readability of the ipynb.file, which will cause inevitable rollback expense.

pip install nbdime

nbdime config-git --enable

pip install nbstripout

nbstripout --install

2. Please use the double_cleaned_wiki dataframe instead of directly use the cleaned image.

Some pictures in the cleaned image are also throwed by the second_face_score.

There's also some interesting feature in the dataframe, for example, the name of the individuals, gender, age, face_score and second_face_score.

However, I think the face_score are not good enough. On the one hand, the face_score cannot recognize as well on yellow and black race as on white race.

On the other hand, the face_score neglects some picture that have a small face or a far face. This intention is for facial detection or recognition, but our task is to do age regression on the image individual, so some human small face picture also make sense.

The experienced threshold of a image i think which is appropriate is 8.

Some picture do have 2 or 1.3 to 1.5 human faces, but it can be obvious noticed that these picture has a obvious main character even though that they have other people.

Since we only have one person age label for one image, the obvious parallel two people or more people images are useless.

3. Zavier's version:

python - 3.12.4

pytorch - 2.4.1 + cuda 12.4

onnxruntime-gpu 1.19.2

numpy - 1.26.3

numpy-base 1.26.4

onnx - 1.17.0

nbdime - 4.0.2

nbstripout - 0.7.1

notebook - 7.2.2

insightface - 0.7.3
