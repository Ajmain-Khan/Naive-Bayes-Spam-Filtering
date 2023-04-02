# Naive-Bayes-Spam-Filtering
A Java implementation of the naive bayes classifier algorithm in an application to detect and filter spam and stop words.

## Interface Features
- A visual representation of the accuracy and precision
- Shows distribution of ham(H) files and spam(S) files in training and testing phase
---
#### Demo
![Preview](./demo/NaiveBayesSpamDetection.png?raw=true)

# Model features

### Naive Bayes spam filtering
#### First computation:

![Equation](https://latex.codecogs.com/svg.latex?Pr(W_i|S)=\frac{Pr(W_i|S)}{Pr(S|W_i)&space;&plus;&space;Pr(W_i|H)})

#### Second Computation:

![Equation](https://latex.codecogs.com/svg.latex?\eta&space;=&space;\sum_{i&space;=&space;1}^{N}[\ln&space;(1-Pr(S|W_i))-ln(Pr(S|W_i))])

![Equation](https://latex.codecogs.com/svg.latex?Pr(S|F)&space;=&space;\frac{1}{1&plus;e^\eta})

#### Third Computation (Improved detection):

![Equation](https://latex.codecogs.com/svg.latex?Pr%27(S|W_i)=&space;\frac{s&space;\cdot&space;Pr(S)&space;&plus;&space;n&space;\cdot&space;Pr(S|W_i)}{s&plus;n})

Where <img src="https://render.githubusercontent.com/render/math?math=Pr(S) = 0.5">, ![Equation](https://latex.codecogs.com/svg.latex?s&space;=&space;4) and ![Equation](https://latex.codecogs.com/svg.latex?n&space;=) number of files that have ![Equation](https://latex.codecogs.com/svg.latex?W_i)

The third computation deals with rare words by putting more confidence in the spam probability than the default probability, if the word occurs more than 4 times in the training phase
#### Stop words (Improved detection):
Does not evaluate stop words specified in `stopwords.txt`.

Stop words like "a", "the", or "is" provide little to no context to if the file is a spam. Therefore, it is optimal to not evaluate such words

# Build Instructions for IntelliJ
#### *Prerequisites: JDK 15+, JAVAFX 15+*

#### 1. Clone the repository
     git clone https://github.com/Ajmain-Khan/Naive-Bayes-Spam-Filtering

#### 2. In Intellij, navigate to (`File -> Project Structure`)
i. Navigate to `Project` and add the Java 15 SDK

ii. Navigate to `Global Libraries` and add JavaFX 15 to modules

#### 3. Edit run configurations
i. Add an application template, modify it to direct to `src.main`

ii. Add VM options `--module-path "path-to-lib" --add-modules javafx.controls,javafx.fxml`
