# Analiza ekonometryczna rynku budownictwa mieszkaniowego w Polsce

## O projekcie
Celem pracy jest zbadanie wpływu wartości produkcji budowlano-montażowej na liczbę mieszkań oddanych do użytku w Polsce. Projekt obejmuje stworzenie modelu ekonometrycznego oraz wykonanie prognozy na przyszły (pierwszy) kwartał 2024 roku. 

Analiza opiera się na danych kwartalnych pochodzących z Głównego Urzędu Statystycznego (GUS), obejmujących okres 2016-2024.

## Zmienne w modelu
* **Zmienna objaśniana (Y):** Liczba mieszkań w sztukach. Zmienna ta opisuje podaż na rynku nieruchomości (finalny efekt procesu inwestycyjnego) i wykazuje sezonowość (mniej mieszkań oddaje się w I kwartale).
* **Zmienna objaśniająca (X):** Wartość produkcji budowlano-montażowej w mln zł. Według założeń jest to główny czynnik determinujący liczbę oddawanych mieszkań.
* **Zmienne sztuczne (Z1, Z2, Z3):** Wprowadzone w celu wyeliminowania wahań sezonowych wynikających z cyklu pogodowego i gospodarczego, takich jak zimowe przestoje w budownictwie.
  * **Z1:** Przyjmuje wartość 1 dla I kwartału, 0 dla pozostałych.
  * **Z2:** Przyjmuje wartość 1 dla II kwartału, 0 dla pozostałych.
  * **Z3:** Przyjmuje wartość 1 dla III kwartału, 0 dla pozostałych.
  * *Uwaga: IV kwartał jest okresem bazowym, reprezentowanym przez same zera*.

## Model ekonometryczny
Wykres rozrzutu dla zmiennych wskazał na występowanie dodatniej zależności liniowej.

**Postać teoretyczna:**
`Y_t = α_0 + α_1*X_t + δ_1*Z_1t + δ_2*Z_2t + δ_3*Z_3t + ε_t`

**Postać oszacowana:**
`Y_t = 33904,7 + 4,77*X_t - 4676,93*Z_1t - 10373,9*Z_2t - 6439,39*Z_3t`

## Weryfikacja i testy diagnostyczne
Skonstruowany model okazał się poprawny strukturalnie, co potwierdziła weryfikacja kluczowych testów statystycznych:
* **Istotność parametrów:** Ponieważ p < 0,05, odrzucono hipotezę zerową, co oznacza, że wybrane zmienne są istotne statystycznie.
* **Homoskedastyczność (Test White'a):** Z wartością p = 0,286652 (p > 0,05), brak jest podstaw do odrzucenia hipotezy zerowej. Wariancje są sobie równe, model jest homoskedastyczny.
* **Normalność reszt (Test Doornika-Hansena):** Z wartością p = 0,34629 (p > 0,05) brak podstaw do odrzucenia hipotezy zerowej. Oznacza to, że składnik losowy ma rozkład normalny.
* **Autokorelacja (Test Breuscha-Godfreya):** Przy wartości p = 0,8179 (p > 0,05) również brak podstaw do odrzucenia hipotezy zerowej. W modelu nie występuje autokorelacja rzędu 4.

## Prognoza na pierwszy kwartał 2024 r.
Na podstawie modelu wyznaczono prognozę na I kwartał 2024 roku.

* **Prognoza punktowa (ŷ):** 57 672,73 mieszkań.
* **Prognoza przedziałowa:** Z prawdopodobieństwem 95% rzeczywista wartość zawiera się w przedziale (47972,04; 67373,42).
* **Wartość rzeczywista (y):** 48 382,00 mieszkań.

### Ocena prognozy
* **Błąd ex ante (V_T*):** Wyniósł 8,19%, co jest zgodne z założeniem projektu (V_T* < 10%) i potwierdza, że prognoza jest dopuszczalna.
* **Błąd ex post (MAPE):** Wyniósł 19,20%, co oznacza, że wyznaczona liczba mieszkań różni się od rzeczywistej o 19,20%. Odchylenie od danych rzeczywistych przypisano lokalnej anomalii rynkowej.

---
*Autor: Kinga Gnidzińska*
