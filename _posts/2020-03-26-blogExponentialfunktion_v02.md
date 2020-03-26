# Corona-Fallzahlen und die Exponentialfunktion

Für die Beantwortung der Frage, wie sich die Corona-Fallzahlen weiter entwickeln werden, gehen wir im ersten Schritt davon, dass es sich um exponentielles Wachstum handelt. Das ist sicherlich nicht ganz richtig, aber diese Annahme ist gut genug, um sich einen ersten Überblick zu verschaffen. Weiter unten gibt es Zahlen, die ich mit einem realistischeren Modell berechnet habe.

Nochmals: Die Formeln, die jetzt kommen, sind für die daran Interessierten. Man kann sie aber auch einfach überspringen.

Die Exponentialfunktion beschreibt also die Zahl der Infizierten für jeden Zeitpunkt. Eine bekannte Form, die Exponentialfunktion zu schreiben, verwendet die nätürliche Zahl $e$ und lautet:

$$N(t) = N_0 \cdot e^{\alpha \cdot t}$$

Der Buchstabe $t$ (engl: time) ist die Zeit, die wir einsetzten werden. Beispielsweise könnten wir $t = 5$ einsetzen, um die Fallzahl in 5 Tagen auszurechnen. Dann gibt es noch $N_0$ und $\alpha$ (sprich: alpha). Diese Werte bestimmen die genaue Form der speziellen Exponentialfunktion, die uns den Verlauf der Fallzahlen ab heute anzeigen soll. 

$N_0$ ist der Startwert, also die Fallzahl von heute (heute ist $t = 0$). Wir wählen $N_0 = 37000$, weil das ungfähr die Fallzahl ist, die die John Hopkins University für den 25.03.2020 für Deutschland angibt.



In den Medien fällt immer wieder der Begriff der Verdopplungs-Zeit. Das ist der Zeitraum, in dem sich die Anzahl der Infizierten verdoppelt. Nennen wir sie $\tau$ (sprich: tau). Die Verdopplungszeit $\tau$ legt fest, was wir für $\alpha$ wählen müssen, um die für unsern Fall korrekte Exponentialfunktion zu erhlaten. Der Zusammenhang ist:

$$ \alpha = \frac{\ln 2}{ \tau}$$

Dabei ist $\ln$ der natürliche Logarithmus, und $\ln 2$ ist ungefähr gleich 0,6931.

Dann benötigen wir noch eine Zahl für die Verdopplungs-Zeit $\tau$. Sie lag in Deutschland den letzten 5 Tagen so um die 5.  Für die folgenden Berechnungen nehmen wir die Zahl 5 als Verdopplungszeit. Wie man die Verdopplungszeit bestimmt, kommt im nächsten Beitrag.

Damit haben wir alles zusammen, um die Exponentialfunktion ausrechnen zu können. $N_0 = 37000$ und $ \alpha = \frac{\ln 2}{ 5}$, also:

$$N(t) = 37000 \cdot e^{(\frac{\ln 2}{ 5} \cdot t)}$$

Rechnen wir für die ersten 20 Tage die Werte aus: 


Ganz links in der Tabelle ist ein Zeilen-Zähler abgebildet (der ist bei der Tabellenfunktion, die ich verwende, automatisch dabei). In der Spalte mit der Überschrift t sind die Zeiten angegeben (in Tagen), also die erste Zeile steht für heute, die zweite für morgen usw. In der Spalte Nexp (exp, weil wir hier die unveränderte Exponentialfunktion verwendet haben) sind die Fallzahlen eingetragen. Heute steht dort 37000, so wie es sein sollte.

Man sieht, dass sich die Fallzahlen nach 5 Tagen auf 74000 verdoppelt haben und nach weiteren 5 Tagen auf 148000. Das stimmt also damit überein, dass wir die Verdopplungszeit von 5 Tagen in die Formel eingesetzt haben.

Eine Fallzahl von 370000, das ist das zehnfache des Startwerts, liegt zwischen den Zeilen 16 und 17. Eine Verdopplungszeit von 5 Tagen führt also zu einer Verzehnfachung der Fallzahlen in knapp zweieinhalb Wochen. In den nächsten zweieinhalb Wochen sind es dann 3,7 Mio Infizierte usw. Eine längere Tabelle mit weiteren Werten gibt es ganz unten.

Zunächst einmal folgt hier eine graphische Darstellung. Unten von links nach rechts ist die Zeit in Tagen ab heute aufgetragen und nach oben die Fallzahlen:


Man erkennt das erst langsame und dann explosionsartige Anwachsen der Exponentialfunktion. Bis zu 10 Mio. Infizierten dauert es ca. 40 Tage. 5 Tage später sind es dann 20 Mio. Infizierte.

Es ist aber auch zu erkennen, dass die Exponentialfunktion das Geschehen nicht korrekt beschreibt. Nach 57 Tagen gäbe es laut Graphik über 100 Mio. Infizierte. Das kann natürlich bei einer Bevölkerungszahl von 83 Mio. gar nicht sein. Deshalb gibt es weiter unten eine Graphik und eine Tabelle, die mit einem verbesserten Modell berechnet wurde. Dieses verbesserte Modell berücksichtigt zwei Effekte. Erstens, gibt es immer weniger Gesunde, die das Virus infizieren kann. Zweitens endet für jede Person, die Zeit, in der sie andere infizieren kann. Entweder weil sie wieder gesund geworden oder verstorben ist.

Diese beiden Effekte führen dazu, das die Kurve mit wachsenden Fallzahlen immer mehr unterhalb der reinen Exponentialfunktion bleibt. Die mit dem verbesserten Model berechneten Fallzahlen sind mit Nmodel bezeichnet:

Man erkennt, dass die Exponentialfunktion bis Tag 30 die Entwicklung noch ganz gut beschreibt, sich danach aber immer mehr von dem realistischeren Model entfernt. 

Da in dieses Modell aber Annahmen eingehen, die auch nur geschätzt sind, ist auch dieser Verlauf nur eine Ännäherung an die Realität. Aber man sieht, dass die Kurve in eine Sättigung läuft, was im Gegensatz zur Exponentialfunktion schon deutlich besser ist. Bei wieviel Millionen diese Sättigung liegt, hängt sehr stark davon ab, welche Zeit annimmt, in der eine Person infektiös ist. Und in welchem Verhältnis diese Zeit zur Verdopplungszeit steht.

Aufgrund der Unkenntnis wichtiger Einflussgrößen läßt sich naturgemäß keine genaue Vorausberechnung anstellen. Aber für die Anfangsphase der Corona-Pandemie, in der wir uns noch befinden, ist die Exponentialfunktion eine gute Näherung. 
Für die Berechnung benötigt man neben dem Startwert, der einfach die Fallzahl heute ist, nur die Verdopplungszeit. Wie man die berechnet, kommt im nächsten Beitrag.

Hier nun die Tabelle mit den Werten für die 60 Tage:
