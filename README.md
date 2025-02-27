# FlappyBirdAI
FlappyBird AI Trained using NEAT in python to beat the game
# Flappy Bird: Treniranje Veštačke Inteligencije sa Neuronskim Mrežama i Genetskim Algoritmima

## Uvod
Flappy Bird je popularna igra jednostavnog koncepta, gde igrač kontroliše pticu kako bi izbegao prepreke. U ovom projektu, igra je automatizovana korišćenjem veštačke inteligencije, konkretno neuronskih mreža i genetskih algoritama, kroz biblioteku NEAT (NeuroEvolution of Augmenting Topologies). Cilj je da se trenira agent (ptica) da postigne što bolji rezultat autonomno, bez ljudske intervencije.

## Opis Projekta
Projekat koristi Python i Pygame za simulaciju igre, dok se NEAT biblioteka koristi za implementaciju neuronske mreže koja pokreće ponašanje ptice. Ptica donosi odluke o skakanju na osnovu trenutne visine, udaljenosti do cevi i visinske razlike između ptice i otvora cevi.

### Arhitektura Igra
Igra se sastoji od nekoliko klasa:
- **Bird**: Predstavlja agenta koji se trenira. Implementira logiku skakanja, kretanja i crtanja.
- **Pipe**: Predstavlja prepreke koje ptica treba da izbegne.
- **Base**: Donji deo ekrana koji se pomera zajedno sa cevima.
- **Fitness funkcija**: Implementirana u funkciji `fitness`, koristi se za evaluaciju performansi svakog genoma u populaciji.

## Veštačka Inteligencija

### Neuronske Mreže
NEAT koristi jednostavne neuronske mreže koje se evoluiraju tokom vremena. Mreža se inicijalno kreira kao "Feed-Forward" mreža sa nekoliko ulaza:
- Visina ptice (`bird.y`)
- Udaljenost od gornje cevi
- Udaljenost od donje cevi

Izlaz mreže je binarna odluka o tome da li ptica treba da skoči (`output[0] > 0.5`).

### Genetski Algoritam
Genetski algoritam optimizuje mrežu kroz evoluciju populacije:
1. **Inicijalizacija populacije**: Generiše se početna nasumična populacija ptica.
2. **Evaluacija fitnesa**: Svaka ptica dobija fitnes poene na osnovu pređenih cevi.
3. **Selekcija i ukrštanje**: Najbolji genomi se ukrštaju da bi stvorili novu generaciju.
4. **Mutacija**: Mreže se povremeno nasumično menjaju kako bi se istražile nove strategije.

## Treniranje i Evaluacija
Tokom treniranja, fitnes funkcija daje nagrade pticama koje duže preživljavaju i prolaze više cevi. Kada ptica udari u cev ili padne na zemlju, njen fitnes se smanjuje. Evolucija se odvija kroz nekoliko generacija dok agent ne postigne zadovoljavajuće performanse.

## Zaključak
Projekat uspešno pokazuje kako se neuronske mreže mogu optimizovati korišćenjem genetskih algoritama. NEAT pristup omogućava automatsko dodavanje novih neurona i veza tokom evolucije, što doprinosi fleksibilnosti i potencijalu za učenje složenijih obrazaca ponašanja. Ovaj pristup se može primeniti i na složenije probleme u oblasti veštačke inteligencije i mašinskog učenja.

