# Analiza ekonometryczna rynku budownictwa mieszkaniowego w Polsce

## O projekcie
Celem pracy jest zbadanie wpływu wartości produkcji budowlano-montażowej na liczbę mieszkań oddanych do użytku w Polsce[cite: 1]. Projekt obejmuje stworzenie modelu ekonometrycznego oraz wykonanie prognozy na przyszły (pierwszy) kwartał 2024 roku[cite: 1]. 

Analiza opiera się na danych kwartalnych pochodzących z Głównego Urzędu Statystycznego (GUS), obejmujących okres 2016-2024[cite: 1].

## Zmienne w modelu
* **Zmienna objaśniana (Y):** Liczba mieszkań w sztukach[cite: 1]. Zmienna ta opisuje podaż na rynku nieruchomości (finalny efekt procesu inwestycyjnego) i wykazuje sezonowość (mniej mieszkań oddaje się w I kwartale)[cite: 1].
* **Zmienna objaśniająca (X):** Wartość produkcji budowlano-montażowej w mln zł[cite: 1]. Według założeń jest to główny czynnik determinujący liczbę oddawanych mieszkań[cite: 1].
* **Zmienne sztuczne (Z1, Z2, Z3):** Wprowadzone w celu wyeliminowania wahań sezonowych wynikających z cyklu pogodowego i gospodarczego, takich jak zimowe przestoje w budownictwie[cite: 1].
  * **Z1:** Przyjmuje wartość 1 dla I kwartału, 0 dla pozostałych[cite: 1].
  * **Z2:** Przyjmuje wartość 1 dla II kwartału, 0 dla pozostałych[cite: 1].
  * **Z3:** Przyjmuje wartość 1 dla III kwartału, 0 dla pozostałych[cite: 1].
  * *Uwaga: IV kwartał jest okresem bazowym, reprezentowanym przez same zera*[cite: 1].

## Model ekonometryczny
Wykres rozrzutu dla zmiennych wskazał na występowanie dodatniej zależności liniowej[cite: 1].

**Postać teoretyczna:**
`Y_t = α_0 + α_1*X_t + δ_1*Z_1t + δ_2*Z_2t + δ_3*Z_3t + ε_t`[cite: 1]

**Postać oszacowana:**
`Y_t = 33904,7 + 4,77*X_t - 4676,93*Z_1t - 10373,9*Z_2t - 6439,39*Z_3t`[cite: 1]

## Weryfikacja i testy diagnostyczne
Skonstruowany model okazał się poprawny strukturalnie, co potwierdziła weryfikacja kluczowych testów statystycznych[cite: 1]:
* **Istotność parametrów:** Ponieważ p < 0,05, odrzucono hipotezę zerową, co oznacza, że wybrane zmienne są istotne statystycznie[cite: 1].
* **Homoskedastyczność (Test White'a):** Z wartością p = 0,286652 (p > 0,05), brak jest podstaw do odrzucenia hipotezy zerowej[cite: 1]. Wariancje są sobie równe, model jest homoskedastyczny[cite: 1].
* **Normalność reszt (Test Doornika-Hansena):** Z wartością p = 0,34629 (p > 0,05) brak podstaw do odrzucenia hipotezy zerowej[cite: 1]. Oznacza to, że składnik losowy ma rozkład normalny[cite: 1].
* **Autokorelacja (Test Breuscha-Godfreya):** Przy wartości p = 0,8179 (p > 0,05) również brak podstaw do odrzucenia hipotezy zerowej[cite: 1]. W modelu nie występuje autokorelacja rzędu 4[cite: 1].

## Prognoza na pierwszy kwartał 2024 r.
Na podstawie modelu wyznaczono prognozę na I kwartał 2024 roku[cite: 1].

* **Prognoza punktowa (ŷ):** 57 672,73 mieszkań[cite: 1].
* **Prognoza przedziałowa:** Z prawdopodobieństwem 95% rzeczywista wartość zawiera się w przedziale (47972,04; 67373,42)[cite: 1].
* **Wartość rzeczywista (y):** 48 382,00 mieszkań[cite: 1].

### Ocena prognozy
* **Błąd ex ante (V_T*):** Wyniósł 8,19%, co jest zgodne z założeniem projektu (V_T* < 10%) i potwierdza, że prognoza jest dopuszczalna[cite: 1].
* **Błąd ex post (MAPE):** Wyniósł 19,20%, co oznacza, że wyznaczona liczba mieszkań różni się od rzeczywistej o 19,20%[cite: 1]. Odchylenie od danych rzeczywistych przypisano lokalnej anomalii rynkowej[cite: 1].

---
*Autor: Kinga Gnidzińska*[cite: 1]
