# Come ho scelto gli iperparametri?

Introdurre un early stopping manuale o c'è qualche funzione che permette di farlo automaticamente?

#### Batch Size

Non troppo grande o non troppo piccolo. Generalmente sarebbe da testare prima su un set più piccolo prima di farlo sul dataset completo.

#### Learning Rate

A parità di accuracy e di tempo impiegato, cambia qualcosa un learning rate alto o basso?

#### Loss Function

Dipende dalla tipologia di problema da risolvere. Classificazione vs Regressione

# Test effettuati usando la softmax:

| # | N1    | N2     | Output Shape    | Num Epochs | Batch Size | Learning Rate | CPU Times | Average Loss | Accuracy |
| - | ------- | ------------ | ------- |------- | ------- | ------- | ------- | ------- | ------- |
| #1 Cambio n1, n2 | 256 | 128 | 1 | 30 | 256 | 0.01 | 3min 56s | 4.3207 | 5486/10000 (55%) |
| #2 Cambio n1, n2 | 128 | 64 | 1 | 30 | 256 | 0.01 | 3min 56s | 3.8917 | 2938/10000 (29%) |
| #3 Cambio n1, n2 | 256 | 64 | 1 | 30 | 256 | 0.01 | 3min 56s | 3.7979 | 3883/10000 (39%) |
| #4 Cambio LR | 512 | 256 | 1 | 30 | 128 | 0.1 | 3min 58s | 5.16000 | 3918/10000 (39%) | 
| #5 Cambio LR | 512 | 256 | 1 | 30 | 128 | 0.01 | 3min 56s | 5.1637 | 3891/10000 (39%) |
| #6 Cambio LR | 512 | 256 | 1 | 30 | 128 | 0.001 | 3min 56s |  5.4514 | 1000/10000 (10%) |
| #7 Cambio Batch Size| 512 | 256 | 1 | 30 | 256 | 0.01 | 3min 56s | 5.2566 | 2959/10000 (30%) |