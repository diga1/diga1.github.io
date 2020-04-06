
# Bestimmung der Verdopplungszeit

## Einleitung

Beim Vergleich der Corona-Pandemie in verschiedenen Ländern werden oft die absoluten Fallzahlen verglichen. Wenn man sie ins Verhältnis zur Gesamtbevölkerung des entsprechenden Landes bringt, sind sie ein Maß dafür, wieweit die Ausbreitung schon fortgeschritten ist. Aber die absoluten Zahlen sind kein Maß dafür, inwieweit die Situation unter Kontrolle ist, d.h. wie weit man noch von einer Eindämmung entfernt ist. Um das beurteilen zu können, ist die Verdopplungszeit, also die Zeit, in der sich die Fallzahlen verdoppeln, eine bessere Größe. Doch wie bestimmt man die Verdopplungszeit?

Man kann die Verdopplungszeit berechnen, wenn man die Fallzahlen nicht direkt gegen die Zeit aufträgt, sondern die logarithmierten Werte. Bei exponentiellem Wachstum ergeben die logarithmierten Fallzahlen eine Gerade, aus deren Steigung man die Verdopplungszeit berechnen kann. Je steiler die Gerade, desto kürzer die Verdopplungszeit.

Im nächsten Abschnitt kommen die Ergebnisse für die Verdopplungszeiten, im Abschnitt danach dann der mathematische Zusammenhang, wie man sie bestimmt.

Ich verwende die Daten der Johns Hopkins University, und zwar folgende Datei (heruntergeladen am 4.4.20, an dem Tag habe ich die Berechnungen durchgeführt):

https://github.com/CSSEGISandData/COVID-19/blob/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv


## Verdopplungszeiten einiger Länder

Hier zunächst die Fallzahlen für Deutschland:






![png](/images/verdopplungsZeit_files/output_2_0.png)



Man sieht, dass man nicht viel sieht. Jedenfalls kann man nicht erkennen, wie sich die Verdopplungszeit für die Ausbreitung in Deutschland entwickelt hat. Anders sieht die Sache aus, wenn man die logarithmierten Werte in einer Graphik darstellt:






![png](/images/verdopplungsZeit_files/output_4_0.png)



Man erkennt hier schon einiges. Das exponentielle Wachstum hat am 25.2.20 begonnen. Danach gibt es verschiedene Abschnitte, in denen der Verlauf wie eine Gerade aussieht. Und zwischen diesen Abschnitten gibt es jeweils einen Knick. Ich habe für jeden dieser Abschnitte eine Gerade berechnet (genau genommen hat das eine Funktion für mich gemacht). Im nächsten Graphen ist die jeweilige Gerade durch die Punkte gezeichnet, aus denen sie berechnet wurde. Aus der Steigung der Geraden erhält man die Verdopplungszeit, die in der Legende angegeben wird.






![png](/images/verdopplungsZeit_files/output_6_0.png)



Einen Punkt (11.3.) habe ich außen vor gelassen, da er offenbar ein Ausreißer ist.

Man erkennt die linearen Abschnitte sehr gut. Das sind Zeitabschnitte, in denen es exponentielles Wachstum mit einer relativ konstanten Verdopplungszeit gegeben hat. Die Verdopplungszeit nimmt im Lauf der Zeit, d.h. von Abschnitt zu Abschnitt, immer weiter ab. Das würde man auch erwarten, wenn die Maßnahmen greifen. Eine Anomalie zeigt lediglich die gelbe Gerade. Hier streuen die Werte allerdings auch deutlich, so dass das abweichende Verhalten vielleicht auf die zufälligen Schwankungen zurückzuführen ist.

Die deutlichen Knickpunkte sind schon auffällig. Wie sieht es also bei unseren Nachbarn aus?

Hier die logarithmische Kurve für Frankreich:






![png](/images/verdopplungsZeit_files/output_8_0.png)



Das sieht eher abgerundet aus. Man erkennt keine linearen Abschnitte mit Knickpunkten dazwischen. 

Und jetzt Italien:






![png](/images/verdopplungsZeit_files/output_10_0.png)



Man kann lineare Abschnitte gerade so erkennen. Mit hineingerechneten Geraden sieht es so aus:






![png](/images/verdopplungsZeit_files/output_12_0.png)



Und als letztes Land Spanien:






![png](/images/verdopplungsZeit_files/output_14_0.png)



Am oberen Ende lassen sich lineare Bereiche erkennen. Und nun wieder der Graph mit den berechneten Geraden.






![png](/images/verdopplungsZeit_files/output_16_0.png)



Sieht man sich die jüngsten Verdopplungszeiten im Vergleich an, dann hat Italien mit 16,9 Tagen den besten Wert. Deutlich entfernt kommt Deutschland mit 8,9 Tagen, dicht gefolgt von Spanien mit 8,1 Tagen. Der Wert für Frankreich lässt sich mit dieser Methode nicht sicher bestimmen, da die Steigungen zwischen den einzelnen Punkten am Ende zu stark variieren.

## Mathematischer Hintergrund

Die Verdopplungszeit ist nur dann eine konstante Größe, wenn es sich um eine exponentielle Entwicklung handelt. 

Wie misst man die Verdopplungszeit? Man kann versuchen, die Verdopplungszeit direkt an den Fallzahlen abzulesen.


Dazu wählt man sich einen Startzeitpunkt aus und sieht nach, nach wieviel Tagen sich die Fallzahl verdoppelt hat. Dann nimmt man den Startzeitpunkt plus 1 und macht das gleiche, usw. Das ist aufgrund der zufälligen Schwankungen, denen die Fallzahlen unterliegen, recht mühsam. Außerdem ist es schwierig, zu erkennen, ob sich die Entwicklung wirklich auf einem exponentiellen Pfad befindet.

Deshalb ist es günstiger, den Logarithmus zu verwenden. Der Logarithmus (genauer der natürliche Logarithmus, den wir hier verwenden) ist die Umkehrfunktion der Exponentialfunktion. Das bedeutet, dass für jede Zahl x gilt: $\ln(e^x) = x$. Gehen wir also von einer exponentiellen Entwicklung der Fallzahlen $N(t)$ aus, so gilt:

$$N(t) = N_0 \cdot e^{\alpha \cdot t}$$

Wenden wir auf beiden Seiten den Logarithmus an, so erhalten wir:

$$\ln (N(t)) = \ln (N_0 \cdot e^{\alpha \cdot t}) = \ln (N_0) + \ln ( e^{\alpha \cdot t}) = \ln (N_0) + \alpha \cdot t$$

also:

$$\ln (N(t)) = \ln (N_0) + \alpha \cdot t$$

Wenn wir also $\ln (N(t))$, d.h. die logarithmierte Anzahl der Infizierten, gegen die Zeit auftragen, dann erhalten wir einen Graphen der $\ln (N_0) + \alpha \cdot t$ als Funktion der Zeit zeigt. Das ist aber eine Gerade mit dem Achsenabschnitt $\ln (N_0)$ und der Steigung $\alpha$. Aus $\alpha$ können wir dann die Verdopplungszeit $\tau$ über folgende Beziehung ausrechnen:

$$ \tau = \frac{\ln 2}{\alpha }$$

Das erhält man direkt aus dem Ausdruck $ \alpha = \frac{\ln 2}{ \tau}$, den ich im  Post vom 26.03.2020 hergeleitet habe. Die Verdopplungszeit $\tau$ ist also umso kleiner, je steiler die Gerade (d.h. je größer $\alpha$) ist.

Um die Verdopplungszeit zu erhalten, muss man lediglich die Steigung der Geraden bestimmen. Das geht klassisch auf Papier, indem man nach Augenmaß die beste Gerade einzeichnet und die Steigung über ein Steigungsdreieck bestimmt. Oder man verwendet eine Funktion, die einem eine solche Gerade ausrechnet und Achsenabschnitt und Steigung als Output liefert. So habe ich es oben gemacht.


