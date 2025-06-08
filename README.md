## Image Captioning with CNN-RNN (Flickr8k)
This project generates descriptive captions for images using a deep learning model that combines convolutional and recurrent networks.

### Dataset
We use the Flickr8k dataset, which contains:

8,000 images of everyday scenes

5 captions per image written in natural language

Each image is stored in the Images/ folder and associated captions are in captions.txt.

### Architecture
The model follows an Encoder-Decoder sequence-to-sequence architecture:

#### Encoder: CNN
Model: Pretrained ResNet-50

Purpose: Extracts high-level image features

Freezes all ResNet layers to speed up training

Final layer replaced with a linear layer to produce fixed-size embeddings

#### Decoder: RNN
Model: Bidirectional LSTM

Purpose: Takes image features and generates a sequence of words

Embedding Layer: Converts word indices into vectors

LSTM Layer: Processes the sequence

Linear Layer: Maps LSTM outputs to vocabulary space

### Training Details
Loss: CrossEntropyLoss (ignores <PAD>)

Optimizer: Adam

Scheduler: StepLR

Beam Search supported during caption generation for better quality

Vocabulary built using a frequency threshold to reduce rare words

#### Features
Load and preprocess images

Build vocabulary from captions

Visualize random training samples


### Future Work
Add attention mechanism

Fine-tune CNN layers

Use Transformer decoder for better language modeling

Add BLEU score evaluation

