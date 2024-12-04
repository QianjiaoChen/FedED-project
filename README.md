## FedED-project
## Paper
FedED:             chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://aclanthology.org/2020.emnlp-main.165.pdf
## Author:
♥ National Laboratory of Pattern Recognition, Institute of Automation, Chinese Academy of Sciences, Beijing, China ♠ School of Artificial Intelligence, University of Chinese Academy of Sciences, Beijing, China ♦ Huawei Technologies Co., Ltd., Beijing, China
## Why does this project exist?
Joseph Casey and I tried to code the idea of this paper. We didn't implement the BERT as what the authors said. However, we believed that we did fine in other details.

In this project, we have the python implementation and the poster for this project. 

## Abstract
In order to protect the privacy of clients, we have to extract the medical relation and train the  model by federated learning. We use the pretrained model called BERT and also commented the bioBERT if you needed. (The problem here is that we didn't implement the BERT by ourselves as what they said.) For protecting the privacy, they choose to use federated learning. And then the problem is how to lower the communication cost because of the huge number of the parameters. For the time efficiency, they introduce the ensemble distillation to have teacher models from local dataset to train the student model from central server. Our hyperparameters are different than what paper said since we didn't follow the BERT embedding thing they did. Compared with normal knowledge distillation, their central model and local models use the same nerual network structure. 
## GAD dataset
This is a corpus identifying associations between genes and diseases by a semi-automatic annotation procedure based on the Genetic Association Database. 

For a given dataset, after shuffling the training data, we have 5% as the central dataset, and the remaining data are divided by 10 parts,simulating the existence of local datasets.  In our training, we take 40% of local models are selected for trainning in each communication. After training, the precdition results of the model on the central server are uploaded and then we get the prediction results for all local models are integrated. They are all privoded to central model for learning.

Compared with our results, we also coded the FedAvg algorithm. 
## Poster 
It is under the readme file.
















## citation
@article{Bravo2015,
  doi = {10.1186/s12859-015-0472-9},
  url = {https://doi.org/10.1186/s12859-015-0472-9},
  year = {2015},
  month = feb,
  publisher = {Springer Science and Business Media {LLC}},
  volume = {16},
  number = {1},
  author = {{\`{A}}lex Bravo and Janet Pi{\~{n}}ero and N{\'{u}}ria Queralt-Rosinach and Michael Rautschka and Laura I Furlong},
  title = {Extraction of relations between genes and diseases from text and large-scale data analysis: implications for translational research},
  journal = {{BMC} Bioinformatics}
}

@inproceedings{sui2020feded,
  title={Feded: Federated learning via ensemble distillation for medical relation extraction},
  author={Sui, Dianbo and Chen, Yubo and Zhao, Jun and Jia, Yantao and Xie, Yuantao and Sun, Weijian},
  booktitle={Proceedings of the 2020 conference on empirical methods in natural language processing (EMNLP)},
  pages={2118--2128},
  year={2020}
}
