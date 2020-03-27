
# Corona-Fallzahlen und die Exponentialfunktion

Für die Beantwortung der Frage, wie sich die Corona-Fallzahlen weiter entwickeln werden, gehen wir im ersten Schritt davon aus, dass es sich um exponentielles Wachstum handelt. Das ist sicherlich nicht ganz richtig, aber diese Annahme ist gut genug, um sich einen ersten Überblick zu verschaffen. Weiter unten gibt es Zahlen, die ich mit einem realistischeren Modell berechnet habe.

Nochmals: Die Formeln, die jetzt kommen, sind für die daran Interessierten. Man kann sie aber auch einfach überspringen.

Die Exponentialfunktion beschreibt also die Zahl der Infizierten für jeden Zeitpunkt. Eine bekannte Form, die Exponentialfunktion zu schreiben lautet:

$$N(t) = N_0 \cdot e^{\alpha \cdot t}$$

Dabei ist $e$ die Eulersche Zahl. Der Buchstabe $t$ (engl: time) ist die Zeit in Tagen, die wir einsetzen werden. Beispielsweise könnten wir $t = 5$ einsetzen, um die Fallzahl in 5 Tagen auszurechnen. Dann gibt es noch $N_0$ und $\alpha$ (sprich: alpha). Diese Werte bestimmen die genaue Form der speziellen Exponentialfunktion, die uns den Verlauf der Fallzahlen ab heute anzeigen soll. 

$N_0$ ist der Startwert, also die Fallzahl von heute (heute ist $t = 0$). Wir wählen $N_0 = 37000$, weil das ungefähr die Fallzahl ist, die die John Hopkins University für den 25.03.2020 für Deutschland angibt.



In den Medien fällt immer wieder der Begriff der Verdopplungs-Zeit. Das ist der Zeitraum, in dem sich die Anzahl der Infizierten verdoppelt. Nennen wir sie $\tau$ (sprich: tau). Die Verdopplungszeit $\tau$ legt fest, was wir für $\alpha$ wählen müssen, um die für unseren Fall korrekte Exponentialfunktion zu erhalten. Der Zusammenhang ist:

$$ \alpha = \frac{\ln 2}{ \tau}$$

Dabei ist $\ln$ der natürliche Logarithmus, und $\ln 2$ ist ungefähr gleich 0,6931.

Den Zusammenhang zwischen $\alpha$ und $\tau$ erhält man wie folgt.

*Beweis Anfang*

Gesucht wird die Zeit $\tau$, die die Ausgangsfallzahl verdoppelt, also muss gelten:

$$N(\tau) = 2 \cdot N_0 $$
 
Setzt man andererseits $\tau$ in die Exponentialfunktion ein, ergibt sich:

$$N(\tau) = N_0 \cdot e^{\alpha \cdot \tau}$$

wenn man beide Gleichungen zusammen nimmt, erhält man:

$$N_0 \cdot e^{\alpha \cdot \tau} = 2 \cdot N_0$$

$N_0$ fällt weg. Dann wendet man auf beide Seiten den natürlichen Logarithmus an. Da er die Umkehrfunktion zur Exponentialfunktion ist, gilt für jede Zahl x, $ln(e^x) = x$, also:

$$ \ln(e^{\alpha \cdot \tau}) = \ln 2 $$

$$ \alpha \cdot \tau = \ln 2$$

$$ \alpha = \frac{\ln 2}{ \tau}$$

*Beweis Ende*


Dann benötigen wir noch eine Zahl für die Verdopplungs-Zeit $\tau$. Sie lag in Deutschland den letzten 5 Tagen etwas über 5.  Für die folgenden Berechnungen nehmen wir die Zahl 5 als Verdopplungszeit. Wie man die Verdopplungszeit bestimmt, kommt im nächsten Beitrag.

Damit haben wir alles zusammen, um die Exponentialfunktion ausrechnen zu können. $N_0 = 37000$ und $ \alpha = \frac{\ln 2}{ 5}$, also:

$$N(t) = 37000 \cdot e^{(\frac{\ln 2}{ 5} \cdot t)}$$

Rechnen wir für die ersten 20 Tage die Werte aus: 







<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>t</th>
      <th>Nexp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>37000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>42501</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>48821</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>56081</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>64420</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5</td>
      <td>74000</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>85003</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7</td>
      <td>97643</td>
    </tr>
    <tr>
      <th>8</th>
      <td>8</td>
      <td>112163</td>
    </tr>
    <tr>
      <th>9</th>
      <td>9</td>
      <td>128841</td>
    </tr>
    <tr>
      <th>10</th>
      <td>10</td>
      <td>148000</td>
    </tr>
    <tr>
      <th>11</th>
      <td>11</td>
      <td>170007</td>
    </tr>
    <tr>
      <th>12</th>
      <td>12</td>
      <td>195287</td>
    </tr>
    <tr>
      <th>13</th>
      <td>13</td>
      <td>224326</td>
    </tr>
    <tr>
      <th>14</th>
      <td>14</td>
      <td>257683</td>
    </tr>
    <tr>
      <th>15</th>
      <td>15</td>
      <td>296000</td>
    </tr>
    <tr>
      <th>16</th>
      <td>16</td>
      <td>340014</td>
    </tr>
    <tr>
      <th>17</th>
      <td>17</td>
      <td>390574</td>
    </tr>
    <tr>
      <th>18</th>
      <td>18</td>
      <td>448652</td>
    </tr>
    <tr>
      <th>19</th>
      <td>19</td>
      <td>515366</td>
    </tr>
  </tbody>
</table>
</div>



Ganz links in der Tabelle ist ein Zeilen-Zähler abgebildet (der ist bei der Tabellenfunktion, die ich verwende, automatisch dabei). In der Spalte mit der Überschrift t sind die Zeiten angegeben (in Tagen), also die erste Zeile steht für heute, die zweite für morgen usw. In der Spalte Nexp (exp, weil wir hier die unveränderte Exponentialfunktion verwendet haben) sind die Fallzahlen eingetragen. Heute steht dort 37000, so wie es sein sollte.

Man sieht, dass sich die Fallzahlen nach 5 Tagen auf 74000 verdoppelt haben und nach weiteren 5 Tagen auf 148000. Das stimmt also damit überein, dass wir die Verdopplungszeit von 5 Tagen in die Formel eingesetzt haben.

Eine Fallzahl von 370000, das ist das zehnfache des Startwerts, liegt zwischen den Zeilen 16 und 17. Eine Verdopplungszeit von 5 Tagen führt also zu einer Verzehnfachung der Fallzahlen in knapp zweieinhalb Wochen. In den nächsten zweieinhalb Wochen sind es dann 3,7 Mio Infizierte usw. Eine längere Tabelle mit weiteren Werten gibt es ganz unten.

Zunächst einmal folgt hier eine graphische Darstellung. Unten von links nach rechts ist die Zeit in Tagen ab heute aufgetragen und nach oben die Fallzahlen:





![png](/images/blogExponentialfunktion_v02_files/output_3_0.png)



Man erkennt das erst langsame und dann explosionsartige Anwachsen der Exponentialfunktion. Bis zu 10 Mio. Infizierten dauert es ca. 40 Tage. 5 Tage später sind es dann 20 Mio. Infizierte.

Es ist aber auch zu erkennen, dass die Exponentialfunktion das Geschehen nicht korrekt beschreibt. Nach 57 Tagen gäbe es laut Graphik über 100 Mio. Infizierte. Das kann natürlich bei einer Bevölkerungszahl von 83 Mio. gar nicht sein. Deshalb gibt es weiter unten eine Graphik und eine Tabelle, die mit einem verbesserten Modell berechnet wurde. Dieses verbesserte Modell berücksichtigt zwei Effekte. Erstens gibt es immer weniger Personen ohne Immunisierung, die das Virus infizieren kann. Zweitens endet für jede Person die Zeit, in der sie andere noch infizieren kann. Entweder weil sie wieder gesund geworden oder verstorben ist.

Diese beiden Effekte führen dazu, dass die Kurve mit wachsenden Fallzahlen immer mehr unterhalb der reinen Exponentialfunktion bleibt. Die mit dem verbesserten Model berechneten Fallzahlen sind mit Nmodel bezeichnet:






![png](/images/blogExponentialfunktion_v02_files/output_5_0.png)



Die Zeit $t = 0$ ist wieder heute. Man erkennt, dass die Exponentialfunktion bis Tag 30 die Entwicklung noch ganz gut beschreibt, sich danach aber immer mehr von dem realistischeren Model entfernt. 

Da in dieses Modell aber Annahmen eingehen, die auch nur geschätzt sind, ist auch dieser Verlauf nur eine Annäherung an die Realität. Aber man sieht, dass die Kurve in eine Sättigung läuft, was im Gegensatz zur Exponentialfunktion schon deutlich besser ist. Bei wieviel Millionen diese Sättigung liegt, hängt sehr stark davon ab, welche Zeit man annimmt, in der eine Person infektiös ist. Ich habe hier 17 Tage gewählt. Das steht für 3 Tage Inkubationszeit plus 14 Tage Krankheitsepisode. Vermutlich gibt es gerade bei den Personen im Krankenhaus deutlich längere Krankheitsepisoden, andererseits sind diese Patienten wohl auch besser isoliert. 

Aufgrund der Unkenntnis wichtiger Einflussgrößen lässt sich naturgemäß keine genaue Vorausberechnung anstellen. Aber für die Anfangsphase der Corona-Pandemie, in der wir uns noch befinden, ist die Exponentialfunktion eine gute Annäherung. Für die Berechnung benötigt man neben dem Startwert, der einfach die Fallzahl heute ist, nur die Verdopplungszeit. Wie man die berechnet, kommt im nächsten Beitrag.

Hier nun die Tabelle mit den Zahlen für 70 Tage. Die Spalte Nexp enthält die mit der Exponentialfunktion berechneten Werte, die Spalte Nmodel die mit dem realistischeren Modell ermittelten Werte und die Zeile mit t = 0 ist heute. Die Spalte t zählt also die Tage ab heute, d.h. also ab dem 25.03.2020:





<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>t</th>
      <th>Nexp</th>
      <th>Nmodel</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>37000</td>
      <td>37000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>42501</td>
      <td>41960</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>48821</td>
      <td>47554</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>56081</td>
      <td>53868</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>64420</td>
      <td>60998</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5</td>
      <td>74000</td>
      <td>69050</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>85003</td>
      <td>78146</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7</td>
      <td>97643</td>
      <td>88418</td>
    </tr>
    <tr>
      <th>8</th>
      <td>8</td>
      <td>112163</td>
      <td>100018</td>
    </tr>
    <tr>
      <th>9</th>
      <td>9</td>
      <td>128841</td>
      <td>113115</td>
    </tr>
    <tr>
      <th>10</th>
      <td>10</td>
      <td>148000</td>
      <td>127899</td>
    </tr>
    <tr>
      <th>11</th>
      <td>11</td>
      <td>170007</td>
      <td>144586</td>
    </tr>
    <tr>
      <th>12</th>
      <td>12</td>
      <td>195287</td>
      <td>163419</td>
    </tr>
    <tr>
      <th>13</th>
      <td>13</td>
      <td>224326</td>
      <td>184669</td>
    </tr>
    <tr>
      <th>14</th>
      <td>14</td>
      <td>257683</td>
      <td>208646</td>
    </tr>
    <tr>
      <th>15</th>
      <td>15</td>
      <td>296000</td>
      <td>235697</td>
    </tr>
    <tr>
      <th>16</th>
      <td>16</td>
      <td>340014</td>
      <td>266211</td>
    </tr>
    <tr>
      <th>17</th>
      <td>17</td>
      <td>390574</td>
      <td>300631</td>
    </tr>
    <tr>
      <th>18</th>
      <td>18</td>
      <td>448652</td>
      <td>339450</td>
    </tr>
    <tr>
      <th>19</th>
      <td>19</td>
      <td>515366</td>
      <td>383227</td>
    </tr>
    <tr>
      <th>20</th>
      <td>20</td>
      <td>592000</td>
      <td>432585</td>
    </tr>
    <tr>
      <th>21</th>
      <td>21</td>
      <td>680029</td>
      <td>488228</td>
    </tr>
    <tr>
      <th>22</th>
      <td>22</td>
      <td>781149</td>
      <td>550942</td>
    </tr>
    <tr>
      <th>23</th>
      <td>23</td>
      <td>897304</td>
      <td>621609</td>
    </tr>
    <tr>
      <th>24</th>
      <td>24</td>
      <td>1030732</td>
      <td>701215</td>
    </tr>
    <tr>
      <th>25</th>
      <td>25</td>
      <td>1184000</td>
      <td>790865</td>
    </tr>
    <tr>
      <th>26</th>
      <td>26</td>
      <td>1360059</td>
      <td>891790</td>
    </tr>
    <tr>
      <th>27</th>
      <td>27</td>
      <td>1562298</td>
      <td>1005364</td>
    </tr>
    <tr>
      <th>28</th>
      <td>28</td>
      <td>1794609</td>
      <td>1133116</td>
    </tr>
    <tr>
      <th>29</th>
      <td>29</td>
      <td>2061464</td>
      <td>1276746</td>
    </tr>
    <tr>
      <th>30</th>
      <td>30</td>
      <td>2368001</td>
      <td>1438137</td>
    </tr>
    <tr>
      <th>31</th>
      <td>31</td>
      <td>2720118</td>
      <td>1619373</td>
    </tr>
    <tr>
      <th>32</th>
      <td>32</td>
      <td>3124596</td>
      <td>1822750</td>
    </tr>
    <tr>
      <th>33</th>
      <td>33</td>
      <td>3589218</td>
      <td>2050793</td>
    </tr>
    <tr>
      <th>34</th>
      <td>34</td>
      <td>4122929</td>
      <td>2306266</td>
    </tr>
    <tr>
      <th>35</th>
      <td>35</td>
      <td>4736002</td>
      <td>2592183</td>
    </tr>
    <tr>
      <th>36</th>
      <td>36</td>
      <td>5440237</td>
      <td>2911813</td>
    </tr>
    <tr>
      <th>37</th>
      <td>37</td>
      <td>6249192</td>
      <td>3268679</td>
    </tr>
    <tr>
      <th>38</th>
      <td>38</td>
      <td>7178436</td>
      <td>3666557</td>
    </tr>
    <tr>
      <th>39</th>
      <td>39</td>
      <td>8245858</td>
      <td>4109453</td>
    </tr>
    <tr>
      <th>40</th>
      <td>40</td>
      <td>9472004</td>
      <td>4601586</td>
    </tr>
    <tr>
      <th>41</th>
      <td>41</td>
      <td>10880475</td>
      <td>5147339</td>
    </tr>
    <tr>
      <th>42</th>
      <td>42</td>
      <td>12498384</td>
      <td>5751207</td>
    </tr>
    <tr>
      <th>43</th>
      <td>43</td>
      <td>14356873</td>
      <td>6417715</td>
    </tr>
    <tr>
      <th>44</th>
      <td>44</td>
      <td>16491717</td>
      <td>7151317</td>
    </tr>
    <tr>
      <th>45</th>
      <td>45</td>
      <td>18944008</td>
      <td>7956270</td>
    </tr>
    <tr>
      <th>46</th>
      <td>46</td>
      <td>21760951</td>
      <td>8836469</td>
    </tr>
    <tr>
      <th>47</th>
      <td>47</td>
      <td>24996768</td>
      <td>9795265</td>
    </tr>
    <tr>
      <th>48</th>
      <td>48</td>
      <td>28713747</td>
      <td>10835239</td>
    </tr>
    <tr>
      <th>49</th>
      <td>49</td>
      <td>32983434</td>
      <td>11957955</td>
    </tr>
    <tr>
      <th>50</th>
      <td>50</td>
      <td>37888016</td>
      <td>13163689</td>
    </tr>
    <tr>
      <th>51</th>
      <td>51</td>
      <td>43521902</td>
      <td>14451132</td>
    </tr>
    <tr>
      <th>52</th>
      <td>52</td>
      <td>49993537</td>
      <td>15817108</td>
    </tr>
    <tr>
      <th>53</th>
      <td>53</td>
      <td>57427494</td>
      <td>17256285</td>
    </tr>
    <tr>
      <th>54</th>
      <td>54</td>
      <td>65966868</td>
      <td>18760935</td>
    </tr>
    <tr>
      <th>55</th>
      <td>55</td>
      <td>75776032</td>
      <td>20320746</td>
    </tr>
    <tr>
      <th>56</th>
      <td>56</td>
      <td>87043804</td>
      <td>21922708</td>
    </tr>
    <tr>
      <th>57</th>
      <td>57</td>
      <td>99987074</td>
      <td>23551120</td>
    </tr>
    <tr>
      <th>58</th>
      <td>58</td>
      <td>114854988</td>
      <td>25187710</td>
    </tr>
    <tr>
      <th>59</th>
      <td>59</td>
      <td>131933736</td>
      <td>26811904</td>
    </tr>
    <tr>
      <th>60</th>
      <td>60</td>
      <td>151552065</td>
      <td>28401234</td>
    </tr>
    <tr>
      <th>61</th>
      <td>61</td>
      <td>174087608</td>
      <td>29931887</td>
    </tr>
    <tr>
      <th>62</th>
      <td>62</td>
      <td>199974149</td>
      <td>31379369</td>
    </tr>
    <tr>
      <th>63</th>
      <td>63</td>
      <td>229709976</td>
      <td>32719251</td>
    </tr>
    <tr>
      <th>64</th>
      <td>64</td>
      <td>263867472</td>
      <td>33927967</td>
    </tr>
    <tr>
      <th>65</th>
      <td>65</td>
      <td>303104131</td>
      <td>34983601</td>
    </tr>
    <tr>
      <th>66</th>
      <td>66</td>
      <td>348175216</td>
      <td>35866631</td>
    </tr>
    <tr>
      <th>67</th>
      <td>67</td>
      <td>399948298</td>
      <td>36560582</td>
    </tr>
    <tr>
      <th>68</th>
      <td>68</td>
      <td>459419952</td>
      <td>37052558</td>
    </tr>
    <tr>
      <th>69</th>
      <td>69</td>
      <td>527734944</td>
      <td>37333627</td>
    </tr>
  </tbody>
</table>
</div>


