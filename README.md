# adversarial-melanoma-classification
This is an in-progress set of models for lesion classification, trained on the 23k images in the ISIC archive. The file `preprocessor.ipynb` is a custom data preprocessor, which turns the images and labels in the raw 50GB archive into 20 large  PyTorch tensors - 10 of these are image tensors with shape (~2100, 3, 216, 303), and the other 10 are their corresponding labels.

The file `trainer.ipynb` is a neural network training pipeline. The best-performing model is currently a pre-trained CNN (VGG-19) with the final, fully-connected layer fine-tuned on the ISIC archive. Currently, I am using the novel methodology in a recent [paper](https://arxiv.org/pdf/1905.02175.pdf) to attempt to construct a lesion classifier resistant to [adversarial inputs](https://openai.com/blog/adversarial-example-research/).

The `models/`, `raw_data/` and `data/` folders are `.gitignore`'d. An updated repository will contain a few of the best performing models pending my implementation of Git Large File Storage.
