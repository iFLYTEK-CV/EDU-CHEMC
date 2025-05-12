# Introduction
This repository is an official data link of paper "**Handwritten Chemical Structure Image to Structure-Specific Markup Using Random Conditional Guided Decoder**" in ACM MultiMedia 2023. In this paper, we officially introduced the handwritten chemical structure image dataset named **EDU-CHEMC**. Comprising 52,986 handwritten molecular structure images sourced from educational settings, The official download link is available at **https://drive.google.com/drive/folders/1e6BVAYWY386B6o1bncb1PC2z9BdMqjiR**.

## Dataset Application and Competition Relevance
The EDU-CHEMC dataset has been pivotal in supporting the **ICDAR 2024 Competition on Recognition of Chemical Structures**. This competition is built upon the EDU-CHEMC dataset. However, due to competition format requirements and data processing variances, the data utilized in the competition differs somewhat from the original EDU-CHEMC dataset. To access the competition website and utilize the annotation tools, visit: **https://crocs-ifly-ustc.github.io/crocs/index.html**. For comprehensive details about this competition, refer to the paper "ICDAR 2024 Competition on Recognition of Chemical Structures", published in the International Conference on Document Analysis and Recognition 2024.

## Dataset File Instructions
In the EDU-CHEMC dataset, all images are stored within the "EDU-CHEMC" folder. Each image has a corresponding annotation JSON file with the same name. The JSON file contains the following key informations:
- **chemfig**: The original Chemfig string. After installing the Chemfig package, it can be rendered with the assistance of TeX Live.
- **ssml_sd**: The training target of the SSML-SD model. Modeling units are separated by spaces and can be directly input into the encoder-decoder model. Graph format data can also be obtained via simple parsing.
- **ssml_rcgd**: The training target of the SSML-RCGD model. As there are multiple SSML-RCGD targets for one training image, we randomly selected some. Thus, the value corresponding to this key is an array. Each training target is an array sorted by time step, with each element being a three-tuple `(text, reconnection marks, condition input)`. The specific meanings are as follows:
    - **text**: A string representing the basic modeling unit.
    - **condition input**: An integer indicating the index (starting from 0) of the candidate Branch Angle Unit (BAU) to be input into the decoder at the current time step.
    - **reconnection marks**: An array with elements as two-tuples `(reconnection index, bond type)`. Here, **reconnection index** refers to the index of the candidate BAU forming a reconnection with the current-time-step element, and **bond type** represents the reconnection's bond type, presented as a string.
- **ssml_normed**: The submission format for the 2024 ICDAR CROCS competition. For detailed content, visit **https://crocs-ifly-ustc.github.io/crocs/data.html**.

Moreover, the "EDU-CHEMC.vocab" file encompasses all the modeling units.

## Research Expansion and Achievements
Building on prior research, we've expanded relevant methods and achieved remarkable results. The paper "RFL: Simplifying Chemical Structure Recognition with Ring-Free Language" was published in the AAAI 2025 conference and selected for an oral presentation. This paper optimized solution effectiveness, offering novel ideas and methods for the chemical structure recognition field.

## Citation
If you use the **EDU-CHEMC** database in your research, please cite the following references:
```bibtex
@article{Hu2023,  
        author = {Jinshui Hu, Hao Wu, Mingjun Chen, Chenyu Liu, Jiajia Wu, Shi Yin, Baocai Yin, Bing Yin, Cong Liu, Jun Du, Lirong Dai}, 
        title = {Handwritten chemical structure image to structure-specific markup using random conditional guided decoder},  
        journal = {Proceedings of the 31st ACM International Conference on Multimedia},  
        year = {2023}
}  
@article{Chen2024, 
        author  = {Mingjun Chen, Hao Wu, Qikai Chang, Hanbo Cheng, Jiefeng Ma, Pengfei Hu, Zhenrong Zhang, Chenyu Liu, Changpeng Pi, Jinshui Hu, Baocai Yin, Bing Yin, Cong Liu, Jun Du}, 
        title = {ICDAR 2024 Competition on Recognition of Chemical Structures},  
        journal = {International Conference on Document Analysis and Recognition},  
        year = {2024}
}  
@article{Chang2025,
        author  = {Qikai Chang, Mingjun Chen, Changpeng Pi, Pengfei Hu, Zhenrong Zhang, Jiefeng Ma, Jun Du, Baocai Yin, Jinshui Hu}, 
        title  = {RFL: Simplifying Chemical Structure Recognition with Ring-Free Language},  
        journal = {Proceedings of the AAAI Conference on Artificial Intelligence},  
        year = {2025}
}  
``` 
