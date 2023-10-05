# FL x Security in Network Management

This tutorial has been presented at the [14th International Conference on Network of the Future](https://nof.dnac.org) (NoF 2023) on Wednesday 4th October 2023. This repository contains the materials, including the Jupyter notebooks and the presentations support, that have been used during the tutorial.

> :warning: If you attended the presentation, you have observed the disappointing results at the end of part III. In their current state, the notebooks are not fully reproducible. We are working on it and will update the repository as soon as possible. 

## Abstract

Federated learning (FL) is a machine learning (ML) paradigm that enables distributed agents to learn collaborative models without sharing data. In the context of network security, FL promises to improve the detection and mitigation of attacks, notably by virtually extending the local dataset of each participant. However, one of the major challenges of this recent technology is the heterogeneity of the data used by the participants. Indeed, some participants with very different monitoring contexts could penalize the global model. Furthermore, identifying malicious contributions is made more difficult in heterogeneous environments.

In this tutorial, we will first present the fundamentals of federated learning, then focus on its use in network monitoring, and more specifically, in collaborative intrusion detection (Federated Learning-based Intrusion Detection System—FIDS). Secondly, we will address some of the open research questions in this context, before focusing on the problem of training data heterogeneity. Finally, we will discuss the security of FL architectures, and more specifically, the problem of poisoning attacks. All these parts will be illustrated by hands-on exercises, guided step by step throughout the tutorial.

## Speakers

### Yann Busnel

<p align="center">
    <img src="./img/yann.png" alt="Yann Busnel - NoF 2023" style="width: 50%; max-width: 200px;">
</p>

Yann Busnel has joined IMT Nord Europe as Dean of Research and Innovation from June 2023. After more than 15 years of experience as a faculty, including 6 years as a full professor at IMT Atlantique and member of the IRISA laboratory, he now oversees all research and innovation activities in line with Institut Mines-Télécom’s strategy. He contributes closely to the definition of strategic orientations and to the operational management of the institution. He also represents the Executive Board internally and externally with its partners in the research environment.

He holds an Habilitation to Supervise Research and a PhD respectively from the École Normale Supérieure de Rennes and the University of Rennes. After starting his career in Italy (La Sapienza Universita di Roma), he worked at the University of Nantes, then at ENSAI in Rennes, before joining IMT. As a professor at IMT, he was previously head of the Rennes campus of IMT Atlantique, in charge of education and research purposes.

His research topics are mainly related to Models for large-scale distributed systems and networks, with application in Data stream analysis, Cybersecurity, Massive health data and Artificial Intelligence. Recently, his areas of application range from (i) cybersecurity and dependability to (3) the analysis of medical data, in the context of pharmacovigilance or genomic sequence analysis, and (3) the self-organized coordination of fleets of drones. He is co-head of the national network of research on Distributed Systems and Networks (GDR RSD and GDR Security). He has published over 100 articles in peer-reviewed journals and conferences. He has also coordinated several national and international collaborative research projects.


### Léo Lavaur

<p align="center">
    <img src="./img/leo.png" alt="Leo Lavaur - NoF 2023" style="width: 50%; max-width: 200px;">
</p>

Léo Lavaur received the engineering degree in information security from the National Engineering School, South Brittany (ENSIBS), Vannes, France, in 2020. He is currently pursuing the Ph.D. degree in cybersecurity with the Engineering School, IMT Atlantique and the Chair on Cybersecurity in Critical Networked Infrastructures (Cyber CNI), Rennes, France. During his studies, he also worked in industry with Orange Cyberdefense as a part-time Employee for three years, where he worked on application security, and Wi-Fi rogue access-point detection and location.

He now studies the collaboration in security systems, and how to share data without compromising security. His current research focuses on the challenges of using federated learning as a framework for collaborative intrusion detection systems. In particular, he works on the detections of malicious contributions in heterogeneous environments, as well as on the creation of datasets for evaluating FIDS in heterogeneous settings.

## Tutorial content

This tutorial is structured as an alternation between lectures and practical exercises. Lectures will take about 20 to 30 minutes each, with the exercises filling the rest. This program is divided in three parts:

1. fundamentals of FL,
2. FL for collaborative security,
3. security of FL architectures.

**Fundamentals of FL.** First, we will introduce the audience to FL and some of its applications, from general framework to the context of network management. In the practical part, learners will be introduced to Flower, an open-source FL framework, and to existing datasets for network security. The objective is to lay the foundations for the rest of the tutorial, and to make sure that everyone has the necessary knowledge to follow.

**FL for collaborative security.** In this part, we will focus on the use of FL in the context of network security, and more specifically, in collaborative intrusion detection (Federated Learning-based Intrusion Detection System—FIDS). The lecture will give an overview of the challenges of collaborative security in FL, with a focus on the heterogeneity between clients. In the practical exercise, we will implement common models on standard IDS datasets and observe these challenge through small experiments.

**Security in collaborative FL.** Finally, the last lecture will address some challenges of running FIDS in terms of security. Depending on the exposure of the federation (open or closed entrance, trustworthiness of the participants, etc.), such collaborative architectures can be vulnerable to various types of attacks. The lecture will especially focus on the problem of data poisoning, and how it can be mitigated. In particular, we will talk about the difficulty of detecting such attacks in heterogeneous environments, with leads from the literature, and mention some of our current research on the topic. The practical exercise will be a hands-on experiment on data poisoning, where attendees will be able to observe the impact of such attacks on the models, and how existing works try to mitigate them.

## Materials

### Repository structure

The repository is structured as follows:
```bash
.
│   # Materials
├── notebooks
│   ├── part1.ipynb  # Part I: Fundamentals of FL
│   ├── part2.ipynb  # Part II: FL for collaborative security
│   └── part3.ipynb  # Part III: Security in collaborative FL
├── slides.pdf       # Slides of the presentation
│   
│   # Dependencies management
├── pyproject.toml   # Python dependencies (Poetry)
├── poetry.lock      # ^
├── poetry.toml      # ^
├── flake.nix        # Nix dependencies (Flake)
├── flake.lock       # ^
└── README.md        # This file
```

### Installation

The project uses [Poetry](https://python-poetry.org) for Python dependencies management, and [Nix](https://nixos.org) for system dependencies management.

If you are a Nix user, the easiest way to install the dependencies is to use the provided `flake.nix` file, which will create a virtual environment with all the necessary dependencies, including the Python ones. To do so, simply run the following command from anywhere inside the repository, and open the Jupyter notebooks from the generated shell session.
```bash
nix develop
```

If you are not a Nix user, you can still use Poetry to install the Python dependencies. To do so, run the following command at the root of the respository.
```bash
poetry install
```
You can then use the generated virtual environment to run the notebooks. If not, you can open a shell session using `poetry shell` and run `jupyter notebook` from there.




