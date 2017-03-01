计算视觉高级专题第二节课： 
Dr. Yadong Mu
###visual recogniton


1. Bag-of-words models
2. Locality: spatial pyramid matching& pyramid match kernel(PMK)
3. aggregation: VLAD,fisher vector(@^_^@),soft assignment
4. dictionary: vocabulary tree,product quantization,sparse coding


1, 1st challenge: semantic gap
    
> images are just 3-d type array for the computer.Although we human beings can easily detect the visual information.

2, visual challenge
> different kinds of visual appearance.

CV community:

1,pascal VOC challenge 05-12

2,Large-scale visual recognition challenge(ILSVRC) 2010-2016 (subset of ImageNet) 1000类

3,Multimedia community, like YFCC100M, Image tagging

4,Concept detection: TRECVID SIN task(*LSCOM*)
*ontology design->Image collection->Image annotation->Concept detection*

###bag of words: 
*from Word-Cloud,NLP.ignore the sentence structure and only select words independently.*

1.get local features(SIFT). sift: several variants: *[http://koen.me/research/colordescription](http://koen.me/research/colordescription)*

		SIFT so on:( package: VLFeat)

2.clustering(K-means)->dictionary or code book (an unsupervised process)

3.Assign feature to a dictionary word(L2 distance)

4.Histogram Assignment

5.Normalization->Bag-of-words

How can we improve the performance of SIFT:

1, spatial information

2,Quantization error

3.the way to learn the dictionary

4.The granularity of BOW


####Spatial pyramid matching 

1.Adding spatial information: Locally orderless representation at several levels of resolution(*2x2,4x4 ...*)

2.Similar ideas in video analysis: spatial-temporal matching in video analysis: subclip matching.

3.Motivation of pyramid match kernel: PMK to solve: find the correspondence and match them(partial matching).

4.PMK are well transfered into 3-D point retrieval.


####VLAD

the variance of visual dictionary word.  保留了一阶的 variance (与每个center的距离)

协方差矩阵： 保留二阶信息，但数据太大。

####Fisher vector（fisher information matrix）
Gx=Δxlog uλ（x）

Fλ   FV formulas： difference of 方差和均值

*VLAD always perform the optimal. it's a special case of Fisher vector.

经常求似然函数的gradient.
