# Understanding Deep Learning Requires Rethinking Generalization

Link to paper: https://arxiv.org/pdf/1611.03530.pdf

## Overview:
This paper puts into question, conventional wisdom. It shows that large neural networks can actually fit random labels, that is labels that remain fixed but, for example, have no relationship to what is actually in the image. The key finding to this paper to me, is that optimization using a neural network remains an easy problem but generalization is challenging to guarantee given that training of a neural network can converge even on random labels.


## Write-up:
From the paper, the implication seems to show that neural networks can "memorize" the data. This explains the high training performance when actual labels are replaced with random label assignments that don't correlate with patterns in the data. This begs the question of why neural networks can learn meaningful, generalizable representations when there are meaningful patterns in the data. In my opinion, in the former case, with no meaningful associations between features and labels, the neural network is able to tune the large number of parameters it has (n << d) to memorize the noise. In the latter case, with meaningful associations, patterns can be established within the structure of neural networks that can incorporate information in a compositional/hierachical fashion. This can actually be seen in other research where researchers try to visualize what the neurons learn after optimization by generating heatmaps or salience maps (e.g., Grad-CAM).

The result is surprising and counterintuitive, as traditional machine learning algorithms tend to not converge when there is no association between features and labels (poor training performance). Here, it is shown due to the large dimensionality of the weight space of neural networks, any dataset can be fitted perfectly to its labels but generalize poorly to the test data. Some explicit regularizers are also shown to not help in this case, such as weight decay, although if there are meaningful associations between features and labels, there is a improvement in generalization. The authors' conclusion that explicit regularizers are neither necessary or sufficient in generalization goes to show that more research needs to be conducted to establish reliable methods of generalization.

Final thoughts: Neural networks are extremely powerful but it is really a tool which can be easily misused if one is not careful with establishing/verifying the associations between features and labels in the dataset. 