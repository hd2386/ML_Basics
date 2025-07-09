# Maschinelles Lernen Exam Notes

## Task 1: Allgemeines Verständnis

### 1. Definieren Sie kurz Supervised, Unsupervised und Reinforcement Learning und nennen Sie je ein Beispielverfahren

*🔴 Supervised Learning:*
- Lernen mit gelabelten Daten: Modell wird auf Paare (input, output) trainiert.
- *Beispiel:* Lineare Regression, Decision Trees, SVM (Support Vector Machine)

*🟡 Unsupervised Learning:*
- Lernen ohne Labels, Muster in Daten entdecken
- *Beispiel:* k-Means Clustering

*🟢 Reinforcement Learning:*
- Lerne durch Interaktion mit einer Umgebung
- Agent lernt durch Belohnung und Bestrafung
- *Beispiel:* Spielstrategie lernen mit Q-Learning

### 2. Erläutern Sie den Unterschied zwischen Parametric und Non-Parametric Methoden und geben Sie je ein Beispiel

*⚡ Parametric:*
- Feste Anzahl von Parametern, unabhängig von Datensatzgröße
- *Beispiel:* Lineare Regression

*📊 Non-Parametric:*
- Anzahl Parameter wächst mit Datensatzgröße
- *Beispiel:* k-Nearest Neighbor (speichert alle Trainingsdaten)


### 3. Beschreiben Sie das Bias–Variance Trade-off und seine Bedeutung für Over-/Underfitting:

![Bias-Variance-Trade-off](https://github.com/user-attachments/assets/92a132a1-9c51-479f-8b48-24937e66b97f)


*🎯 Bias:* Systematischer Fehler durch zu vereinfachte Modellannahmen

*📈 Variance:* Empfindlichkeit gegenüber Schwankungen in Trainingsdaten

*⚠️ Underfitting:* Hoher Bias, niedrige Variance (zu einfaches Modell)

*🔥 Overfitting:* Niedriger Bias, hohe Variance (zu komplexes Modell)

### 4. Machine-Learning-Workflow

![machine_learning-workflow](https://github.com/user-attachments/assets/77ae9b80-e9b2-494f-b8a2-fb16eff7c5c1)

### EXTRA: Erläutern Sie den Unterschied zwischen Regression und Classification in Supervised Learning und geben Sie je ein Beispiel.

| Aspekt              | Classification                          | Regression                            |
|---------------------|------------------------------------------|----------------------------------------|
| 🎯 Zielvariable     | Kategorisch (z. B. „Ja“ / „Nein“)        | Numerisch (z. B. 3.14, 42)             |
| 🧩 Ziel             | Daten in Klassen einteilen               | Einen konkreten Zahlenwert vorhersagen |
| 📈 Beispielmodell   | Logistic Regression, Decision Tree       | Lineare Regression, SVR                |
| 👥 Beispiel         | Spam-Erkennung, Bildklassifikation       | Hauspreisvorhersage, Temperatur        |

### EXTRA: Erläutern Sie den Unterschied zwischen White Models und Black Box Models
- White Models: Hohe Interpredability (Linear Regression)
- Black Box Models: Hohe Prediction accuracy (Neuronale Netze, GenAI)

---

## Task 2: Classification Metrics


### 1. Gegeben sei die folgende Confusion-Matrix eines binären Klassifikators auf 200 Beispielen:

|              | pred = Pos    | pred = Neg | 
|--------------|---------------|-------------|
| true = Pos   | 50             | 10            
| true = Neg   | 30             | 110           



### Berechnungen:

*a) Accuracy:*

Accuracy = (TP + TN) / (Gesamt)
         = (50 + 110) / 200
         = 160 / 200 = 0.8 = 80%


*b) Precision:*

Precision = TP / (TP + FP)
          = 50 / (50 + 30)
          = 50 / 80 = 0.625 = 62.5%


*c) Recall vs. FPR:*

*📊 Recall (TPR):*
- Anteil der korrekt erkannter positiven Fälle
- TPR = TP / (TP + FN) = 50 / 60 = 83.3%

*⚠️ False Positive Rate (FPR):*
- Anteil der falsch erkannter positive unter negativen Fälle
- FPR = FP / (FP + TN) = 30 / 140 = 21.4%

---

## Task 3: Wahr oder Falsch?

### 1. Random Forest kann kategoriale Eingangsgrößen verarbeiten: *✅ WAHR*
- Splits basieren auf Kategorien, nicht auf numerischen Schwellenwerten

### 2. One-Hot-Codierung bei k-NN führt zu sinnvollen Abständen: *❌ FALSCH*
- One-Hot führt zu konstanten Abständen zwischen verschiedenen Kategorien
- Alle Kategorien haben gleiche euklidische Distanz (√2)

### 3. Höherer C-Parameter bei SVM erhöht Overfitting-Risiko: *✅ WAHR*
- C kontrolliert Trade-off zwischen Margin-Maximierung und Fehlerminimierung
- Höheres C → weniger Regularisierung → höheres Overfitting-Risiko

### 4. Kernel-Trick benötigt explizite Kenntnis der Abbildung: *❌ FALSCH*
- Kernel-Trick arbeitet nur mit Skalarprodukt im transformierten Raum
- Explizite Transformation ist nicht notwendig

### 5. ROC-AUC = 0.5 bedeutet besser als Raten: *❌ FALSCH*
- AUC = 0.5 entspricht zufälligem Raten
- Bessere Klassifikatoren haben AUC > 0.5

---

## Task 4: Linear Regression

Gegeben ist das Dataset:
| X | Y | 
|---|---|
| 2 | 3 |                 
| 4 | 7 |         
| 6 | 11 |              
| 8 | 15 |   


### a) Formulieren Sie die Strukturgleichung eines linearen Modells (𝑓(x) = ⋯ ):

f(x) = w₀ + w₁ · x


### b) Mit Startwerten 𝑤0 = 0, 𝑤1 = 1 führen Sie eine Gradient Descent-Iteration mit Lernrate 𝛼 = 0.01 durch. Aktualisieren Sie die Gewichte nach: <br>

![Gradient Descent-Iteration](https://github.com/user-attachments/assets/0f4927cb-9715-49fe-9ae6-2ee4eba9481e)


*Startwerte:* w₀ = 0, w₁ = 1, α = 0.01        

*Schritt 1: Vorhersagen berechnen*

f(2) = 0 + 1·2 = 2 <br>
f(4) = 0 + 1·4 = 4 <br> 
f(6) = 0 + 1·6 = 6 <br>
f(8) = 0 + 1·8 = 8 <br>


*Schritt 2: Fehler berechnen*

e₁ = f(2) - y₁ = 2 - 3 = -1 <br>
e₂ = f(4) - y₂ = 4 - 7 = -3 <br>
e₃ = f(6) - y₃ = 6 - 11 = -5 <br>
e₄ = f(8) - y₄ = 8 - 15 = -7 <br>


*Schritt 3: Gradienten berechnen*

∂J/∂w₀ = (1/4) · Σeᵢ = (1/4) · (-1-3-5-7) = -4 <br>
∂J/∂w₁ = (1/4) · Σ(eᵢ · xᵢ) = (1/4) · (-1·2 + -3·4 + -5·6 + -7·8) = -25


*Schritt 4: Parameter aktualisieren*

w₀ = 0 - 0.01 · (-4) = 0.04 <br>
w₁ = 1 - 0.01 · (-25) = 1.25


---

## Task 5: k-Nearest Neighbor
### 1. Im Onlineshop liegen folgende Daten (Sekunden auf Website 𝑡, Score 𝑠, Label {0,1}) vor:

### Daten:

| Sek. t  | Score s  | Label | 
|---------|--------------|-------------|
| 30      | 0.2          | 0           
| 45      | 0.5          | 1  
| 50      | 0.4          | 1    
| 20      | 0.3          | 0    
| 60      | 0.6          | 1    


*Ein neuer Nutzer kommt mit (𝑡 = 40, 𝑠 = 0.45).*

### a) Berechnen Sie die euklidischen Distanzen:

d₁ = √((40-30)² + (0.45-0.2)²) = √(100 + 0.0625) = 10.003 <br>
d₂ = √((40-45)² + (0.45-0.5)²) = √(25 + 0.0025) = 5.001 <br>
d₃ = √((40-50)² + (0.45-0.4)²) = √(100 + 0.0025) = 10.001 <br>
d₄ = √((40-20)² + (0.45-0.3)²) = √(400 + 0.0225) = 20.001 <br> 
d₅ = √((40-60)² + (0.45-0.6)²) = √(400 + 0.0225) = 20.001 <br>


### b) Klassifizieren Sie für 𝑘 = 1,3,5 (Mehrheitsentscheid):

*Sortierte Distanzen:*
1. d₂ = 5.001 → Label 1
2. d₃ = 10.001 → Label 1
3. d₁ = 10.003 → Label 0
4. d₄ = 20.001 → Label 0
5. d₅ = 20.001 → Label 1

*Ergebnisse:*
- *k=1:* Nächster Nachbar hat Label 1 → *Klassifikation: 1*
- *k=3:* 3 nächste Nachbarn: 1, 1, 0 → Mehrheit: 1 → *Klassifikation: 1*
- *k=5:* Alle Nachbarn: 1, 1, 0, 0, 1 → Mehrheit: 1 → *Klassifikation: 1*

### c) Nachbarschaften-Skizze:

![k-Nearest Neighbor](https://github.com/user-attachments/assets/ff5fe4b4-4efa-4cc9-8ba8-1fc1615b3d8c)


## Task 6: Unsupervised Learning - Clustering

### a) Erläutern Sie den k-Means-Algorithmus und seine Konvergenzbedingung:

*Schritte:*
1. *Initialisierung:* k Zentroide zufällig platzieren
2. *Assignment:* Jeden Datenpunkt dem nächsten Zentroid zuordnen
3. *Update:* Zentroide als Mittelwert der zugeordneten Punkte neu berechnen
4. *Wiederholung:* Schritte 2-3 bis zur Konvergenz

*Konvergenzbedingung:* Zentroide ändern sich nicht mehr (oder nur minimal)

### b) Nennen Sie zwei Nachteile von k-Means und schlagen Sie eine Alternative vor:

*🔴 Nachteile von k-Means:*
- Erfordert Vorgabe von k
- Empfindlich gegenüber Initialisierung
- Nur sphärische Cluster

*✅ Alternative: DBSCAN*
- Erkennt Cluster beliebiger Form
- Automatische Bestimmung der Clusteranzahl
- Robust gegenüber Ausreißern

### c) Diskutieren Sie, wie die Wahl der Distanzmetrik (z. B. Euclid vs. Manhattan) das Clustering-Ergebnis beeinflusst:

*📏 Euklidische Distanz:* Bevorzugt sphärische Cluster

*🔄 Manhattan-Distanz:* Weniger empfindlich gegenüber Ausreißern, bevorzugt achsenparallele Strukturen

*Wahl abhängig von:* Datencharakteristik und gewünschter Clusterform

---

## Task 7: Neuronale Netze

### a) Skizzieren Sie die Architektur eines einfachen CNN für die Bildklassifikation und beschriften Sie die Layer:


Input Image → Conv Layer → Pooling → Conv Layer → Pooling → Flatten → Dense Layer (Softmax)


*Komponenten:*
- *Conv Layer:* Merkmalsextraktion
- *Pooling:* Dimensionsreduktion
- *Dense Layer:* Vollvernetzte Schicht
- *Softmax:* Wahrscheinlichkeitsverteilung

### b) Berechnen Sie die Ausgabegröße eines 5×5-Bilds bei einem 2×3-Filter und Stride 2 (ohne Padding und mit Zero-Padding P=1):

*Input:* 5×5, Filter: 2×3, Stride: 2

*Formel:* Output_size = floor((Input_size - Filter_size + 2·Padding) / Stride) + 1

*Ohne Padding (P=0):*

Output_height = floor((5 - 2)/2) + 1 = floor(1.5) + 1 = 2
Output_width = floor((5 - 3)/2) + 1 = floor(1) + 1 = 2
→ Ausgabe: 2×2


*Mit Zero-Padding (P=1):*

Output_height = floor((5 + 2·1 - 2)/2) + 1 = floor(2.5) + 1 = 3
Output_width = floor((5 + 2·1 - 3)/2) + 1 = floor(2) + 1 = 3
→ Ausgabe: 3×3


### c) Erklären Sie kurz, warum Parameter Sharing in CNNs wichtig ist:

*🔄 Gewichtswiederverwendung:* Gleiche Filter werden auf gesamtes Bild angewendet

*✅ Vorteile:*
- Reduzierte Parameteranzahl
- Translationsinvarianz
- Bessere Generalisierung

*⚡ Effizienz:* Weniger Parameter zu trainieren, weniger Overfitting-Risiko

---

## Task 8: ML-Engineer-Praxis

*Projekt:* Gesundheitszustand von Pflanzen vorhersagen

### a) Welche Daten (Features, Label) erfassen Sie, und wie verarbeiten Sie sie vor?

*🌱 Features:*
- *Alter:* numerisch, in Tagen
- *Wasserzufuhr:* numerisch, ml/Tag
- *Blattfarbe:* kategorisch (grün, gelb, braun)

*🎯 Label:* Gesundheitszustand (kategorisch: gesund, krank, kritisch)

*⚙️ Vorverarbeitung:*
- Normalisierung numerischer Features
- One-Hot-Encoding für Blattfarbe
- Ausreißer-Behandlung bei Wasserzufuhr
- Fehlende Werte durch Median ersetzen

### b) Welches Modell setzen Sie ein, und mit welchen Metriken evaluieren Sie es?

*🌳 Modell: Random Forest Classifier*
- Kann mit gemischten Datentypen umgehen
- Robust gegenüber Ausreißern
- Liefert Feature Importance

*📊 Metriken:*
- *Accuracy:* Gesamtperformance
- *Precision/Recall:* für jede Klasse
- *F1-Score:* für unbalancierte Klassen
- *Confusion Matrix:* detaillierte Analyse

### c) Skizzieren Sie den ML-Workflow:

1. Datensammlung
      
2. Explorative Datenanalyse
      
3. Datenvorbereitung
      
4. Train/Validation/Test Split
      
5. Modelltraining
      
6. Hyperparameter-Tuning (Grid Search)
      
7. Modell-Evaluierung
      
8. Deployment
      
9. Monitoring


### d) Diskutieren Sie Quellen möglicher Unsicherheiten in den Vorhersagen und geeignete Ansätze, um darauf zu reagieren:

*🔴 Unsicherheitsquellen:*
- Messfehler bei Wasserzufuhr
- Subjektive Blattfarb-Bewertung
- Saisonale Effekte
- Unvollständige Daten

*✅ Lösungsansätze:*
- *Datenqualität:* Mehrfachmessungen, standardisierte Protokolle
- *Modell-Ensemble:* Kombination mehrerer Modelle
- *Konfidenzintervalle:* Unsicherheitsschätzung der Vorhersagen
- *Kontinuierliches Lernen:* Regelmäßiges Nachtraining mit neuen Daten
- *Feature Engineering:* Zusätzliche relevante Features sammeln

---

## 🎯 Wichtige Formeln zum Merken:

### Classification Metrics:

- Accuracy = (TP + TN) / (TP + TN + FP + FN)
- Precision = TP / (TP + FP)
- Recall(TPR) = TP / (TP + FN) 
- FPR = FP / (FP + TN)


### CNN Output Size:

- Output_size = floor((Input_size - Filter_size + 2·Padding) / Stride) + 1


### Gradient Descent:

- w_new = w_old - α · ∇J(w)


### k-NN Distance:

- Euclidean: d = √((x₁-x₂)² + (y₁-y₂)²)
- Manhattan: d = |x₁-x₂| + |y₁-y₂|

