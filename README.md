# NLVL_DETR: Neural Network Architecture

`NLVL_DETR` (<ins>N</ins>atural <ins>L</ins>anguage <ins>V</ins>ideo <ins>L</ins>ocalization <ins>De</ins>tection <ins>Tr</ins>ansformer) is a neural network designed for the task of localizing moments in videos based on natural language queries. This architecture integrates both video and text processing modules, and uses a Transformer-based encoder-decoder mechanism to predict the span of the relevant video segment.

```plaintext
+--------------+    +--------------------+    +---------------------+    +---------------------+         +---------------------+    +-----------------+
|              |    |                    |    |      Kmeans or      |    |                     | context |                     |    |                 |
| Video Frames +--->| Vision Transformer +--->| Positional Encoding +--->| Transformer Encoder +-------->| Transformer Decoder +--->| Span Prediction |
|              |    |                    |    |                     |    |                     |         |                     |    |                 |
+--------------+    +--------------------+    +---------------------+    +---------------------+         +---------------------+    +-----------------+
                                                                                                                     ^
+------------+    +-------+                                                                                          |
|            |    |       |                        input sequence                                                    |
| Text Query +--->| Phi-2 +-------------------------------------------------------------------------------------------
|            |    |       |
+------------+    +-------+
```

To view training/eval loss metrics, run `tensorboard --logdir results`

Link to the [Charades-STA](https://prior.allenai.org/projects/charades) dataset. "Data (scaled to 480p, 13GB)" was used for this project.
