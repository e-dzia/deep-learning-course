# Sieci rekurencyjne w NLP, Część I

## Wstęp:

 Ćwiczenie jest wprowadzeniem do zastosowania sieci rekurencyjnych w analizie języka naturalnego. W ramach zadania należy przebadać wyniki w zadaniu analizy sentymentu na zbiorze recenzji IMDB: 
 
 https://ai.stanford.edu/~amaas/data/sentiment/
 
 Zbiór dostępny jest w module tf.keras.datasets
 
 W pierwszej części zadania należy zaimplementować i przebadać działanie sieci na danych zakodowanych w postaci wektorów one-hot.


## Lista zadań: 

 1. Zaimplementuj w Tensorflow sieć rekurencyjną LSTM. W implementacji dozwolone jest wykorzystanie operacji w tf.keras.backend, ale nie gotowych warstw. Rekurencję można zaimplementować wykorzystując operację tf.keras.backend.rnn, której podać trzeba własnoręcznie napisaną definicję kroku. (2 pkt)

 2. Dobierz hiperparametry uczenia tak, aby zmaksymalizować otrzymane wyniki. Przedstaw wyniki w oparciu o które dokonany został dobór końcowych parametrów. (2pkt)

 3. Porównaj wynik sieci LSTM z prostą siecią rekurencyjną. Oceń zysk z zastosowania komórki LSTM. W porównaniu przedstaw:
   - krzywą funkcji kosztu w zależności od epoki
   - krzywą accuracy w zależności od epoki dla zbioru testowego i uczącego
  (1pkt)


