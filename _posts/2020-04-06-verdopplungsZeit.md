

## Einleitung

Beim Vergleich der Corona-Pandemie in verschiedenen Ländern, werden oft die absoluten Fallzahlen verglichen. Wenn man sie ins Verhältnis zur Gesamtbevölkerung des entsprechenden Landes bringt sind, sie ein Maß dafür, wieweit die Ausbreitung schon fortgeschritten ist. Aber die absoluten Zahlen sind kein Maß dafür, inwieweit die Situation unter Kontrolle ist, d.h. wie weit man noch von einer Eindämmung entfernt ist. Um das beurteilen zu können, ist die Verdopplungszeit, also die Zeit, in der sich die Fallzahlen verdoppeln, eine wichtige Größe. Doch wie mißt man die Verdopplungszeit.

Man kann die Verdopplungszeit berechnen, wenn man die Fallzahlen nicht direkt gegen die Zeit aufträgt, sondern die logarithmierten Werte. Bei exponentiellem Wachstum ergeben die logarithmierten Fallzahlen eine Gerade, aus deren Steigung man die Verdopplungszeit berechnen kann. Umso steiler die Gerade, umso kürzer die Verdopplungszeit.

Im nächsten Abschnitt kommen die Ergebnisse für die Verdopplungzeiten, im Abschnitt danach dann der mathematische Zusammenhang.

## Verdopplungszeiten einiger Länder

Hier zunächst die Fallzahlen für Deutschland:






![png](2020-04-06-verdopplungsZeit_files/output_1_0.png)



Man sieht, dass man nicht viel sieht. Jedenfalls kann man nicht erkennen, wie sich die Verdopplungszeit für die Ausbreitung in Deutschland entwickelt hat. Anders sieht die Sache aus, wenn man die logarithmierten Werte in einer Graphik darstellt:






![png](2020-04-06-verdopplungsZeit_files/output_3_0.png)



Man erkennt hier schon einiges. Das exponentielle Wachstum hat am 25.3.20 begonnen. Danach gibt es verschiedene Abschnitte, in denen der Verlauf wie eine Gerade aussieht. Und zwischen diesen Abschnitten gibt es jeweils einen Knick. Ich habe für jeden dieser Abschnitte jeweils eine Gerade berechnet (genau genommen hat das eine Funktion für mich gemacht). Im nächsten Graphen ist die jeweilige Gerade durch die Punkte gezeichnet, aus denen sie berechnet wurde. Aus der Steigung der Geraden erhält man die Verdopplungszeit, die in der Legende ausgegeben wird.






![png](2020-04-06-verdopplungsZeit_files/output_5_0.png)



Einen Punkt (11.3.) hab ich außen vor gelassen, da er offenbar ein Ausreißer ist.

Man erkennt die linearen Abschnitte sehr gut. Das sind Zeitabschnitte, in denen es exponentielles Wachstum mit eine relativ konstanten Verdopplungszeit gegeben hat. Die Verdopplungzeit nimmt im Lauf der Zeit , d.h. von Abschnitt zu Abschnitt, immer weiter ab. Das würde man auch erwarten, wenn die Maßnahmen greifen. Eine Anomalie zeigt lediglich die gelbe Gerade. Hier streuen die Werte allerding auch deutlich, so dass das abweichende Verhalten vielleicht auf die zufällichen Schwankungen zurückzufühen ist.

Die deutlichen Knickpunkte sind schon auffällig. Wie sieht es also bei unseren Nachbarn aus?

Hier die logarithmische Kurve für Frankreich:






![png](2020-04-06-verdopplungsZeit_files/output_7_0.png)



Das sieht abgerundet aus. Man erkennt keine linearen Abschnitte mit Knickpunkten dazwischen. 

Und jetzt Italien:






![png](2020-04-06-verdopplungsZeit_files/output_9_0.png)



Man kann lineare Abschnitte gerade so erkennen. Mit hineingerechneten Geraden sieht es so aus:






![png](2020-04-06-verdopplungsZeit_files/output_11_0.png)



Und als letztes Land Spanien:






![png](2020-04-06-verdopplungsZeit_files/output_13_0.png)



Im oberen Bereich lassen sich linerare Bereiche erkennen. Wieder mit den Geraden.






![png](2020-04-06-verdopplungsZeit_files/output_15_0.png)



## Mathematischer Hintergrund

Die Verdopplungszeit ist nur dann eine konstante Größe, wenn es sich um eine exponentielle Entwicklung handelt. 

Wie misst man die Verdopplungszeit? Man kann versuchen, die Verdopplungszeit direkt an den Fallzahlen abzulesen.


Man wählt sich dazu einen Startzeitpunkt aus und sieht nach, nach wievil Tagen sich die Fallzahl verdoppelt hat. Dann nimmt man die nächste Zahl den Startzeitpunkt plus 1 und macht das gleiche, usw. Das ist aufgrund der zufälligen Schwankungen, denen die Fallzahlen unterliegen recht mühsam. Außerdem ist es schwierig, zu erkennen, ob sich die Entwicklung wwirklich auf einem exponentiellen Pfad befindet.

Deshalb ist es günstiger den Logarithmus zu verwenden. Der Logarithmus (genauer der natürliche Logarithmus, den wir hier verwenden) ist die Umkehrfunktion der Exponentialfunktion. Das bedeutet, dass für jede Zahl x gilt $\ln(e^x) = x$. Gehen wir also von einer exponentiellen Enwicklung der Fallzahlen $N(t)$ aus, so gilt:

$$N(t) = N_0 \cdot e^{\alpha \cdot t}$$

Wenden wir auf beiden Seiten den Logarithmus an, so erhalten wir:

$$\ln (N(t)) = \ln (N_0 \cdot e^{\alpha \cdot t}) = \ln (N_0) + \ln ( e^{\alpha \cdot t}) = \ln (N_0) + \alpha \cdot t$$

also:

$$\ln (N(t)) = \ln (N_0) + \alpha \cdot t$$

Wenn wir also $\ln (N(t))$, d.h. die logarithmierten Infiziertenzahlen, gegen die Zeit auftragen, dann erhalten wir einen Graphen der $\ln (N_0) + \alpha \cdot t$ als Funktion der Zeit zeigt. Das ist aber einen Gerade mit dem Achsenabschnitt $\ln (N_0)$ und der Steigung $\alpha$. Aus $\alpha$ können wir dann die Verdopplungszeit $\tau$ über folgende Beziehung ausrechnen:

$$ \tau = \frac{\ln 2}{\alpha }$$

Das erhält man direkt aus dem Ausdruck $ \alpha = \frac{\ln 2}{ \tau}$, den ich im  Post vom 26.03.2020 hergeleitet. Die Verdopplungzeit $\tau$ ist also umso kleiner, je steiler die Gerade (d.h. je größer $\alpha$) ist.

Um die Verdopplungszeit zu erhalten, muss man lediglich die Steigung der Geraden bestimmen. Das geht klassisch auf Papier, indem man nach Augenmaß die beste Gerade einzeichnet und die Steigung über ein Steigungsdreieck bestimmt. Oder man verwendet eine Funktion, die einem eine solche Gerade ausrechnet und Achsenabschnitt und Steigung als Output liefert. So habe ich es oben gemacht.


