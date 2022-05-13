# Detection-of-persuasive-techniques-in-memes

This project was developed for the *Deep Learning* exam, academic year 2021/2022, University of Sapienza.

This work was developed as a group project, the three members were Leonardo Mongelli, Antonio Purificato and I.

This task was taken from the competition semeval 2021, task 6. https://propaganda.math.unipd.it/semeval2021task6/

The data used is shared on the repository: https://github.com/di-dimitrov/SEMEVAL-2021-task6-corpus

The aim of this project is to, given an image with text, classify the propaganda techniques used in said image. This is quicly becoming a very importany task, given the shown influence that social media has on the public opinion. Being able to identify automatically harmful messages can be a very important tool, for big social media platforms, in order to stop the spreading of disinformation campaigns.

<p align="center">
  <img src="/src/380_image_batch_2.png" width="300" title="example meme" >
<p\>

The competition proposed three tasks, but we only worked on the first and the third:
  - the first task consists on detecting the propaganda techniques using only the text content of an image
  - the third task uses instead both the textual part and the visual part of the image

The repository contains the main colab notebook used for comparing the models performances and the notebooks used for training the models. The pretrained models are not shared because of their dimensions.

The models used in this work are several:
  - Different text classifiers based on **transformers** were tried on the first task
  - An ensemble of the best models was used for the final predictions
  - An image classifier using **ResNet50** was used on task 3
  - An ensemble using a text classifier and ResNet50 was tried
  - **DVTT** models was tried on task 3: it uses two encoders, one for the textual part and one for the image, and then two transformers are used, one for the visual part and one for the textual part. The peculiarity is in the use of the visual part to condition the textual transformer and viceversa. 
  
<p align="center">
  <img src="/src/dvtt.jpeg" width="600" title="DVTT architecture">
  <em>DVTT architecture</em>
<p\>

The metrics used for comparing the performances of our methods are the **f1-scores**, in particular the *micro* and *macro* scores, being this a classification task with 20 (and 22 for task 3) categories.
  
<p align="center">
  <img src="/src/results_task1.png" width="600" title="Results for task 1">
  <em>Results for task 1</em>
<p\>
  

<p align="center">
  <img src="/src/results_task3.png" width="600" title="Results for task 3">
  <em>Results for task 3</em>
<p\>
  
## References

### {BERT:} Pre-training of Deep Bidirectional Transformers for Language Understanding

[1] Jacob Devlin, Ming{-}Wei Chang, Kenton Lee, Kristina Toutanova, [*{BERT:} Pre-training of Deep Bidirectional Transformers for Language Understanding*](http://arxiv.org/abs/1810.04805)

```
@article{DBLP:journals/corr/abs-1810-04805,
  author    = {Jacob Devlin and
               Ming{-}Wei Chang and
               Kenton Lee and
               Kristina Toutanova},
  title     = {{BERT:} Pre-training of Deep Bidirectional Transformers for Language
               Understanding},
  journal   = {CoRR},
  volume    = {abs/1810.04805},
  year      = {2018},
  url       = {http://arxiv.org/abs/1810.04805},
  eprinttype = {arXiv},
  eprint    = {1810.04805},
  timestamp = {Tue, 30 Oct 2018 20:39:56 +0100},
  biburl    = {https://dblp.org/rec/journals/corr/abs-1810-04805.bib},
  bibsource = {dblp computer science bibliography, https://dblp.org}
}
```

### Deep Residual Learning for Image Recognition

[2] Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun, [*Deep Residual Learning for Image Recognition*](http://arxiv.org/abs/1512.03385)

```
@article{DBLP:journals/corr/HeZRS15,
  author    = {Kaiming He and
               Xiangyu Zhang and
               Shaoqing Ren and
               Jian Sun},
  title     = {Deep Residual Learning for Image Recognition},
  journal   = {CoRR},
  volume    = {abs/1512.03385},
  year      = {2015},
  url       = {http://arxiv.org/abs/1512.03385},
  eprinttype = {arXiv},
  eprint    = {1512.03385},
  timestamp = {Wed, 17 Apr 2019 17:23:45 +0200},
  biburl    = {https://dblp.org/rec/journals/corr/HeZRS15.bib},
  bibsource = {dblp computer science bibliography, https://dblp.org}
}
```

### {AIMH} at {S}em{E}val-2021 Task 6: Multimodal Classification Using an Ensemble of Transformer Models

[3] Messina Nicola, Falchi Fabrizio, Gennaro Claudio, Amato Giuseppe [*{AIMH} at {S}em{E}val-2021 Task 6: Multimodal Classification Using an Ensemble of Transformer Models*](https://aclanthology.org/2021.semeval-1.140)

```
@inproceedings{messina-etal-2021-aimh,
    title = "{AIMH} at {S}em{E}val-2021 Task 6: Multimodal Classification Using an Ensemble of Transformer Models",
    author = "Messina, Nicola  and
      Falchi, Fabrizio  and
      Gennaro, Claudio  and
      Amato, Giuseppe",
    booktitle = "Proceedings of the 15th International Workshop on Semantic Evaluation (SemEval-2021)",
    month = aug,
    year = "2021",
    address = "Online",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2021.semeval-1.140",
    doi = "10.18653/v1/2021.semeval-1.140",
    pages = "1020--1026",
}
```
