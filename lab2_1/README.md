# Konwolucyjna sieć neuronowa, Cześć I

## Wstęp

Poznanie możliwości sieci konwolucyjnej (CNN) w zadaniu klasyfikacji obrazów w bibliotece Tensorflow. Sieć powinna rozwiązywać problem klasyfikacji obrazów ze zbioru CIFAR-10 dataset. 

## Lista zadań (Część I)

1. Zaimplementuj zdefiniowaną poniżej architekturę sieci konwolucyjnej (2 pkt)

| Blok | Warstwy | Wymiar filtra | Liczba kanałów wejściowych | Liczba kanałów wejściowych | Przesunięcie / krok (ang. stride) |
| --- | --- | --- | --- | --- | --- |
| conv1 | Konwolucja <br /> ReLU <br /> Max-pool | [5,5] <br /> - <br /> [3,3]| 3 <br /> - <br /> - | 64 <br /> - <br /> - | [1, 1] <br /> - <br /> [2, 2] |
| conv2 | Konwolucja <br /> ReLU <br /> Max-pool | [5,5] <br /> - <br /> [3,3]| 64 <br /> - <br /> - | 64 <br /> - <br /> - | [1, 1] <br /> - <br /> [2, 2] |
| flatten | Spłaszczenie | - | - | - | - | 
| fc1 | Warstwa w pełni połączona <br /> ReLU | [dim(conv2), 384] | - | - | - |
| fc2 | Warstwa w pełni połączona  <br /> ReLU | [384, 192] | - | - | - |
| fc3 | Warstwa w pełni połączona  <br /> Softmax | [192, 10] | - | - | - |

2. Dobierz odpowiednie hiperparametry uczenia modelu oraz przetestuj różne parametry sieci konwolucyjnej 
(rozmiar filtra, zastosowanie innej metody pooling), tak aby model mógł klasyfikować przykłady ze zbioru testowego z dokładnością (ang. accuracy) co najmniej 70%. 
Dla każdego przetestowanego modelu przedstaw wartość metryki accuracy oraz dokonaj porównania tych modeli (2 pkt)

3. Dla znalezionego najlepszego modelu przedstaw (1 pkt):
- wykres zależności accuracy od numeru epoki 
- krzywą funkcji kosztu w zależności od numeru epoki
- macierz pomyłek (confusion matrix)
- wizualizację kilku przykładów na klasę, dla których model podejmowal złą decyzję (przeanalizuj dlaczego model mógł źle sklasyfikować*)

\* Dla ambitnych (niepunktowane): Wykorzystaj następujące narzędzia w celu interpretacji decyzji sieci:
- [What-If Tool](https://pair-code.github.io/what-if-tool/index.html#features) - nakładka do Tensorboarda. Na stronie znajduje się zakładka `Smile Detection`, zawierająca wizualizację dla problemu klasyfikacji.
- `tf-explain` ([link](https://github.com/sicara/tf-explain)) - dodatek do Tensorflowa, implementujący jedne z ostatnich metod w dziedzinie wyjaśnialnej sztucznej inteligencji (explainable AI lub XAI). Metody pozwalają zwizualizować, jakie obszary obrazu najbardziej przyczyniły się do podjęcia decyzji. Ich dokładny opis znajduje się w publikacjach, można je znaleźć po nazwach metod.
