# Wielowarstwowa sieć jednokierunkowa MLP w Tensorflow, Część I

## Wstęp:

Celem ćwiczenia jest wprowadzenie do biblioteki Tensorflow i  przypomnienie podstawowej sieci MLP i wpływu hiperparametrów na uczenie i jakość otrzymywanych wyników.
Sieć powinna rozwiązywać problem klasyfikacji obrazów ze zbioru  CIFAR-10.  
Należy zdefiniować architekturę modelu, funkcję celu i dostarczyć dane do sieci. (Tensorflow automatycznie oblicza pochodne funkcji celu).


Zadania na laboratorium będą oparte o interfejs Subclassing API. W notebooku znajduje się treść zadania wraz ze zdefiniowanymi klasami bazowymi i narzędziami pomocniczymi.

Paczki, które mogą być dodatkowo zastosowane:  
- numpy  
- scikit-learn (Metryki)  
- matplotlib, seaborn (Wykresy)  
- tqdm (Pasek postępu)


## Lista zadań (Część I): 
1. Wykorzystując klasę bazową zdefiniowaną w BaseLayer zaimplementuj warstwę w pełni połączoną. (Dodawanie zmiennych do warstwy odbywa się za pomocą metody add_weight). Źródło:  https://www.tensorflow.org/api_docs/python/tf/keras/layers/Layer) (0.5 pkt).

2. Wykorzystując klasę bazową zdefiniowaną w BaseModel i zaimplementowaną warstwę w pełni połączoną w zadaniu 1 zdefiniuj architekturę sieci, funkcję uczenia sieci i funkcję ewaluacji (0.5 pkt).  
    **Przetwarzanie wstępne**
    - Spłaszczenie obrazu z wymiaru 32x32x3 na wymiar 3072
    
   **Architektura modelu do implementacji**
    - Warstwa w pełni połączona z 128 neuronami i funkcją aktywacji ReLU
    - Warstwa w pełni połączona z 10 neuronami i funkcją aktywacji Softmax
    
    Inicjalizacja wag: uniform  
    Funkcje aktywacji znajdują się w module tensorflow.keras.activation
    
   **Hiperparametry uczenia**
    - Wielkość paczki: 100
    - Optymalizator: Adam
    - Współczynnik uczenia: 0.01
    - Liczba epok: 10
    - Funkcja kosztu: tf.keras.losses.SparseCategoricalCrossentropy
    
 

3. Przedstaw wykres accuracy, krzywą funkcji kosztu i podaj macierz pomyłek (confusion matrix) (1 pkt)
4. Zwizualizuj kilka przykładów na klasę, dla których model podejmowal złą decyzję i przeanalizuj dlaczego (1 pkt)

Jakość analizy i realizacji (prawidłowość wniosków, klarowność prezentacji, rozumienie modelu, jakość kodu)  (2 pkt)  

### Ograniczenia

1. Zadania 1 i 2 muszą być oddane razem z Zadaniem 3

2. Wykorzystanie gotowych modułów implementujących warstwy sieci np. tensorflow.keras.layers i innych jest zabronione!
