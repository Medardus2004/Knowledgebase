# Allgemeine Relativitätstheorie

## Physikalische Grundlagen
### Bezugssysteme
Das **Machsche Prinzip** kritisiert den absoluten Raum, sondern geht nur von Bewegungen in Bezug zu allen anderen Körpern des Universums aus.
Der **metrische Tensor** ist symmetrisch. Die beschleunigte Bewegung legt den metrischen Tensor nur teilweise fest, willkürliche Koordinatentransformationen können dessen Form ändern.
Die Komponenten des metrischen Tensors sind als Beschleunigungspotenziala anzusehen. Dessen Funktion sind die relativistischen Gravitationspotenziale. 

### Äquivalenzprinzip
Das Äquivalenzprinzip besagt, dass Gravitationskräfte äquivalent zu Trägheitskräften sind. 
Das bedeutet, dass ein Schwerefeld durch Übergang in einer beschleunigtes KS eleminiert werden kann
Aquivalenzprinzip: Im lokalen IS gelten die gesetze der SRT. (Das LOKALE IS ist kein IS!!!)
Ein Raum mit einem Wegelement wie in 10.7 heißt Riemannscher Raum.
Für reale Gravitationsfelder gibt es keine GLOBALE Transformation, die 10.7 auf die Minkowsiform bringt. 
Die Einsteinschen Feldgleichungen beschreiben den Zusammenhang zwischen den Gravitationsfeldern und ihren Quellen

### Bewegung im Gravitationsfeld
Die Gravitationskräfte werden durch die Christophelsymbole beschrieben, die proportional zur ersten Ableitung im metrischen Tensor sind.

### Gravitationsrotverschiebung
Wenn die hochenergetische Strahlung eines bestimmten kernübergangs von gleichartigen Kernen wieder absorbiert wird werden, spricht man von Resonanzfluoreszenz.
Bei Rückstoßfreier Resonanzfluoreszenz, dem Mößbauer-Effekt, kommt es zu sehr scharfen Gamma-Linien.
Vergleich einer Uhr, die auf der Erdoberfläche ruht mit der in einem Satalliten:
Die Satellitenuhr geht 

i) schneller, weil das Gravitationspotenzial am Ort des Satelliten schwächer ist

ii) langsamer, weil die Geschwindigkeit des Satelliten gröer ist.

### Geometrische Aspekte
Der metrische Tensor bestimmt die Eigenschaften des Raums. Dazu gehört insbesondere die Krümmung.
Die Gestalt des metrischen Tensors ist durch die Eigenschaften des Raums nicht eindeutig festgelegt. 
Vielmehr kann sie durch die Wahl anderer Koordinaten im Raum verändert werden.

Äußere Krümmung kann man sich mit einem Blatt Papier erklären, dass man rollt. Zwar kommt es zu einer Verbiegung, die Metrik bleibt aber gleich.

Für eine Krümmung ist die Koordinatenabhängigkeit des metrischen Tensors notwendig aber nicht hinreichend:
Raum gekrümmt ==> metrische Tensor ist koordinatenabhängig.

Die durch die Bewegungsgleichungen eines Teilchens im Gravitationsfeld zurückgelegte Bahnen sind zugleich die geodätischen Linien in dem durch den metrischen Tensor definierten Riemannschen Raum.
## Mathematische Grundlagen

### Tensoren im Riemannschen Raum
Unter einer Mannigfaltigkeit versteht man in der Mathematik einen topologischen Raum, der lokal dem euklidischen Raum gleicht. Global muss die Mannigfaltigkeit jedoch nicht einem euklidischen Raum gleichen (nicht zu ihm homöomorph sein).

### Kovariante Ableitung
Im Riemannschen Raum ist die partielle Ableitung eines Tensorfelder im Allgemeinen kein Tensorfeld. Stattdessen führt man die kovariante Ableitung ein. Die kovariante Ableitung eines Tensorfeldes ist wieder ein Tensorfeld.

Für diese Ableitung gilt:

1. Die kovariante Ableitung ergibt wieder einen Tensor entsprechender Stufe im Riemannschen Raum

2. Im Minkowski Raum oder im lokalen Inertialsystem reduziert sich die kovariante Ableitung auf die partielle Ableitung

3. Es gelten die üblichen Rechenregeln für die Ableitung, insbesondere die Kettenregel.

### Parallelverschiebung
Der Zusatzterm der kovarianten Ableitung kann geometrisch als Parallelverschiebung interpretiert werden.

### Krümmungstensor
Der Krümmungstensor wird zur Aufstellung der Feldgleichungen der Allgemeinen Relativitätstheorie benötigt.
Aus dem metrischen Tensor kann man den Krümmungstensor berechnen. Genau dann, wenn dieser Tensor verschwindet , ist der Raum eben.
Man kann sagen, dass der Kürmmungstensor der einzige Tensor ist, der aus dem metrischen Tensor und seinen ersten und zweiten Ableitungen gebildet werden kann und der linear in der ersten und zweiten Ableitung ist.

## Grundgesetze der ART
### Kovarianzprinzip
Insgesamt erhalten wir aus der Isotropieannahme eine Vorschrift zur Aufstellung gültiger Gesetze: Die gesuchte Gleichung muss folgende Bedingung erfüllen:
- Kovarianz unter allgemeinen Koordinatentransformationen. Dies bedeutet, dass das Gesetz die Form einer Riemann-Tensorgleichung haben muss
- Gültigkeit im Lokalen Inertialsystem.

Das Wegelement ist sowohl ein Lorentz, wie auch ein Riemann-Skalar

### Gesetze mit Gravitation
Wenn wir von einem direkten Drehmoment auf den Spin absehen, können wir folgende Fälle unterscheiden:
1. Teilchen im Gravitationsfeld
2. Teilchen in einem anderen Kraftfeld (Thomas-Präzession)
3. Teilchen im Kraftfeld mit einem anderen Kraftfeld (Fermi-Transport)

### Einsteinsche Feldgleichungen
Die Einsteinschen Feldgleichungen können nicht mit Hilfe des Kovarianzprinzips abgeleitet werden, denn im lokalen Interialsystem gibt es keine Feldgleichungen, deren kovariante Ableitung zu finden wäre.
Die Einsteinschen Feldgleichungen können aber weitgehend daduch festgelegt werden, dass sie kovariant und möglichst einfach sind und das sie den Newtonschen Grenzfall enthalten.

Skizze: wir verallgemeinern vom Newtonschen Grenzfall auf die naheliegende relativistische Verallgemeinerung. Eine Analogie zur Elektrodynamik ist aber nicht gültig, da jede Energieform einen Beitrag zur Masse liefert und daher eine Quelle des Gravitationsfelds darstellt. Wir setzen den EnergieImpuls-Tensor vorerst mit einem unbekannten Riemann-Tensor proportional. Dieser muss folgende Eigenschaften erfüllen:
1. Er wird aus der ersten und zweiten Ableitung des metrischen Tensors gebildet. Dabei ist der Riemann-Tensor linear in der zweiten und quadratisch in der ersten Ableitung
2. Er hat die gleichen Symmetrie-Eigenschaften wie der Energie-Impuls-Tensor
3. Für ein schwaches stationäres Feld muss sich der Newtonsche Grenzfall ergeben

Man kann in die so gewonnene Gleichung noch einen Zusatzterm einfügen, der linear zum metrischen Tensor ist. Aktuelle Weltmodelle favorisieren diese kosmologische Konstante.

### Struktur der Feldgleichungen
Für schwache felder wir der Energie-Impuls-Tensor des Gravitationsfelds aufgestellt. In diesem Grenzfall können die Feldgleichungen linearisiert werden und ihre allgemeine Lösung kann angegeben werden.

Da der Riemann-Tensor symmetrisch ist, hat er nur 10 unabhängige Komponenten, d.h. die Feldgleichungen sind 10 algebraisch unabhängige Gleichungen. 

Aufgrund einer Bedingung des Riemann-Tensors sind nur 6 der Einsteinschen Feldgleichungen unabhängig. Daher können die Feldgleichungen die 10 Funktionen nicht vollständig festlegen. Diese Freiheit kann genutzt werden, um die Lösung eines Problems durch die Wahl geeigneter Koordinaten zu vereinfachen.

Auch in der Elektrodynamik sind die Potenziale nicht eindeutig durch die Feldgleichungen festgelegt. Die Maxwellgleichungen stellen 4 algebraisch unabhängige Gleichungen für die 4 unbekannten Felder auf. Allerdings werden diese durch eine Bedingung auf 3 funktional unabhängige Gleichungen reduziert

Da die Feldgleichungen nichtlinear sind, gibt es kein Standardverfahren zur Lösung der Gleichungen bei gegebenen Quellen. Es gibt jedoch:
1. Exakte Lösungen unter vereinfachenden Annahmen
2. Lösungen der linearisierten Feldgleichungen für schwache Felder
3. Post-Newtonsche Näherungen der Feld- und der Bewegungsgleichungen für schwache Felder und für langsam bewegte Teilchen

## Statische Gravitationsfelder

Wir befassen uns hier mit statischen Gravitationsfeldern.
### Isotropische statische Metrik
Die Reobertson Entwicklung hat den Sinn, die Lösung der Bewegungsgleichungen im Gravitationsfeld ergibt Vorhersagen für physikalische Effekte, die von dimenstionslosen Parametern abhängen.
## Gravitationswellen

## Statische Sternmodelle

## Dynamische Sternmodelle

## Kosmologie
