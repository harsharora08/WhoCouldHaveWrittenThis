## Who Could Have Written This? – A Neural Network Model that matches entered prompt with artists' styles

A Deep Learning Network Model trained on thousands of lyrics of ten artists, and tells whose style of writing an input prompt matches the most.

---

## Data Collection

The data was collected from [Genius](https://genius.com/) and the API wrapper used is [Wrap-Genius.](https://github.com/fedecalendino/wrap-genius)

## Data Processing and Model Training

The lyrics were stripped from blanks and duplicates were removed. Resampling was done as per requirements.

Texts were then vectorized and fitted into a neural network model whose summary is as follows

```plaintext
Model: "sequential_1"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 embedding_1 (Embedding)     (None, 216, 216)          3095280   
                                                                 
 global_average_pooling1d_1   (None, 216)              0         
 (GlobalAveragePooling1D)                                        
                                                                 
 dropout_3 (Dropout)         (None, 216)               0         
                                                                 
 dense_3 (Dense)             (None, 432)               93744     
                                                                 
 dropout_4 (Dropout)         (None, 432)               0         
                                                                 
 dense_4 (Dense)             (None, 648)               280584    
                                                                 
 dropout_5 (Dropout)         (None, 648)               0         
                                                                 
 dense_5 (Dense)             (None, 16)                10384     
                                                                 
=================================================================
Total params: 3,479,992
Trainable params: 3,479,992
Non-trainable params: 0
_________________________________________________________________
```

The model scored 86.78% accuracy

## Model Implementation

The models were saved and now they are ready to get tested on real prompts.

Head over to [this Colab notebook](https://colab.research.google.com/drive/1IBo-NfqLF6DVMvGyKLCiUSn-dmz-toch?usp=sharing) to test your own prompts!
