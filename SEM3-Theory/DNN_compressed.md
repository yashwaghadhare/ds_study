# DNN (Deep Neural Networks): Complete Compressed Notes (Units I to IV)

> Exam-revision notes. Every question from the question bank is covered, merged by theme, with **no formulas**.
> Q numbers in brackets (e.g., Q5) match the question bank of that unit.
> Each unit ends with a **Last-Minute Cheat Sheet**. The file ends with **Fill-in-the-Blanks and MCQ answers**.

## Contents
1. [Unit I: Neural Network Learning, Regularization and Evaluation](#unit-i)
2. [Unit II: CNN (Convolutional Neural Networks)](#unit-ii)
3. [Unit III: RNN, BPTT, LSTM and GRU](#unit-iii)
4. [Unit IV: GAN, Transformers, BERT and Deep Reinforcement Learning](#unit-iv)
5. [Fill-in-the-Blanks and MCQs (quick answers)](#quick-answers)

---

<a id="unit-i"></a>
# UNIT I: How a Network Learns, Overfitting and Evaluation

## BLOCK A: How a Neural Network Learns
*(Q1, Q5, Q11, Q8, Q14, Q12)*

### Q1. Forward Propagation
**Meaning:** Input moves forward through the layers (input → hidden → output) to produce a prediction.

**Steps:**
1. Take the input features.
2. Multiply each input by its weight, add them up, and add a bias.
3. Pass the result through an activation function (adds non-linearity).
4. The output becomes the input of the next layer, and steps 2-3 repeat.
5. The final layer gives the prediction.

- It is the first half of training; backpropagation is the second half.
- *Example:* predicting house price from size and location.

### Q5. Backpropagation
**Meaning:** The error is sent backward (output → input) to update the weights, so the network learns from its mistakes.

**Steps:**
1. Forward pass gives a prediction.
2. A loss function compares the prediction with the correct answer to give the error.
3. The error is sent backward through the layers.
4. Using the chain rule, the network finds how much each weight contributed to the error (the gradient).
5. Each weight is adjusted slightly in the direction that reduces the error (size of adjustment depends on the learning rate and the gradient).
6. Repeat over many examples until the error is small.

- Gradient = the direction in which a weight should change to reduce the error.
- *Example:* a cat image predicted as a dog → the weights responsible are corrected.

### Q11. Gradient Descent
**Meaning:** An optimization method that moves the weights "downhill" step by step to reduce the error. (Think of a person walking down a foggy hill.)

**Steps:** start with random weights → measure the error → find the slope (gradient) → move each weight opposite to the slope → repeat until the error is minimum.

**Learning rate** (the step size):
- Too large: it overshoots the minimum.
- Too small: it learns very slowly.

| Type | Uses |
|---|---|
| Batch | All data in each step |
| Stochastic (SGD) | One example per step |
| Mini-batch | Small groups (**most common**) |

### Q8 + Q14. Adam and RMSProp

| | **RMSProp** (Q14) | **Adam** (Q8) |
|---|---|---|
| Full form | Root Mean Square Propagation | Adaptive Moment Estimation |
| Main idea | Gives each weight its own **adaptive learning rate** | Combines **Momentum + RMSProp** |
| Why needed | Plain gradient descent uses one learning rate for all weights (too big for some, too small for others) | Fast, smooth, needs little tuning |
| Working | Tracks a moving average of recent squared gradients. Weights with large gradients take smaller steps; weights with small gradients take larger steps | Keeps a moving average of gradients (momentum) and of squared gradients (step scaling). Applies bias correction so early training is accurate, then updates each weight |
| Best for | Uneven error surfaces, RNNs | Most deep networks (most widely used) |

- **Momentum** = remembers the direction of past gradients, like a rolling ball gaining speed.
- RMSProp is a key idea inside Adam.
- *Example:* image classifier. Adam trains faster and smoother than plain gradient descent.

### Q12. Activation Functions
**Meaning:** A function applied to a neuron's output that decides whether and how strongly it "fires".

**Role:**
- **Adds non-linearity.** Without it, the whole network behaves like one simple linear equation.
- Makes stacking many layers meaningful (enables deep learning).
- Controls signal strength by squashing values into a useful range.

| Function | Output | Use |
|---|---|---|
| **Sigmoid** | Between 0 and 1 | Probabilities (yes/no output) |
| **ReLU** | Passes positive values, turns negatives into 0 | Hidden layers (fast, popular) |
| **Tanh** | Between -1 and 1, centred around zero | Hidden layers |
| **Softmax** | Probabilities of all classes that add up to 1 | Multiclass output layer |

- *Example:* ReLU in hidden layers, Softmax at the output (cat / dog / bird).

---

## BLOCK B: Overfitting and How to Fix It
*(Q2, Q3, Q6, Q9, Q10, Q13, Q15)*

### Q2. Overfitting vs Underfitting

| | **Overfitting** | **Underfitting** |
|---|---|---|
| Meaning | Learns training data too well, including noise | Too simple, fails to learn even basic patterns |
| Cause | Model too **complex** | Model too **simple** |
| Training accuracy | **High** | **Low** |
| Test accuracy | Low | Low |
| Analogy | Student who memorises answers | Student who didn't study |
| Fix | More data, regularization, dropout, simpler model | More complex model, more features, more training |

- *Example:* overfit = 99% on training but 55% on new data. Underfit = 60% on both.
- **Goal:** a balanced model that generalizes well.

### Remedies against overfitting

**Q3. Dropout**
- Randomly **switches off neurons** (e.g., half of them) in each training step.
- The network cannot depend on any single neuron. This acts like training many small networks and combining them.
- At **testing time, all neurons are used.**
- Too much dropout leads to underfitting.
- *Example:* 98% train / 70% test → with dropout, test rises to 88%.

**Q6. Regularization (L1 and L2)**
- Adds a **penalty to the loss function** that grows when weights become large. This keeps the model simple and prevents overfitting.

| | **L1 (Lasso)** | **L2 (Ridge)** |
|---|---|---|
| Penalty based on | Absolute values of weights | Squares of weights |
| Effect | Pushes some weights **exactly to zero** | Shrinks weights **close to zero, rarely exactly zero** |
| Result | Sparse model, **removes features** (feature selection) | Keeps all features but small |

**Q9. Early Stopping**
- Stop training at the right moment, before the model starts memorising.
- At first, both training and validation performance improve. After a point, training accuracy keeps rising but **validation accuracy starts falling** (overfitting).
- **Steps:** keep a validation set → check validation error every epoch → note the best point → stop if no improvement for several epochs → **save the best model's weights**.
- Benefits: prevents overfitting, saves time, improves generalization.

**Q10. Data Augmentation**
- Creates **new, slightly changed versions** of existing data. The **label stays the same** (a rotated cat is still a cat).
- Image techniques: rotation, flipping, zoom/crop, shifting, brightness/colour change, adding noise.
- Benefits: more data, less overfitting, better generalization, saves cost of collecting real data.
- *Example:* 1,000 cat photos become thousands of varied images.

**Q13. Cross-Validation**
- Tests the model on **several different splits** of the data and averages the results. This is more reliable than a single lucky or unlucky split.

| Technique | How it works |
|---|---|
| **K-Fold** | Split data into K parts. Train on K minus 1 parts, test on the remaining one. Repeat K times so every part is tested once, then average |
| **Stratified K-Fold** | Same as K-Fold, but every fold keeps the **same class balance** (good for unbalanced data) |
| **Leave-One-Out (LOOCV)** | Each single example is the test set once; very thorough but **slow** |
| **Holdout** | Data split once into train and test (simplest) |

- *Example:* 1,000 records with 5-fold → train on 4 parts, test on 1, repeat 5 times.

**Q15. Feature Selection**
- Choose only the **useful input features** (columns) and drop the irrelevant ones.
- Why: weak features add noise, slow training, and cause overfitting.

| Method | How it works |
|---|---|
| **Filter** | Rank features using statistics (like correlation) and keep the top ones |
| **Wrapper** | Try different feature subsets and pick the one giving the best model performance |
| **Embedded** | Selection happens during training (e.g., L1 sets weak feature weights to zero) |

- Role: better accuracy, less overfitting, faster training, simpler model.
- *Example:* loan approval. Keep income and credit score, drop "favourite colour".

---

## BLOCK C: Evaluating a Model
*(Q16, Q4, Q7)*

### Q16 + Q4. Confusion Matrix and Classification Metrics
A confusion matrix is a table (2 by 2 for two classes) that compares predictions with the actual answers.

| Term | Meaning | Note |
|---|---|---|
| **True Positive (TP)** | Predicted positive, really positive | Correct |
| **True Negative (TN)** | Predicted negative, really negative | Correct |
| **False Positive (FP)** | Predicted positive, actually negative | False alarm (**Type I error**) |
| **False Negative (FN)** | Predicted negative, actually positive | A miss (**Type II error**), often the most dangerous |

**Metrics (in words):**
- **Accuracy:** how many predictions were correct out of all predictions. Can mislead on unbalanced data.
- **Precision:** of all items predicted positive, how many were truly positive. High precision = few false alarms.
- **Recall:** of all actual positive items, how many the model found. High recall = few missed cases.
- **F1-Score:** the balance of precision and recall in one number. High only when both are high.

- *Example (COVID test):* 90 sick correctly detected, 850 healthy correctly cleared, 10 healthy wrongly flagged, 50 sick wrongly cleared. The 50 missed cases are worrying.
- For disease detection, **recall** matters most.

### Q7. Regression Metrics
Regression predicts **continuous values** (like prices).

| Metric | In words | Key point |
|---|---|---|
| **MAE** (Mean Absolute Error) | Average of the absolute differences between predicted and actual values | Simple, treats all errors equally |
| **MSE** (Mean Squared Error) | Average of the squared differences | Punishes **large errors** heavily, but unit is squared |
| **RMSE** (Root Mean Squared Error) | Square root of MSE | Brings error back to the **original unit**, easy to read |
| **R-squared** | How much of the variation in the data the model explains | 0 to 1, higher is better (0.9 = 90% explained) |

- MAE, MSE and RMSE are **error amounts** (lower is better). R-squared is a **fit percentage** (higher is better).
- *Example:* average error ₹2 lakh (MAE), RMSE ₹3 lakh, R-squared 0.85.

---

## Unit I: Last-Minute Cheat Sheet
- **Learning loop:** Forward prop → Loss → Backprop (chain rule gives gradients) → Optimizer updates weights (Gradient Descent → RMSProp → Adam).
- **Adam = Momentum + RMSProp. RMSProp = adaptive learning rate using squared gradients.**
- **Non-linearity comes from activation functions:** Sigmoid (0 to 1), Tanh (-1 to 1), ReLU (zeroes negatives), Softmax (probabilities add to 1).
- **Overfit** = high training, low test. **Underfit** = low on both.
- **Remedies:** Dropout, L1/L2, Early Stopping, Data Augmentation, Cross-Validation, Feature Selection, more data.
- **L1 → zero weights (feature selection). L2 → small weights.**
- **Dropout:** off during testing. **Early stopping:** keep the best weights.
- **FP = Type I, FN = Type II.** Precision is affected by FP; Recall by FN.
- **MSE punishes big errors. RMSE has original unit. R-squared is fit percentage.**

---

<a id="unit-ii"></a>
# UNIT II: CNN (Convolutional Neural Networks)

## BLOCK A: Image Basics
*(Q1)*

### Q1. How a computer represents an image
- A digital image is made of tiny squares called **pixels**, arranged in a **grid of rows and columns**.
- Each pixel is stored as a **number**, so the whole image becomes a **matrix** (a grid of numbers). Computers only understand numbers, and CNNs work directly on these pixel numbers.

| Type | Numbers per pixel | Structure |
|---|---|---|
| **Grayscale** | 1 number, from 0 (black) to 255 (white) | One 2D matrix |
| **Colour (RGB)** | 3 numbers (Red, Green, Blue), each 0 to 255 | Three stacked matrices (3 channels) |

- *Example:* a small 3×3 grayscale corner image is a matrix of 0s (black) and 255s (white).

---

## BLOCK B: Building Blocks (Layers) of a CNN
*(Q2, Q6, Q9, Q14, Q3, Q7, Q15, Q10, Q11)*

### Q2 + Q6. Convolution layer, filter and feature map
- **Convolution layer** = the main building block of a CNN. It detects features such as edges, corners and shapes.
- **Filter (kernel)** = a small matrix (e.g., 3×3) that detects one specific pattern (e.g., a vertical edge).
- **Feature map** = the output after the filter slides over the image. It shows where the feature was found.

**How it works:**
1. Place the filter on the top-left corner of the image.
2. Multiply each filter number by the pixel under it and add everything into one number.
3. Put that number in the feature map.
4. Slide the filter to the next position and repeat.
5. After covering the whole image, the feature map is complete.

- Where the image matches the filter's pattern, the value is **high**, so the feature map "lights up" there.
- The same filter is reused across the whole image (**filter sharing**), which saves parameters.

**Role of filters (Q6):**
- Different filters detect different patterns: **edge filters**, **vertical/horizontal line filters**, **corner filters**, **texture filters**, and **complex filters** in deeper layers (shapes, parts, whole objects).
- Filters are **not hand-made**. The network **learns** the best filter values during training.
- Early-layer filters learn simple patterns; deeper filters learn complex ones.
- *Example:* on a zebra photo, one filter detects vertical edges (stripes), another detects curves (body outline), and deeper filters combine them into the zebra shape.

### Q9. Stride and Padding

| | **Stride** | **Padding** |
|---|---|---|
| Meaning | Number of pixels the filter moves at each slide | Adding a border of extra pixels (usually zeros) around the image |
| Effect | Stride 1 = larger, more detailed output. Stride 2 = smaller, faster output but may miss fine detail | Keeps the output size and protects **edge information** |
| Without it | - | Output shrinks and edge information is lost |

- **Valid padding** = no padding (output is smaller). **Same padding** = zeros added so output size matches input.
- Together they control the **output feature-map size**. Stride balances speed and detail; padding preserves edges.
- *Example:* a 3×3 filter on a 5×5 image, stride 1, no padding → 3×3 output. With same padding the output stays 5×5.

### Q14. ReLU after convolution
- ReLU keeps **positive values** and turns **negative values into 0**.
- **Why after convolution:** convolution is a linear calculation (multiply and add), and stacking only linear steps cannot learn complex patterns. ReLU adds **non-linearity**.
- Roles: adds non-linearity; removes negative values (keeps strong activations); fast and simple; avoids the vanishing gradient problem (doesn't squash large values like sigmoid).
- *Example:* a feature map with -3, 5, -1, 8 becomes 0, 5, 0, 8.

### Q3 + Q7 + Q15. Pooling (Max vs Average, importance, working)
**Meaning:** Pooling shrinks a feature map by summarising each small region into a single value.

**Working (Q15):**
1. Choose a window size (usually 2×2).
2. Choose a stride (often 2, so windows don't overlap).
3. Slide the window across the feature map.
4. Keep one value per window (maximum or average).
5. The values form a new, smaller map (e.g., 4×4 becomes 2×2).

| | **Max Pooling** | **Average Pooling** |
|---|---|---|
| Keeps | The **largest** value in the window | The **average** of the window |
| Effect | Highlights the strongest, sharpest features | Smoother, gentler summary |
| Use | More common (good for sharp edges) | Softer, blended output |
| Example (window 1, 3, 2, 4) | 4 | 2.5 |

**Importance (Q7), 3 main benefits:**
1. **Reduces computation:** smaller maps = faster and lighter.
2. **Reduces overfitting:** less detail means less chance of memorising noise.
3. **Reduces sensitivity to small position shifts (translation invariance):** if a feature moves slightly, pooling still captures it.

- Pooling keeps the "gist" of each region and throws away tiny details.
- *Example:* a cat's ear a few pixels to the left is still caught by max pooling.

### Q10. Flatten layer
- Converts the 2D/3D feature maps into a **single long 1D vector**.
- **Why needed:** fully connected layers accept only a 1D vector. Flatten is the **bridge** between feature extraction (convolution + pooling) and decision making (fully connected).
- It keeps all values and only changes their **arrangement**.
- *Example:* a 2×2×2 feature map (8 numbers) is unrolled into one list of 8 numbers.

### Q11. Fully Connected (FC / dense) layer
- Every neuron is connected to **every neuron** in the previous layer. FC layers come at the **end** of a CNN.
- Job: **combine all extracted features** and make the final decision.

**Working:**
1. Take the flattened vector.
2. Multiply each feature by a learned weight and add them up (important features get more influence).
3. Apply an activation function.
4. The final FC layer gives a score for each class.
5. **Softmax** turns scores into probabilities; the highest is chosen.

- It learns which feature combinations indicate which class (whiskers + pointy ears + fur → cat).

---

## BLOCK C: Activation Functions in CNNs
*(Q4)*

| Function | What it does | Where used in a CNN | Note |
|---|---|---|---|
| **ReLU** | Keeps positives, turns negatives into 0 | **Hidden / convolution layers** | Fast, simple, avoids vanishing gradient |
| **Sigmoid** | Squashes any value between 0 and 1 | **Output layer, two-class problems** | Can suffer vanishing gradients in deep layers |
| **Softmax** | Turns scores into probabilities adding up to 1 | **Output layer, many-class problems** | Highest probability is chosen |

- *Example:* cat vs dog → Sigmoid at output. Cat vs dog vs bird → Softmax at output. ReLU in convolution layers in both.

---

## BLOCK D: CNN as a Whole
*(Q5, Q13, Q16)*

### Q5. What is a CNN and why is it good at images
- **CNN = Convolutional Neural Network**, a special neural network for images. It detects features (edges, shapes, objects) **automatically**, with no manual feature design.
- Ordinary networks treat every pixel separately and need far too many connections. CNNs use small **filters that slide and are shared** across the image, so they are efficient and spot patterns **anywhere** (position-invariant).

### Q13. Architecture and data flow (write in this order)
1. **Input layer:** image as a pixel matrix (3 channels for colour).
2. **Convolution layer:** filters detect features → feature maps.
3. **ReLU:** adds non-linearity.
4. **Pooling layer:** shrinks the maps, keeps key features.
5. **Repeat convolution + pooling:** simple features first, complex features deeper.
6. **Flatten layer:** unrolls maps into a 1D vector.
7. **Fully connected layers:** combine features to make a decision.
8. **Output layer (Softmax):** class probabilities, highest chosen.

**Flow:** raw pixels → features → smaller features → combined features → final class.

### Q16 (+ Q5). Hierarchical feature extraction
"Hierarchical" = arranged in levels, from simple to complex (like building with blocks).

| Layer depth | What it detects |
|---|---|
| **Early layers** | Simple features: edges, lines, corners |
| **Middle layers** | Shapes, curves, textures (eyes, wheels) |
| **Deeper layers** | Object parts (nose, car door) |
| **Final layers** | Complete objects (full face, full car) |

- Each layer builds on the one before it; more layers allow more levels of combination.
- *Example:* recognising a car: edges → circles and rectangles → doors and wheels → the complete car.

---

## BLOCK E: Applications and Famous Architectures
*(Q8, Q12)*

### Q8. Image Classification vs Face Recognition vs Object Detection

| Task | Question it answers | Output | Example |
|---|---|---|---|
| **Image classification** | "What is this image?" | One label for the whole image | Photo labelled "cat" |
| **Face recognition** | "Whose face is this?" | A specific person's identity | Phone unlock by owner's face |
| **Object detection** | "What objects are here, and where?" | Labels plus **locations (bounding boxes)** | Self-driving car spotting cars, people, signs |

### Q12. AlexNet, VGGNet, GoogLeNet, ResNet

| Network | Year | Key contribution |
|---|---|---|
| **AlexNet** | 2012 | Won ImageNet by a large margin; started the deep-learning boom. Used **ReLU** (faster training), **Dropout** (less overfitting) and **GPUs** |
| **VGGNet** | 2014 | **Many small 3×3 filters stacked deeply** work very well. Simple, uniform design, 16-19 layers. Proved **depth improves performance** |
| **GoogLeNet (Inception)** | 2014 | **Inception module**: applies filters of several sizes at the same time, capturing **multi-scale** features efficiently with fewer parameters |
| **ResNet** | 2015 | **Skip (residual) connections** let information skip layers. They solve the **vanishing gradient** problem and allow **100+ layers** |

- *Memory trick:* **A**lexNet = ReLU + Dropout + GPU. **V**GG = small filters, deep. **G**oogLeNet = Inception. **R**esNet = skip connections.

---

## Unit II: Last-Minute Cheat Sheet
- **Image = grid of pixel numbers.** Grayscale = 1 channel (0-255). RGB = 3 channels.
- **Filter** detects a pattern. **Feature map** is the output. Filters are **learned** and **shared**.
- **CNN order:** Input → Convolution → ReLU → Pooling (repeat) → Flatten → Fully Connected → Softmax.
- **Stride** = step size (bigger = smaller output). **Padding** = border of zeros (keeps size and edges).
- **ReLU** after convolution. **Sigmoid** for 2 classes. **Softmax** for many classes.
- **Max pooling** = strongest value. **Average pooling** = mean.
- **Pooling's 3 benefits:** less computation, less overfitting, tolerance to small shifts.
- **Flatten** = bridge from 2D/3D to 1D. **FC layer** = combines features and decides.
- **Hierarchy:** edges → shapes → parts → objects.
- **Classification** = one label. **Recognition** = who. **Detection** = what and where (boxes).
- **AlexNet** (ReLU, Dropout, GPU), **VGG** (small deep filters), **GoogLeNet** (Inception), **ResNet** (skip connections).

---

<a id="unit-iii"></a>
# UNIT III: RNN, BPTT, LSTM and GRU

## BLOCK A: Sequence Data and Why Feedforward Networks Fail
*(Q1, Q5)*

### Q1. Sequence data and why order matters
- **Sequence data** = data whose elements come in a **specific order**, and the order carries meaning. Examples: sentences (words), time-series (stock prices), music (notes), DNA (bases).
- **Why order matters:**
  - Order carries meaning: "Dog bites man" and "Man bites dog" use the same words but mean opposite things.
  - Context depends on order: each element is understood in relation to those before and after it.
  - Prediction needs order: to predict the next element, the model must know what came before.
  - Shuffling time-series data (e.g., stock prices) destroys the trend.
- *Example:* "I am going to the ..." → a place word like "market" is likely. Shuffled ("the to going am I") the meaning is lost.

### Q5. Limitations of feedforward networks for sequence data
A **feedforward network** sends data in one direction (input → output) with **no memory**; each input is treated independently.

**Limitations:**
1. **No memory:** forgets earlier inputs, so context is lost.
2. **Ignores order:** treats inputs independently.
3. **Fixed input size:** but sentences have different lengths.
4. **No sharing across positions:** doesn't reuse learning across time steps (RNNs do).
5. **Cannot handle dependencies:** cannot link a word at the start to one at the end.

- **Impact:** poor on language, speech and time-series; cannot predict the next element from context.
- **Solution:** RNNs add a **hidden state (memory)**, handle variable-length sequences and share weights.
- *Example:* "The sky is ..." → a feedforward network can't use earlier words to predict "blue"; an RNN can.

---

## BLOCK B: RNN Basics
*(Q2, Q13, Q10, Q6, Q9)*

### Q2 + Q13. RNN equations and the hidden state
- **RNN = Recurrent Neural Network**, built for sequence data. Its special feature is the **hidden state**: a set of numbers acting as **memory**, carrying information from previous steps to the current step.

**The two basic equations (explained in words):**
1. **Hidden state update:** the new hidden state is found by combining the **current input** and the **previous hidden state** (each with its own weights), adding a bias, and passing the result through an activation function (usually **tanh**). In simple words: "what I see now + what I remember".
2. **Output:** the output is produced from the **current hidden state** using an output weight, a bias, and an activation (e.g., **Softmax**).

- The **same weights are used at every step** (shared weights).

**How the hidden state stores previous information (Q13):**
1. **Start:** the hidden state begins with an initial value (usually zeros).
2. **At each step:** combine the current input with the previous hidden state to produce a new hidden state.
3. **Carry forward:** the new hidden state holds a blend of the current input and everything remembered before.
4. **Pass on:** it goes to the next step, so memory flows through the whole sequence.

- It is updated at every step, keeps a compressed record of all previous inputs, and lets the RNN use past context to predict the future.
- **Limitation:** over very long sequences, basic RNNs forget distant information (vanishing gradient); LSTM/GRU fix this.
- *Example:* "I am very happy today": after "I am very" the hidden state remembers a positive build-up, so "happy" is understood in context.

### Q10. Unrolling an RNN through time
- **Unrolling (unfolding)** = drawing the RNN's loop as a **chain of copies, one per time step**.
- **Why:** the loop is hard to visualise and train; unrolling shows how the same cell processes each element in order and how memory flows. It is essential for understanding **BPTT**.

**Steps:**
1. Input 1 + initial hidden state → hidden state 1 and output 1.
2. Input 2 + hidden state 1 → hidden state 2 and output 2.
3. Input 3 + hidden state 2 → hidden state 3 and output 3, and so on.

- **Key points:** the **same weights** in every copy (shared weights); the hidden state carries memory forward.
- *Example:* "I love NLP" → 3 copies: "I" (h1), "love" using h1 (h2), "NLP" using h2 (h3).

### Q6. Role of shared weights in an RNN
- **Shared weights** = the **same set of weights and biases** is used at every time step. Only the inputs and hidden state change.

**Benefits:**
- **Fewer parameters:** smaller network, faster training.
- **Handles any sequence length.**
- **Consistency across positions:** a pattern learned at one position is recognised at any other position.
- **Better generalization.**

- **In training (BPTT):** gradients from all time steps are **added together** to update the single shared weight set.
- *Example:* the same weights read the 1st, 5th and 20th word, so if "not" is learned as important, it is recognised wherever it appears.

### Q9. Four RNN input-output architectures

| Type | Input → Output | Example |
|---|---|---|
| **One-to-One** | 1 input → 1 output (no real sequence, like a standard network) | Single image classified into one label |
| **One-to-Many** | 1 input → sequence of outputs | **Image captioning** (image → sentence) |
| **Many-to-One** | Sequence of inputs → 1 output | **Sentiment analysis** (sentence → positive/negative) |
| **Many-to-Many** | Sequence → sequence (equal length, or different length using encoder-decoder) | **Machine translation** |

---

## BLOCK C: Training RNNs (BPTT) and Its Problems
*(Q3, Q14, Q7, Q8, Q11)*

### Q3 + Q14. BPTT: four steps and purpose
- **BPTT = Backpropagation Through Time.** It is the method used to train an RNN. Because the RNN works step by step and shares weights, normal backpropagation is extended **across all time steps**.

**The four steps (Q3):**
1. **Forward pass through time:** process the whole sequence step by step, computing and storing hidden states and outputs.
2. **Calculate the loss:** compare outputs with correct answers; total error across all time steps.
3. **Backward pass through time:** send the error from the **last step back to the first**, computing gradients at every step (chain rule).
4. **Update the weights:** **add up** the gradients from all time steps (weights are shared) and update the shared weights with an optimizer like gradient descent.

**Purpose (Q14):**
- Work out how each weight contributed to the error **at every time step**.
- Update the **shared weights** correctly by combining error signals from all steps.
- Let the RNN learn **time dependencies** (how earlier inputs affect later outputs).
- Reduce the loss, making predictions more accurate.

- **Assessment:** *Strength:* correctly trains RNNs. *Weakness:* slow and memory-heavy on long sequences; can cause vanishing or exploding gradients. *Solutions:* Truncated BPTT, LSTM/GRU.
- *Example:* predicting the next word: forward over all words → total error → backward through every word → update shared weights.

### Q7. Full BPTT vs Truncated BPTT

| | **Full BPTT** | **Truncated BPTT** |
|---|---|---|
| Backward range | Through the **entire sequence** | Only a **fixed short window (chunk)** |
| Speed | Slow | **Fast** |
| Memory | Heavy | **Light** |
| Long dependencies | Captured fully | May miss the longest ones |
| Use | Short sequences | **Long sequences** |

- *Example:* training on a long document: Full BPTT goes back through thousands of words (impractical); Truncated BPTT processes ~20 words at a time.

### Q8 + Q11. Vanishing vs Exploding Gradient

| | **Vanishing Gradient (Q8)** | **Exploding Gradient (Q11)** |
|---|---|---|
| Meaning | Gradients become **extremely small** (near zero) going backward | Gradients become **extremely large** going backward |
| Why it happens | During BPTT, gradients are multiplied again and again; values **less than 1** shrink rapidly toward zero | Same repeated multiplication; values **greater than 1** grow rapidly |
| Effects | Early inputs are forgotten; **cannot learn long-term dependencies**; slow, ineffective training | **Unstable training**; huge weights (overflow, NaN values); poor learning, no convergence |
| Solutions | **LSTM and GRU** (gates), ReLU activation, better initialization | **Gradient clipping** (most common: limit the gradient to a maximum), **smaller learning rate**, better initialization, LSTM/GRU |

- *Vanishing example:* "I grew up in France ... [many words] ... so I speak fluent ___": the signal from "France" fades, so a basic RNN forgets it; an LSTM solves it.
- *Exploding example:* loss suddenly jumps to infinity (NaN); gradient clipping makes training stable again.

---

## BLOCK D: LSTM and GRU
*(Q4, Q12, Q15)*

### Q4. LSTM: three gates and their roles
- **LSTM = Long Short-Term Memory.** A special RNN that remembers information over **long sequences**, solving the vanishing gradient problem. It uses a **memory cell** and **three gates**.
- **Gates** use the **sigmoid** function, giving values from **0 (block completely) to 1 (allow fully)**.

| Gate | Role |
|---|---|
| **1. Forget gate** | Decides which **old information** in the memory should be **thrown away** (0 = forget, 1 = keep) |
| **2. Input gate** | Decides which **new information** should be **added** to the memory |
| **3. Output gate** | Decides what part of the memory is **given as output** at the current step and passed to the next step |

- **Together:** forget gate clears unneeded old memory, input gate stores important new memory, output gate decides what to reveal.
- *Example:* "I grew up in France ... so I speak fluent French": the input gate stores "France", the output gate later uses it to predict "French".

### Q12. GRU: reset gate vs update gate
- **GRU = Gated Recurrent Unit.** A simplified RNN (like LSTM) with only **two gates**.

| | **Reset Gate** | **Update Gate** |
|---|---|---|
| Decides | How much of the **past (previous hidden state) to forget** when forming the new candidate memory | How much **old memory to keep versus new information to add** in the final hidden state |
| Near 0 | Ignores the past, focuses on current input | Mostly new information is used |
| Near 1 | Past is used fully | Most old memory is kept |
| Focus | The **candidate content** (short-term relevance) | The **final blend** (long-term retention) |

- *Example:* reading a long review: reset gate drops irrelevant earlier words; update gate keeps the key sentiment word "excellent" until the end.

### Q15. LSTM vs GRU

| Feature | **LSTM** | **GRU** |
|---|---|---|
| Gates | **Three** (forget, input, output) | **Two** (reset, update) |
| Memory cell | **Separate cell state** | **None** (memory merged into hidden state) |
| Complexity | More complex, more parameters | **Simpler**, fewer parameters |
| Speed | Slower | **Faster to train** |
| Data | Better on large, complex data and very long sequences | Works well on smaller data |
| Performance | Both strong, often similar | Both strong, often similar |

- **Use GRU** for speed and small data. **Use LSTM** for very long sequences and complex tasks.
- *Example:* quick sentiment model on small data → GRU. Complex translation on huge data → LSTM.

---

## Unit III: Last-Minute Cheat Sheet
- **Sequence data = order matters** ("Dog bites man" ≠ "Man bites dog"). Feedforward nets have **no memory** → use RNN.
- **RNN:** hidden state = memory. New hidden state = current input + previous hidden state. **Weights shared** across all steps.
- **Unrolling** = RNN loop drawn as a chain, one copy per time step.
- **4 architectures:** One-to-One, One-to-Many (captioning), Many-to-One (sentiment), Many-to-Many (translation).
- **BPTT 4 steps:** forward pass → loss → backward pass through time → update (add gradients, update shared weights).
- **Full BPTT** = whole sequence (slow, heavy). **Truncated BPTT** = short chunks (fast, light, may miss long dependencies).
- **Vanishing gradient** (tiny, forgets early inputs) → fix with **LSTM/GRU**. **Exploding gradient** (huge, NaN) → fix with **gradient clipping** and smaller learning rate.
- **LSTM gates:** Forget (remove old), Input (add new), Output (reveal). **GRU gates:** Reset, Update.
- **LSTM = 3 gates + cell state (powerful, slower). GRU = 2 gates, no cell (simple, faster).**

---

<a id="unit-iv"></a>
# UNIT IV: GAN, Transformers, BERT and Deep Reinforcement Learning

## BLOCK A: GANs (Generative Adversarial Networks)
*(Q1, Q5, Q9, Q10)*

### Q1 + Q5. GAN, Generator and Discriminator
- **GAN = Generative Adversarial Network.** Two networks **compete**: the **Generator** (creates fake data) and the **Discriminator** (judges real vs fake). Together they learn to create realistic fake data (like images).

| | **Generator (Q1)** | **Discriminator (Q5)** |
|---|---|---|
| Role | The **creative part**: makes fake data that looks real | The **judge or detective**: decides if data is real or fake |
| Input | **Random noise** (latent vector) | A real sample or a fake from the generator |
| Output | Generated data (e.g., a fake image) | A **probability**: close to 1 = real, close to 0 = fake |
| Goal | **Fool** the discriminator | **Catch** the generator's fakes |

**Generator steps:** random noise → pass through layers that shape it → fake data produced → discriminator gives feedback → generator adjusts its weights → repeat.

**Discriminator steps:** receive data (real or fake) → analyse through layers → output probability of being real → compare with the truth → update weights to get better.

- **Adversarial training:** each improves the other until fakes look genuinely real. Without the discriminator's feedback, the generator couldn't learn.
- *Example:* generating fake human faces: early faces look strange (discriminator says "fake", 0.1); later they are realistic faces that don't belong to any real person.

### Q9. Conditional GAN (cGAN)
- A GAN whose output is **controlled by an extra condition** (usually a **label**). A normal GAN makes random samples; a cGAN makes **data of a specific requested type**.

**Architecture:**
- **Generator:** takes **noise + condition (label)** → produces fake data matching the label.
- **Discriminator:** takes **data + the same condition** → judges whether it is **real AND matches the condition**.

**Steps:** give noise + label (e.g., "cat") → generator makes a matching image → discriminator checks real and matching → both improve.

- **Use:** controlled generation, image-to-image translation, labelled image generation.
- *Example:* noise + label "7" → image of the digit 7; label "3" → a 3.

### Q10. Applications of GANs in images

| **Image Generation** | **Image Enhancement** |
|---|---|
| Realistic faces (people who don't exist) | **Super-resolution** (blurry → sharp, high resolution) |
| Art and design generation | **Denoising** (remove noise and grain) |
| **Synthetic training data** (expand small datasets) | **Inpainting** (fill missing or damaged parts) |
| **Text-to-image** generation | **Colorization** (colour old black-and-white photos) |
| | **Style transfer** (photo → painting) |

- *Example:* restoring an old family photo: super-resolution sharpens, inpainting repairs tears, colorization adds colour.

---

## BLOCK B: Transformers
*(Q2, Q6)*

### Q2. Self-Attention mechanism
- **Self-attention** lets **each word look at all the other words** in its sentence and decide which are most important for understanding it. It is the **core idea of Transformers**.
- **Why needed:** to understand a word we need its context; self-attention gathers information from all words **at once**, even far-apart ones.

**Steps:**
1. **Create Query (Q), Key (K), Value (V)** vectors for each word.
2. **Compare words:** each word's Query is compared with every word's Key → attention scores (relevance).
3. **Scores → weights:** Softmax turns scores into weights that add up to 1.
4. **Weighted sum of Values:** each word's new representation blends all Value vectors using those weights.
5. **Output:** a **context-aware** representation of each word.

- In simple terms: each word asks (Query) "which words matter to me?", checks all Keys, gives more weight to relevant ones, and blends their Values.
- **Benefits:** captures context, handles long-distance links, allows **fast parallel processing** (unlike RNNs).
- *Example:* "The animal did not cross the road because **it** was tired": "it" gives high attention to "animal".

### Q6. Positional Encoding
- **Problem:** Transformers read all words **in parallel**, so they don't know word order, yet order matters ("dog bites man" ≠ "man bites dog").
- **Positional encoding** adds **position information** to each word's embedding. Each position gets a **unique numerical pattern** (often built with sine and cosine functions), which is **added to the word vector**. The vector now carries **meaning + position**.
- **Role:** provides word order, preserves sequence structure lost by parallel processing, helps attention consider relative positions.
- Without it, a Transformer treats a sentence as an **unordered bag of words**.
- *Example:* "The cat chased the dog" vs "The dog chased the cat": same words, different meaning; positional encoding tells which noun came first.

---

## BLOCK C: BERT
*(Q3, Q7, Q11)*

### Q3. BERT architecture
- **BERT = Bidirectional Encoder Representations from Transformers** (made by Google). It understands a word using context from **both sides** (before AND after).

**Architecture:**
- Built by stacking many **Transformer encoder layers** (only the **encoder**, no decoder).
- **Input = sum of three embeddings:** **token** embedding (the word), **segment** embedding (which sentence), **position** embedding (word position).
- **Special tokens:** **[CLS]** at the start (used for classification), **[SEP]** to separate sentences.
- Each layer has **multi-head self-attention + feed-forward network**.
- **Bidirectional attention:** looks at left and right context at the same time.
- **Output:** a rich, context-aware vector for each token.
- **Sizes:** **BERT-Base = 12 encoder layers. BERT-Large = 24 encoder layers.**
- *Example:* "bank" in "I sat by the river bank" is understood as a riverside, not a money bank.

### Q7. BERT training (pre-training)
BERT is **pre-trained** on huge text (Wikipedia, books) using **two tasks**:

| Task | What happens |
|---|---|
| **1. Masked Language Model (MLM)** | About **15%** of words are randomly **hidden (masked)**; BERT predicts them using left and right context → deep bidirectional understanding |
| **2. Next Sentence Prediction (NSP)** | Given two sentences, BERT decides whether the second **logically follows** the first → sentence relationships |

**Steps:** gather huge text → tokenize, add [CLS]/[SEP], mask ~15% → apply MLM → apply NSP → update weights using backpropagation → repeat.

- Pre-training = general language learning; later **fine-tuning** for a specific task.
- *Example:* "The [MASK] is shining brightly" → predicts "sun".

### Q11. Fine-tuning BERT
- **Fine-tuning** = take the already **pre-trained BERT** and train it a little more on a **specific task** with a **small labelled dataset**. (This is **transfer learning**.)
- **Why useful:** needs far less data and time than training from scratch; high accuracy; saves computing cost.

**Steps:** start with pre-trained BERT → **add a task-specific output layer** (e.g., classification layer) → provide labelled task data → train BERT and the new layer together (BERT's weights adjust slightly) → use the fine-tuned model.

- **Tasks:** sentiment analysis, question answering, named entity recognition, text classification.
- *Example:* fine-tune on a few thousand movie reviews labelled positive/negative → accurate sentiment model.

---

## BLOCK D: Deep Reinforcement Learning
*(Q4, Q8, Q12)*

### Q4. Deep RL: definition and process
- **Reinforcement Learning (RL):** an **agent** learns by **trial and error**, getting **rewards** for good actions and penalties for bad ones. **Deep RL** = RL + **deep neural networks**, so the agent can learn complex tasks from high-dimensional data (like images).

**Key terms:**
| Term | Meaning |
|---|---|
| **Agent** | The learner / decision-maker |
| **Environment** | The world the agent interacts with |
| **State** | Current situation of the environment |
| **Action** | A move the agent can make |
| **Reward** | Feedback (positive or negative) after an action |
| **Policy** | The agent's strategy for choosing actions |

**Process:** observe the state → choose an action (using the neural network/policy) → receive a reward and move to a new state → learn (update the network to prefer high-reward actions) → repeat many times.

- *Example:* video game: sees the screen (state), makes a move (action), gets points (reward), and over many games learns the best moves.

### Q8. Deep Q-Network (DQN)
- **DQN = Q-Learning + deep neural network.** **Q-value** = expected future reward of taking an action in a state. Old Q-Learning stored Q-values in a **table**, which fails when there are too many states (e.g., every game screen). **DQN replaces the table with a neural network.**

**Architecture:**
- **Input:** current state (e.g., game screen pixels).
- **Deep neural network:** outputs a **Q-value for each possible action**.
- **Output:** the action with the **highest Q-value** is usually chosen.
- **Replay buffer (memory):** stores past experiences (state, action, reward, next state) for later training.
- **Target network:** a second, slowly-updated network that **stabilises training**.

**Working:** observe state → network predicts Q-values → choose action (usually the best, but sometimes **explores randomly**) → get reward and next state → **store experience in replay buffer** → train on **random samples** from the buffer.

- *Example:* a DQN playing a game takes screen input, estimates Q-values for left/right/jump and picks the best (used for Atari games).

### Q12. Applications of Deep RL

| Area | Applications |
|---|---|
| **Gaming** | Expert-level play (chess, Go, video games); discovers new strategies. *Example:* **AlphaGo** beat world champions at Go |
| **Robotics** | Learning to walk, grasp objects and balance; adapting to new environments. *Example:* robotic arm learns to pick and place objects |
| **Automation** | **Self-driving cars** (steer, brake, navigate); **industrial control** (optimise factory processes and energy); **resource management** (data centres, traffic signals). *Example:* traffic-control system learns to time signals |

- **Why Deep RL suits these:** sequential decisions with feedback; learns from experience without exact instructions; deep networks handle images and sensor data.

---

## Unit IV: Last-Minute Cheat Sheet
- **GAN = Generator (noise → fake data) vs Discriminator (real or fake?).** Adversarial training makes fakes realistic.
- **cGAN** = GAN + **label/condition** given to both networks → controlled output.
- **GAN uses:** faces, art, synthetic data, text-to-image, super-resolution, denoising, inpainting, colorization, style transfer.
- **Self-attention:** each word attends to all others using **Query, Key, Value** → Softmax weights → weighted sum of Values.
- **Positional encoding** gives word order (sine/cosine patterns **added** to embeddings) because Transformers read words in parallel.
- **BERT:** Transformer **encoder only**, **bidirectional**, inputs = token + segment + position embeddings, tokens **[CLS]** and **[SEP]**, Base = 12 layers, Large = 24.
- **BERT pre-training:** **MLM** (mask ~15%) + **NSP**. **Fine-tuning** = add task layer + small labelled data (transfer learning).
- **Deep RL = RL + deep networks.** Agent, Environment, State, Action, Reward, Policy.
- **DQN = neural network replaces Q-table;** uses **replay buffer** and **target network**; explores sometimes randomly.
- **Deep RL applications:** gaming (AlphaGo), robotics, automation (self-driving cars, traffic).

---

<a id="quick-answers"></a>
# FILL IN THE BLANKS (Quick Answers)

| # | Question | Answer |
|---|---|---|
| 1 | The variable predicted by a supervised model is the ___ variable | **Target** |
| 2 | GoogLeNet introduced the ___ module | **Inception** |
| 3 | Converting categorical values to numbers is called ___ encoding | **Categorical** |
| 4 | Good on training data, poor on unseen data = ___ | **Overfitting** |
| 5 | A digital image is a grid of small units called ___ | **Pixels** |
| 6 | Passing input through the layers to get output = ___ propagation | **Forward** |
| 7 | PCA is used for ___ reduction | **Dimensionality** |
| 8 | Pooling that calculates the mean of each window | **Average Pooling** |
| 9 | In supervised learning, data has features and correct ___ | **Labels** |
| 10 | Number of pixels a filter moves each time | **Stride** |
| 11 | First step in the ML workflow | **Data Collection** |
| 12 | Dividing data into parts for repeated training and validation | **Cross-validation** |
| 13 | Additional value added before the activation function | **Bias** |
| 14 | K-Means is commonly used for | **Clustering** |
| 15 | Adding a border of zeros around an image before convolution | **Padding** |
| 16 | Supervised learning = classification and ___ | **Regression** |
| 17 | Identifying unusual or abnormal data points = ___ detection | **Anomaly** |
| 18 | CNN that won ImageNet 2012 by a large margin | **AlexNet** |
| 19 | Dividing a dataset into training and testing portions | **Train-test split** |
| 20 | Standardization gives mean of ___ and standard deviation of one | **Zero** |
| 21 | Pooling that keeps the largest value of each window | **Max Pooling** |
| 22 | Machine Learning is a branch of ___ | **Artificial Intelligence** |
| 23 | Flatten layer converts a 2D/3D feature map into a ___ | **1D vector** |
| 24 | In Reinforcement Learning, the learner is called the ___ | **Agent** |
| 25 | Propagating the error backward to update weights | **Backpropagation** |
| 26 | A digital image can be represented as a ___ of numerical values | **Matrix** |

---

# MULTIPLE CHOICE QUESTIONS (Quick Answers)

| # | Question (short) | Answer |
|---|---|---|
| 1 | Main objective of GAN training | **To generate realistic data** |
| 2 | RL strategy of sometimes choosing a random action | **Exploration** |
| 3 | LSTM stands for | **Long Short-Term Memory** |
| 4 | Role of positional encoding in a Transformer | **Provide information about token order** |
| 5 | Technique initializing weights in a suitable range | **Better Initialization** |
| 6 | LSTM gate that removes information from the cell state | **Forget gate** |
| 7 | BERT is primarily designed for | **Text** |
| 8 | Technique that limits gradient size before updating weights | **Gradient Clipping** |
| 9 | Architecture with separate encoder and decoder for seq-to-seq | **Encoder-decoder architecture** |
| 10 | Full BPTT on a very long sequence is | **Slow and memory-heavy** |
| 11 | Mechanism letting a Transformer focus on important parts | **Self-attention** |
| 12 | What an RL agent receives after an action | **Reward** |
| 13 | Transformer component converting tokens into numbers | **Token embedding** |
| 14 | RNN architecture for long-term dependencies | **LSTM** |
| 15 | Problem when gradients become extremely small | **Vanishing gradient problem** |
| 16 | Component associated with a Transformer encoder | **Feed-forward network** |
| 17 | Technique that shortens the backward window | **Truncated BPTT** |
| 18 | Part of a GAN that creates samples from random input | **Generator** |
| 19 | GRU stands for | **Gated Recurrent Unit** |
| 20 | A smaller learning rate helps reduce damage caused by | **Large gradient updates** |
| 21 | Main purpose of fine-tuning a pre-trained NLP model | **Adapt it to a specific task** |
| 22 | Major feature of the Transformer architecture | **It can process sequence elements efficiently** |
| 23 | Query, Key and Value belong to which mechanism | **Attention** |
| 24 | Task where long-range dependencies matter | **Machine translation** |
| 25 | What BERT's bidirectional nature allows | **Context from both directions** |

---

*End of notes. Best of luck for the exam!*
