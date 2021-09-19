# allenlp-hacks

Colab link : https://colab.research.google.com/drive/1igiEjFR5G1kj2TFsLZQjaDfblbWtWiqn?usp=sharing

# Overview 

This project is a submission to [AllenNLP Hackathon](https://allennlp-hackathon.apps.allenai.org/) with following team members - Tahsin Mayeesha, Khalid Saifullah and Atuhurra Jesse. 

# Task 

We picked [Semeval 2022 task 5 : Multimedia Automatic Misogyny Identification (MAMI)](https://competitions.codalab.org/competitions/34175) as our project. Here the task is to identify microaggression against women that is spread online via meme's. 

According to task description : 


***Women have a strong presence online, particularly in image-based social media such as Twitter and Instagram: 78% of women use social media multiple times per day compared to 65% of men...............Although most of them are created with the intent of making funny jokes, in a short time people started to use them as a form of hate against women, landing to sexist and aggressive messages in online environments that subsequently amplify the sexual stereotyping and gender inequality of the offline world.***

The proposed task, i.e. Multimedia Automatic Misogyny Identification (MAMI) consists in the identification of misogynous memes, taking advantage of both text and images available as source of information. The task will be organized around two main sub-tasks:

**Sub-task A:** a basic task about misogynous meme identification, where a meme should be categorized either as misogynous or not misogynous;


# Approach

* We have tried to train two seperate models. First one is the model in this colab that uses [CLIP](https://openai.com/blog/clip/) by openai via huggingface transformers. We extract text and image embeddings from clip and train the multimodal task via a fusion model with pytorch lightning to avoid boilerplate code. Our training loss reduced from 0.69 on the binary classification problem to classify a meme as misogynist vs non-misogynist to 0.483 after 10 epochs. We found multimodal training extremely slow in practice despite increasing learning rate. 

![](https://github.com/Tahsin-Mayeesha/allenlp-hacks/blob/main/new.png?raw=true)

![](https://github.com/Tahsin-Mayeesha/allenlp-hacks/blob/main/HatefulMemeDetector_Pipeline.png?raw=true)


* Our second model was Huggingface's [MMBT](https://github.com/facebookresearch/mmbt). However while we were able to modify the script to acccomodate current dataset from multimodal IMDB, a bug in the model couldn't be worked out.



# Resources 

* https://www.drivendata.co/blog/hateful-memes-benchmark/ for modifying to current model with significant changes.

# Computational Resources

- Google colab general, 1 GPU, 10k image dataset

# Wandb link 

- https://wandb.ai/khalidsaifullaah/wandb-lightning/overview?workspace=user-khalidsaifullaah
-


