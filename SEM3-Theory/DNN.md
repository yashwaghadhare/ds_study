**DNN Question Bank**

**UNIT I**

**Q1. Explain Forward Propagation and its steps with suitable mathematical expressions.**

**What is Forward Propagation?**

'Forward' means moving ahead, and 'Propagation' means passing something along. So Forward Propagation means passing the input data forward through the layers of a neural network - from the input layer to the output layer - to produce a prediction.

In simple words, it is how a neural network takes an input and calculates its answer.

**The Steps of Forward Propagation**

- **Step 1 - Take the input:** The input features (for example, x1, x2) enter the network.
- **Step 2 - Multiply by weights and add bias:** Each input is multiplied by its weight and a bias is added. The formula is: z = (w1·x1 + w2·x2 + ... + wn·xn) + b.
- **Step 3 - Apply an activation function:** The result z is passed through an activation function (like ReLU or Sigmoid) to add non-linearity: a = f(z).
- **Step 4 - Pass to the next layer:** The output 'a' becomes the input to the next layer, and steps 2-3 repeat.
- **Step 5 - Produce the output:** The final layer produces the network's prediction (ŷ).

**Key Mathematical Expressions**

- Weighted sum: z = Σ (wᵢ · xᵢ) + b
- Activation: a = f(z), where f may be Sigmoid (1 ÷ (1 + e⁻ᶻ)) or ReLU (max(0, z)).

**Why is Forward Propagation Important?**

- It is how the network makes predictions.
- It produces the output needed to measure error.
- It is the first half of training (the second half is backpropagation).

**Real-life example:** To predict a house price, forward propagation takes inputs like size and location, multiplies them by weights, adds bias, applies an activation function at each layer, and finally outputs a predicted price. This step-by-step forward flow shows how forward propagation works.

**Q2. Differentiate between Overfitting and Underfitting.**

**Introduction**

When training a machine-learning model, two common problems can occur: overfitting and underfitting. Both reduce the model's usefulness on new data, but in opposite ways. Let us understand and compare them.

**What is Overfitting?**

'Overfitting' happens when a model learns the training data too well - including its noise and tiny details.

- It performs excellently on training data but poorly on new data.
- The model is too complex.
- It is like a student who memorises answers but cannot solve new questions.

**What is Underfitting?**

'Underfitting' happens when a model is too simple and fails to learn even the basic patterns in the data.

- It performs poorly on both training data AND new data.
- The model is too weak.
- It is like a student who did not study enough and fails everywhere.

**Key Differences**

- **Cause:** Overfitting is from too much complexity; underfitting from too little.
- **Training accuracy:** Overfitting is high; underfitting is low.
- **Test accuracy:** Both are low, but for different reasons.
- **Fix for overfitting:** more data, regularization, dropout, simpler model.
- **Fix for underfitting:** more complex model, more features, more training.

**Why is This Important?**

- The goal is a balanced model that generalises well.
- Recognising each problem guides the right fix.
- It ensures reliable real-world performance.

**Real-life example:** A model predicting exam results gets 99% on training data but 55% on new data - that is overfitting. Another model gets only 60% on both training and new data - that is underfitting. The ideal model performs well on both, showing the difference between overfitting and underfitting.

**Q3. Evaluate the use of Dropout in neural networks.**

**What is Dropout?**

'Dropout' means temporarily dropping (turning off) some neurons in a neural network during training. It is a technique used to prevent overfitting - when a model learns training data too well and fails on new data.

During each training step, a random set of neurons is switched off, so the network cannot depend too heavily on any single neuron.

**How Dropout Works**

- During training, each neuron is randomly 'dropped' with a certain probability (for example, 0.5).
- The dropped neurons do not participate in that training step.
- Different neurons are dropped each time, so the network learns many independent patterns.
- During testing, all neurons are used (no dropout), giving a strong combined result.

**The Use and Benefits of Dropout**

- **Reduces overfitting:** The network cannot rely on specific neurons, so it generalises better.
- **Improves robustness:** It forces neurons to learn useful features independently.
- **Acts like averaging many networks:** Training with random dropouts is like training many smaller networks and combining them.
- **Simple and effective:** It is easy to add and works well.

**Points to Consider**

- Too much dropout can cause underfitting.
- The dropout rate must be chosen carefully.

**Why is Dropout Important?**

- Overfitting is a major problem in deep networks.
- Dropout is a simple, powerful cure.
- It improves performance on unseen data.

**Real-life example:** A deep network for image classification overfits, scoring 98% on training but 70% on test images. Adding dropout of 0.5 randomly disables half the neurons each step, forcing better learning. Test accuracy rises to 88%. This shows the value of dropout in neural networks.

**Q4. Describe Accuracy, Precision, Recall, and F1-Score.**

**Introduction**

After training a classification model, we must measure how good it is. Four common measures are Accuracy, Precision, Recall, and F1-Score. They are based on four outcomes: True Positives (TP), True Negatives (TN), False Positives (FP), and False Negatives (FN). Let us understand each measure.

**What is Accuracy?**

'Accuracy' is the overall correctness - how many predictions were right out of all predictions.

- Formula: Accuracy = (TP + TN) ÷ (TP + TN + FP + FN).
- It can be misleading when the data is unbalanced.

**What is Precision?**

'Precision' answers: of all items predicted positive, how many were truly positive?

- Formula: Precision = TP ÷ (TP + FP).
- High precision means few false alarms.

**What is Recall?**

'Recall' answers: of all actual positive items, how many did the model correctly find?

- Formula: Recall = TP ÷ (TP + FN).
- High recall means few missed cases.

**What is F1-Score?**

'F1-Score' is the balance (harmonic mean) of precision and recall.

- Formula: F1 = 2 × (Precision × Recall) ÷ (Precision + Recall).
- It is high only when both precision and recall are high.

**Why are These Measures Important?**

- Accuracy alone can be misleading; the others give a fuller picture.
- Precision and recall reveal different kinds of errors.
- F1 balances both in one number.

**Real-life example:** A disease-detection model is tested. Accuracy shows overall correctness, but recall is watched closely so sick patients are not missed (few false negatives), while precision checks that healthy people are not wrongly flagged. The F1-score balances both. This shows the role of accuracy, precision, recall, and F1-score.

**Q5. Describe the Backpropagation process used for neural network learning.**

**What is Backpropagation?**

'Back' means going backward, and 'Propagation' means passing something along. So Backpropagation means passing the error backward through the neural network - from the output layer to the input layer - to update the weights so the network learns.

It is the main method by which neural networks learn from their mistakes.

**The Backpropagation Process (Step by Step)**

- **Step 1 - Forward propagation:** The input passes forward through the network to produce a prediction.
- **Step 2 - Calculate the error (loss):** The prediction is compared with the correct answer using a loss function, giving the error.
- **Step 3 - Send the error backward:** The error is passed backward through the layers.
- **Step 4 - Compute gradients:** Using the chain rule of calculus, the network calculates how much each weight contributed to the error (the gradient).
- **Step 5 - Update the weights:** Each weight is adjusted a little to reduce the error, using an optimizer like Gradient Descent: new weight = old weight − (learning rate × gradient).
- **Step 6 - Repeat:** This cycle repeats over many examples until the error is small.

**Why is Backpropagation Important?**

- It is how a neural network actually learns.
- It efficiently updates millions of weights.
- Without it, deep learning would not be possible.

**The Role of Gradients**

- The gradient shows the direction to change each weight to reduce error.
- Small, repeated updates gradually improve the network.

**Real-life example:** A network wrongly predicts a cat image as a dog. Backpropagation calculates the error, sends it backward, finds which weights caused the mistake, and adjusts them. After many such corrections, the network correctly recognises cats. This shows how backpropagation drives neural network learning.

**Q6. Discuss Regularization and its L1 and L2 approaches.**

**What is Regularization?**

'Regularization' means adding a control or penalty to keep a model from becoming too complex. Its main purpose is to prevent overfitting - when a model fits the training data too closely and fails on new data.

It works by discouraging very large weights, which keeps the model simpler and more general.

**How Regularization Works**

- A penalty term is added to the loss (error) function.
- This penalty grows when weights become too large.
- The model must balance fitting the data AND keeping weights small.
- The result is a simpler model that generalises better.

**L1 Regularization (Lasso)**

- It adds the sum of the absolute values of the weights as a penalty.
- Penalty term: λ × Σ |w|.
- It tends to push some weights exactly to zero.
- This performs feature selection - unimportant features are removed.

**L2 Regularization (Ridge)**

- It adds the sum of the squares of the weights as a penalty.
- Penalty term: λ × Σ w².
- It shrinks weights towards zero but rarely makes them exactly zero.
- It spreads the effect across all weights, keeping them small.

**L1 vs L2 (Key Difference)**

- **L1:** can make weights zero → removes features (sparse model).
- **L2:** shrinks weights smoothly → keeps all features but small.

**Why is Regularization Important?**

- It reduces overfitting.
- It improves performance on new data.
- L1 also helps select important features.

**Real-life example:** A model predicting house prices overfits with very large weights. Applying L2 regularization shrinks the weights, making the model simpler and better on new houses. Using L1 instead sets some unimportant feature weights to zero, removing them. This shows regularization and its L1 and L2 approaches.

**Q7. Compare MAE, MSE, RMSE, and R-squared regression metrics.**

**Introduction**

Regression models predict continuous numbers (like prices). To measure how good they are, we use error metrics. Four common ones are MAE, MSE, RMSE, and R-squared. Let us understand and compare them.

**What is MAE (Mean Absolute Error)?**

- It is the average of the absolute differences between predicted and actual values.
- Formula: MAE = (1/n) × Σ |actual − predicted|.
- It is easy to understand and treats all errors equally.

**What is MSE (Mean Squared Error)?**

- It is the average of the squared differences between predicted and actual values.
- Formula: MSE = (1/n) × Σ (actual − predicted)².
- Squaring punishes large errors more heavily.

**What is RMSE (Root Mean Squared Error)?**

- It is the square root of MSE.
- Formula: RMSE = √MSE.
- It brings the error back to the same unit as the data, so it is easier to interpret.

**What is R-squared?**

- It measures how much of the variation in the data the model explains.
- Its value ranges from 0 to 1 (higher is better).
- An R-squared of 0.9 means the model explains 90% of the variation.

**Comparison**

- **MAE:** simple, treats all errors equally.
- **MSE:** penalises big errors, but its unit is squared.
- **RMSE:** like MSE but in the original unit, easy to read.
- **R-squared:** shows overall fit as a percentage, not an error amount.

**Why is This Important?**

- Different metrics highlight different aspects of performance.
- Choosing the right metric depends on the problem.

**Real-life example:** For a house-price model, MAE says the average error is ₹2 lakh, RMSE says ₹3 lakh (larger because big errors are punished), and R-squared of 0.85 says the model explains 85% of price variation. Together these metrics evaluate the model - showing how MAE, MSE, RMSE, and R-squared compare.

**Q8. Explain the working principle of Adam Optimization.**

**What is Adam Optimization?**

Adam stands for Adaptive Moment Estimation. It is a popular optimization algorithm used to update the weights of a neural network during training so that the error is reduced quickly and smoothly.

It combines the best ideas of two other methods - Momentum and RMSProp - to become fast and reliable.

**The Two Ideas Adam Combines**

- **Momentum:** It remembers the direction of past gradients (like a rolling ball gaining speed), which smooths and speeds up learning.
- **RMSProp (adaptive learning rate):** It adjusts the step size for each weight based on how large its recent gradients were.

**The Working Principle of Adam (Briefly)**

- **Compute gradients:** For each weight, find the gradient (direction of error reduction).
- **First moment (mean):** Keep a moving average of the gradients - this is the momentum part.
- **Second moment (variance):** Keep a moving average of the squared gradients - this scales the step size.
- **Bias correction:** Adjust these averages so they are accurate early in training.
- **Update weights:** Combine both to update each weight with its own suitable step size.

**Advantages of Adam**

- **Fast convergence:** It reaches a good solution quickly.
- **Adaptive steps:** Each weight gets its own learning rate.
- **Works well by default:** It needs little tuning and suits most problems.

**Why is Adam Important?**

- It trains deep networks efficiently.
- It combines speed and stability.
- It is one of the most widely used optimizers.

**Real-life example:** While training an image classifier, plain Gradient Descent learns slowly and unevenly. Switching to Adam, which uses momentum and adaptive step sizes, makes the training faster and smoother, reaching high accuracy in fewer steps. This shows the working principle and benefit of Adam optimization.

**Q9. Evaluate the concept of Early Stopping and its role in model training.**

**What is Early Stopping?**

'Early Stopping' means stopping the training of a model before it runs for all the planned rounds (epochs) - specifically, stopping at the right moment when the model is performing best on new data.

Its main purpose is to prevent overfitting, which happens when a model trains too long and starts memorising the training data.

**Why Early Stopping is Needed**

- At first, training improves performance on both training and validation data.
- After a point, training accuracy keeps rising but validation accuracy starts falling - this is overfitting.
- Early stopping catches this turning point and stops training there.

**How Early Stopping Works (Step by Step)**

- **Split the data:** Keep a separate validation set.
- **Monitor validation performance:** After each epoch, check the validation error.
- **Watch for the best point:** Note when validation error is lowest.
- **Stop when it worsens:** If validation error stops improving for several epochs, stop training.
- **Keep the best model:** Save the weights from the best-performing epoch.

**The Role and Benefits of Early Stopping**

- **Prevents overfitting:** It stops before the model memorises noise.
- **Saves time:** It avoids unnecessary extra training.
- **Improves generalization:** The saved model performs better on new data.

**Why is Early Stopping Important?**

- It is a simple, effective way to fight overfitting.
- It saves computing time and resources.
- It keeps the best version of the model.

**Real-life example:** A network's validation accuracy rises for 20 epochs, then starts dropping while training accuracy keeps climbing - a sign of overfitting. Early stopping halts training at epoch 20 and keeps that model. This gives the best performance on new data, showing the role of early stopping.

**Q10. Describe Data Augmentation and its importance in deep learning.**

**What is Data Augmentation?**

'Data' means the training examples, and 'Augmentation' means increasing or expanding. So Data Augmentation means creating new, slightly changed versions of existing training data to increase the amount and variety of data.

It is especially useful when we do not have enough data, which is common in deep learning.

**How Data Augmentation Works**

- The original data is modified in small ways to make new examples.
- The label stays the same (a rotated cat is still a cat).
- This gives the model more varied examples to learn from.

**Common Augmentation Techniques (for Images)**

- **Rotation:** Turning the image by some degrees.
- **Flipping:** Mirroring the image horizontally or vertically.
- **Zooming and cropping:** Enlarging or cutting parts of the image.
- **Shifting:** Moving the image slightly.
- **Brightness/color changes:** Adjusting lighting or colours.
- **Adding noise:** Introducing small random changes.

**The Importance of Data Augmentation**

- **Increases data size:** It creates more training examples for free.
- **Reduces overfitting:** More variety stops the model from memorising.
- **Improves generalization:** The model handles new, varied inputs better.
- **Saves cost:** It avoids the expense of collecting more real data.

**Why is Data Augmentation Important in Deep Learning?**

- Deep models need large amounts of data.
- Collecting real data is costly and slow.
- Augmentation cheaply boosts data quantity and quality.

**Real-life example:** A model to recognise cats has only 1,000 photos. By rotating, flipping, zooming, and changing brightness, thousands of new varied images are created. The model now sees cats in many positions and lighting, so it generalises better to real photos. This shows the importance of data augmentation.

**Q11. Explain Gradient Descent as a neural network optimization method.**

**What is Gradient Descent?**

'Gradient' means slope or direction of change, and 'Descent' means going down. So Gradient Descent means an optimization method that gradually moves the model's weights 'downhill' to reduce the error, step by step, until the error is as small as possible.

Imagine standing on a hill in fog and taking small steps downward to reach the lowest point - that is gradient descent.

**How Gradient Descent Works (Step by Step)**

- **Step 1 - Start with random weights:** The network begins with random weight values.
- **Step 2 - Calculate the error:** It measures how wrong the prediction is using a loss function.
- **Step 3 - Compute the gradient:** It finds the slope of the error with respect to each weight (the direction that increases error).
- **Step 4 - Update the weights:** It moves each weight in the opposite direction of the gradient: new weight = old weight − (learning rate × gradient).
- **Step 5 - Repeat:** This continues until the error reaches a minimum.

**The Role of the Learning Rate**

- The 'learning rate' controls the step size.
- Too large: it may overshoot the minimum.
- Too small: it learns very slowly.

**Types of Gradient Descent**

- **Batch:** uses all data each step.
- **Stochastic (SGD):** uses one example at a time.
- **Mini-batch:** uses small groups (most common).

**Why is Gradient Descent Important?**

- It is the core method for training neural networks.
- It reduces error efficiently.
- It underlies advanced optimizers like Adam.

**Real-life example:** A network predicting prices starts with high error. Gradient descent computes the slope and nudges the weights downhill a little each step. After many steps, the error reaches a low minimum and predictions become accurate. This shows how gradient descent optimizes a neural network.

**Q12. Discuss the role of Activation Functions in neural networks.**

**What is an Activation Function?**

An 'Activation Function' is a mathematical function applied to the output of a neuron. It decides whether and how strongly a neuron should 'fire' (pass on its signal). Most importantly, it adds non-linearity to the network.

Without activation functions, a neural network would just be a simple linear equation, unable to learn complex patterns.

**The Role of Activation Functions**

- **Add non-linearity:** They let the network learn complex, curved patterns, not just straight lines.
- **Decide neuron output:** They transform the weighted sum into the neuron's final output.
- **Enable deep learning:** They make stacking many layers meaningful.
- **Control signal strength:** They squash or shape values into useful ranges.

**Common Activation Functions**

- **Sigmoid:** Squashes values between 0 and 1; used for probabilities. Formula: 1 ÷ (1 + e⁻ᶻ).
- **ReLU (Rectified Linear Unit):** Outputs the value if positive, else 0; fast and popular. Formula: max(0, z).
- **Tanh:** Squashes values between −1 and 1; centred around zero.
- **Softmax:** Converts scores into probabilities that sum to 1; used for multiclass output.

**Why Non-linearity Matters**

- Real-world data (images, language) has complex patterns.
- Only non-linear functions can capture these patterns.
- Without them, extra layers add no real power.

**Why are Activation Functions Important?**

- They give neural networks their learning power.
- They enable complex pattern recognition.
- Choosing the right one improves performance.

**Real-life example:** In an image classifier, ReLU is used in hidden layers to learn complex features quickly, and Softmax is used in the output layer to give the probability of each class (cat, dog, bird). These activation functions let the network learn and decide correctly - showing their vital role.

**Q13. Explain Cross-Validation and its major techniques.**

**What is Cross-Validation?**

'Cross-Validation' is a method to test how well a model performs on new, unseen data by dividing the data into parts and training and testing on different combinations of those parts.

Its main purpose is to give a fair, reliable estimate of model performance and to reduce the chance of misleading results from a single lucky or unlucky split.

**Why Cross-Validation is Needed**

- A single train-test split may give results that depend on luck.
- Cross-validation tests the model on several different splits.
- This gives a more trustworthy average performance.

**Major Techniques of Cross-Validation**

- **K-Fold Cross-Validation:** The data is divided into K equal parts (folds). The model is trained on K−1 folds and tested on the remaining one. This repeats K times, each fold acting as the test set once. The results are averaged.
- **Stratified K-Fold:** Like K-Fold, but each fold keeps the same class balance as the full data - useful for unbalanced datasets.
- **Leave-One-Out (LOOCV):** Each single example is used once as the test set while all others train the model. Very thorough but slow.
- **Holdout Method:** The simplest - the data is split once into training and testing sets.

**Benefits of Cross-Validation**

- Gives a reliable performance estimate.
- Uses data efficiently (every part is used for testing once).
- Helps detect overfitting.

**Why is Cross-Validation Important?**

- It ensures the model truly generalises.
- It reduces dependence on one split.
- It supports fair model comparison.

**Real-life example:** With 1,000 records, 5-fold cross-validation splits the data into 5 parts. The model trains on 4 parts and tests on 1, repeating 5 times so every part is tested once. Averaging the 5 scores gives a reliable accuracy. This shows cross-validation and its major techniques.

**Q14. Describe RMSProp optimization and its working principle.**

**What is RMSProp?**

RMSProp stands for Root Mean Square Propagation. It is an optimization algorithm used to update the weights of a neural network. Its special feature is that it gives each weight its own adjusting (adaptive) learning rate, based on how large that weight's recent gradients have been.

It was designed to fix problems where a single fixed learning rate is too big for some weights and too small for others.

**Why RMSProp is Needed**

- In plain gradient descent, all weights use the same learning rate.
- Some weights have large gradients and need small steps; others need larger steps.
- RMSProp adapts the step size for each weight automatically.

**The Working Principle of RMSProp (Briefly)**

- **Compute gradients:** For each weight, find its gradient.
- **Track squared gradients:** Keep a moving average of the squared gradients for each weight.
- **Scale the step:** Divide the learning rate by the square root of this average, so weights with large gradients take smaller steps and vice versa.
- **Update the weights:** Apply the scaled update to each weight.

**Advantages of RMSProp**

- **Adaptive learning rate:** Each weight gets a suitable step size.
- **Handles varying gradients:** It works well when gradients differ a lot.
- **Stable and efficient:** It trains smoothly, especially for RNNs.

**Why is RMSProp Important?**

- It speeds up and stabilises training.
- It is a key idea inside the popular Adam optimizer.
- It handles difficult, uneven error surfaces well.

**Real-life example:** While training a network, some weights have very large gradients that cause unstable jumps. RMSProp tracks the squared gradients and shrinks the step size for those weights, making training smooth and steady. This shows the working principle of RMSProp optimization.

**Q15. Describe Feature Selection and its role in model improvement.**

**What is Feature Selection?**

'Features' are the input variables (columns) used to make predictions - like age, income, or temperature. 'Selection' means choosing. So Feature Selection means choosing only the most useful and important features and removing the useless or irrelevant ones before training a model.

The goal is to keep what helps and drop what does not.

**Why Feature Selection is Needed**

- Not all features are useful; some add noise.
- Too many features slow training and can cause overfitting.
- Removing weak features makes the model simpler and better.

**Common Feature Selection Methods**

- **Filter methods:** Rank features using statistics (like correlation) and keep the top ones.
- **Wrapper methods:** Try different feature subsets and pick the set that gives the best model performance.
- **Embedded methods:** Feature selection happens during training (for example, L1 regularization sets weak feature weights to zero).

**The Role of Feature Selection in Model Improvement**

- **Improves accuracy:** Removing noise helps the model focus on what matters.
- **Reduces overfitting:** Fewer, relevant features generalise better.
- **Speeds up training:** Less data to process means faster models.
- **Simplifies the model:** Easier to understand and maintain.

**Why is Feature Selection Important?**

- It boosts performance and speed.
- It reduces overfitting.
- It makes models cleaner and more interpretable.

**Real-life example:** To predict loan approval, a dataset has 50 features, but many (like a customer's favourite colour) are irrelevant. Feature selection keeps important ones like income and credit score and drops useless ones. The model becomes faster and more accurate. This shows the role of feature selection in model improvement.

**Q16. Interpret the components of a Confusion Matrix.**

**What is a Confusion Matrix?**

A 'Confusion Matrix' is a table that shows how well a classification model performed by comparing its predictions with the actual correct answers. It reveals where the model got 'confused' - that is, where it made mistakes.

It is usually a 2×2 table for two-class problems.

**The Four Components of a Confusion Matrix**

- **True Positive (TP):** The model predicted positive, and it really was positive. (Correct)
- **True Negative (TN):** The model predicted negative, and it really was negative. (Correct)
- **False Positive (FP):** The model predicted positive, but it was actually negative. (Wrong - a false alarm; also called Type I error.)
- **False Negative (FN):** The model predicted negative, but it was actually positive. (Wrong - a miss; also called Type II error.)

**How to Interpret Them**

- TP and TN are the correct predictions - we want these to be high.
- FP and FN are the mistakes - we want these to be low.
- FP is raising an alarm when there was no problem.
- FN is missing a real problem - often the most dangerous.

**Measures Built From These Components**

- Accuracy = (TP + TN) ÷ total.
- Precision = TP ÷ (TP + FP).
- Recall = TP ÷ (TP + FN).

**Why is the Confusion Matrix Important?**

- It shows not just how many, but what type of errors were made.
- It helps calculate precision, recall, and F1.
- It reveals if the model is biased toward one class.

**Real-life example:** A COVID test model gives TP = 90 (sick correctly detected), TN = 850 (healthy correctly cleared), FP = 10 (healthy wrongly flagged sick), FN = 50 (sick wrongly cleared). The high FN is worrying because sick people are missed. Interpreting these components shows exactly where the model needs improvement.

**UNIT II**

**Q1. Describe how a computer represents a digital image as numerical data.**

**What is a Digital Image?**

A 'Digital Image' is a picture stored in a computer. Although we see it as a photo, the computer actually stores it as numbers. Understanding this is the foundation of image processing and CNNs.

**How a Computer Represents an Image**

- **Pixels are the building blocks:** An image is made of tiny dots called pixels. Each pixel is one small square of colour.
- **Pixels form a grid:** These pixels are arranged in a grid of rows and columns, like a chessboard.
- **Each pixel is a number:** The brightness or colour of each pixel is stored as a number.
- **The image becomes a matrix:** The whole image is stored as a matrix (a grid of numbers).

**Grayscale vs Colour Images**

- **Grayscale image:** Each pixel has one number from 0 (black) to 255 (white), with grays in between. The image is a single 2D matrix.
- **Colour image (RGB):** Each pixel has three numbers - for Red, Green, and Blue - each from 0 to 255. The image is like three stacked matrices (three channels).

**Why Numbers?**

- Computers only understand numbers, not pictures.
- Storing pixels as numbers lets the computer process, edit, and analyse images.
- CNNs work directly on these pixel numbers.

**Why is This Important?**

- It explains how machines 'see' images.
- It is the basis for all computer vision and CNN work.
- It shows why images become matrices for processing.

**Real-life example:** A small 3×3 grayscale image of a corner might be stored as the matrix [[0,0,255],[0,255,255],[255,255,255]], where 0 is black and 255 is white. A colour photo stores three such matrices (Red, Green, Blue). This shows how a computer represents a digital image as numerical data.

**Q2. Explain the working of a convolution layer using a filter and feature map.**

**What is a Convolution Layer?**

The 'Convolution Layer' is the main building block of a CNN (Convolutional Neural Network). Its job is to detect features (like edges, corners, and shapes) in an image using small grids of numbers called filters.

**What is a Filter (Kernel)?**

A 'Filter' (or kernel) is a small matrix of numbers (for example, 3×3) that is designed to detect a particular feature, such as a vertical edge.

**What is a Feature Map?**

A 'Feature Map' is the output produced after the filter slides over the image. It highlights where the feature was found in the image.

**How the Convolution Layer Works (Step by Step)**

- **Step 1 - Place the filter:** The small filter is placed on the top-left corner of the image.
- **Step 2 - Multiply and add:** Each filter number is multiplied by the pixel beneath it, and all products are added to get one number.
- **Step 3 - Record the result:** This single number is placed in the feature map.
- **Step 4 - Slide the filter:** The filter moves (strides) to the next position, and steps 2-3 repeat.
- **Step 5 - Complete the feature map:** After covering the whole image, the full feature map is built.

**Why This Works**

- Where the image matches the filter's pattern, the result is high.
- So the feature map lights up where the feature exists.

**Why is the Convolution Layer Important?**

- It automatically detects useful image features.
- It shares filters across the image, saving parameters.
- It is the core of image recognition in CNNs.

**Real-life example:** A 3×3 filter designed to detect vertical edges slides across a photo of a building. Wherever there is a vertical edge, the filter produces high values in the feature map, marking the building's vertical lines. This shows how a convolution layer uses a filter to create a feature map.

**Q3. Differentiate between Max Pooling and Average Pooling.**

**What is Pooling?**

'Pooling' is a step in a CNN that reduces the size of a feature map by summarising small regions into single values. This makes the network faster and more robust. Two common types are Max Pooling and Average Pooling. Let us compare them.

**What is Max Pooling?**

Max Pooling looks at each small window of the feature map and keeps only the largest (maximum) value.

- It captures the strongest, most prominent feature in each region.
- Example: for the window [1, 3, 2, 4], it keeps 4.
- It highlights the most important features.

**What is Average Pooling?**

Average Pooling looks at each small window and keeps the average (mean) of the values.

- It captures the overall, smoothed information of each region.
- Example: for the window [1, 3, 2, 4], it keeps (1+3+2+4) ÷ 4 = 2.5.
- It gives a gentler, blended summary.

**Key Differences**

- **What is kept:** Max keeps the maximum; Average keeps the mean.
- **Effect:** Max highlights strong features; Average smooths them.
- **Use:** Max is more common (better for sharp features); Average gives a softer summary.
- **Sensitivity:** Max focuses on the strongest signal; Average considers all values.

**Why is Pooling Important?**

- It reduces computation and memory.
- It reduces overfitting.
- It makes the network less sensitive to small shifts in the image.

**Real-life example:** For a feature map region [[1, 3], [2, 4]], Max Pooling outputs 4 (the strongest feature), while Average Pooling outputs 2.5 (the overall level). If detecting a sharp edge, Max Pooling is preferred to keep the strong signal. This shows the difference between max and average pooling.

**Q4. Compare the roles of ReLU, Sigmoid, and Softmax activation functions in CNNs.**

**Introduction**

Activation functions add non-linearity and shape the outputs in a neural network. In CNNs, three important ones are ReLU, Sigmoid, and Softmax. Each has a different role. Let us compare them.

**ReLU (Rectified Linear Unit)**

- **What it does:** Outputs the value if it is positive, and 0 if it is negative. Formula: max(0, z).
- **Role in CNNs:** Used in the hidden (convolution) layers to introduce non-linearity.
- **Advantage:** Fast, simple, and avoids the vanishing gradient problem.

**Sigmoid**

- **What it does:** Squashes any value into a range between 0 and 1. Formula: 1 ÷ (1 + e⁻ᶻ).
- **Role in CNNs:** Used in the output layer for binary (two-class) problems, giving a probability.
- **Limitation:** Can suffer from vanishing gradients in deep layers.

**Softmax**

- **What it does:** Converts a set of scores into probabilities that add up to 1.
- **Role in CNNs:** Used in the output layer for multiclass (many-class) problems.
- **Advantage:** Shows the probability of each class, and the highest is chosen.

**Comparison Summary**

- **ReLU:** hidden layers, adds non-linearity.
- **Sigmoid:** output for two classes (probability 0-1).
- **Softmax:** output for many classes (probabilities summing to 1).

**Why is This Comparison Important?**

- Using the right function in the right place improves performance.
- Hidden layers and output layers need different functions.

**Real-life example:** In a CNN that classifies animal photos, ReLU is used in the convolution layers to learn features. If the task is cat-vs-dog (two classes), Sigmoid gives the output probability. If the task is cat-vs-dog-vs-bird (many classes), Softmax gives a probability for each. This shows the roles of ReLU, Sigmoid, and Softmax in CNNs.

**Q5. Evaluate the concept of CNN and its ability to detect image features.**

**What is a CNN?**

CNN stands for Convolutional Neural Network. It is a special type of neural network designed mainly to work with images. It can automatically detect features in an image - like edges, shapes, and objects - without a human having to describe them.

**Why CNNs are Good at Images**

- Ordinary networks treat every pixel separately and need too many connections.
- CNNs use small filters that slide over the image, sharing them across the whole picture.
- This makes them efficient and good at spotting patterns anywhere in the image.

**How a CNN Detects Image Features (Layer by Layer)**

- **Convolution layers:** Use filters to detect features, producing feature maps.
- **ReLU activation:** Adds non-linearity so complex patterns can be learned.
- **Pooling layers:** Shrink the feature maps, keeping important information and reducing computation.
- **Fully connected layers:** Combine all detected features to make the final decision.

**Hierarchical Feature Detection**

- **Early layers:** Detect simple features like edges and corners.
- **Middle layers:** Combine these into shapes and textures.
- **Deep layers:** Combine shapes into whole objects (like a face or a car).

**Why CNNs are Powerful**

- They learn features automatically from data.
- They detect features anywhere in the image (position-invariant).
- They build complex understanding from simple parts.

**Why is This Important?**

- CNNs power image classification, face recognition, and object detection.
- They removed the need for manual feature design.
- They achieve very high accuracy on images.

**Real-life example:** A CNN recognising faces first detects edges in early layers, then eyes and noses in middle layers, and finally full faces in deep layers. Because it builds features step by step, it can recognise a face anywhere in the photo. This evaluates the CNN concept and its ability to detect image features.

**Q6. Discuss the role of filters in detecting different visual patterns in an image.**

**What is a Filter?**

A 'Filter' (also called a kernel) is a small matrix of numbers (for example, 3×3) used in a CNN's convolution layer. Each filter is designed or learned to detect one specific visual pattern in an image, such as an edge, a curve, or a texture.

**How Filters Detect Patterns**

- A filter slides over the image, region by region.
- At each spot, it multiplies its numbers with the pixel values and adds them up.
- If the region matches the filter's pattern, the result is a high value; if not, a low value.
- The output (feature map) lights up wherever that pattern appears.

**Different Filters Detect Different Patterns**

- **Edge-detecting filters:** Highlight boundaries where brightness changes sharply.
- **Vertical/horizontal line filters:** Detect vertical or horizontal edges.
- **Corner filters:** Detect points where edges meet.
- **Texture filters:** Detect repeated patterns and surfaces.
- **Complex filters (deeper layers):** Detect shapes, parts, and whole objects.

**Filters are Learned Automatically**

- In a CNN, filters are not hand-made; the network learns the best filter values during training.
- Early-layer filters learn simple patterns; deeper-layer filters learn complex ones.

**The Role and Importance of Filters**

- They are the tools that actually detect features.
- Many filters together capture many kinds of patterns.
- They build up from simple to complex features across layers.

**Why is This Important?**

- Filters are the heart of how CNNs 'see'.
- They enable automatic feature detection.
- They allow hierarchical understanding of images.

**Real-life example:** In a CNN analysing a photo of a zebra, one filter detects vertical edges (the stripes), another detects curves (the body outline), and deeper filters combine these to recognise the zebra shape. Different filters detecting different patterns show their crucial role in image analysis.

**Q7. Explain the importance of pooling in reducing computations, overfitting, and sensitivity to small position shifts.**

**What is Pooling?**

'Pooling' is a step in a CNN that reduces the size of a feature map by summarising each small region into a single value (using the maximum or the average). It keeps the important information while shrinking the data.

**How Pooling Works (Briefly)**

- A small window (for example, 2×2) slides over the feature map.
- For each window, pooling keeps one value (the maximum in max pooling, or the mean in average pooling).
- This produces a smaller feature map.

**The Importance of Pooling**

- **Reduces computations:** By shrinking feature maps, pooling reduces the number of values the network must process, making it faster and lighter.
- **Reduces overfitting:** With fewer values and less detail, the model is less likely to memorise noise, so it generalises better.
- **Reduces sensitivity to small position shifts:** If a feature moves slightly in the image, pooling still captures it, because it summarises a whole region. This makes the CNN robust to small movements (called translation invariance).

**In Simple Terms**

- Pooling keeps the 'gist' of each region and throws away tiny, unimportant details.
- This makes the network faster, more general, and more stable.

**Why is Pooling Important?**

- It keeps CNNs efficient enough to train.
- It improves performance on new images.
- It ensures features are detected even if slightly shifted.

**Real-life example:** A CNN detects a cat's ear in a photo. If the same ear appears a few pixels to the left in another photo, max pooling still captures the strong 'ear' signal from that region. Meanwhile, the smaller feature maps speed up training and reduce overfitting. This shows the importance of pooling in three ways.

**Q8. Differentiate image classification, face recognition, and object detection as applications of CNNs.**

**Introduction**

CNNs are used for many image tasks. Three important applications are image classification, face recognition, and object detection. They sound similar but do different jobs. Let us compare them.

**What is Image Classification?**

Image Classification means labelling an entire image with a single category.

- It answers: 'What is this image?'
- It gives one label for the whole picture.
- Example: labelling a photo as 'cat' or 'dog'.

**What is Face Recognition?**

Face Recognition means identifying WHO a specific person is from their face.

- It answers: 'Whose face is this?'
- It matches a face to a known identity.
- Example: unlocking a phone by recognising the owner's face.

**What is Object Detection?**

Object Detection means finding AND locating multiple objects in an image, drawing boxes around each.

- It answers: 'What objects are here, and where are they?'
- It gives labels plus locations (bounding boxes).
- Example: a self-driving car spotting cars, people, and signs with boxes around each.

**Key Differences**

- **Image classification:** one label for the whole image.
- **Face recognition:** identifies a specific person.
- **Object detection:** finds and locates many objects with boxes.
- **Output:** a label / an identity / labels plus locations.

**Why is This Comparison Important?**

- Each task suits different real-world needs.
- Choosing the right one depends on the goal.
- All three are powered by CNNs.

**Real-life example:** For a single photo of a street: image classification might label it 'street scene'; face recognition might identify a specific pedestrian as 'Rahul'; object detection would draw boxes around each car, person, and traffic light. This shows the difference between the three CNN applications.

**Q9. Explain the significance of stride and padding in convolution.**

**Introduction**

In a CNN's convolution layer, a filter slides over the image to detect features. Two settings control how this sliding happens: stride and padding. They affect the size of the output and how the edges are handled. Let us understand each.

**What is Stride?**

'Stride' is the number of pixels by which the filter moves each time it slides across the image.

- A stride of 1 means the filter moves one pixel at a time (detailed, larger output).
- A stride of 2 means it jumps two pixels at a time (faster, smaller output).
- **Significance:** A larger stride reduces the output size and computation but may miss fine details.

**What is Padding?**

'Padding' means adding a border of extra pixels (usually zeros) around the image before applying the filter.

- Without padding, the filter cannot fully cover the edges, so the output shrinks and edge information is lost.
- With padding, the output can keep the same size as the input, and edge features are preserved.
- **Significance:** Padding controls the output size and protects information at the borders.

**Types of Padding**

- **Valid padding:** No padding; output is smaller.
- **Same padding:** Enough zeros are added so the output size matches the input.

**Why Stride and Padding Matter**

- Together they control the output feature-map size.
- Stride balances speed and detail.
- Padding preserves edge information and controls shrinkage.

**Why is This Important?**

- They shape the network's structure and efficiency.
- They prevent unwanted loss of information.
- They let designers control feature-map dimensions.

**Real-life example:** Applying a 3×3 filter to a 5×5 image with stride 1 and no padding gives a 3×3 output (shrunk, edges under-used). Adding same padding keeps the output 5×5 and preserves edge features; using stride 2 instead shrinks it further for speed. This shows the significance of stride and padding.

**Q10. Illustrate the role and working of the Flatten layer in CNN architecture with suitable example.**

**What is the Flatten Layer?**

'Flatten' means to make something flat. In a CNN, the Flatten Layer converts the multi-dimensional feature maps (2D or 3D grids of numbers) into a single long one-dimensional list (a 1D vector).

It acts as a bridge between the convolution/pooling part and the fully connected part of the network.

**Why the Flatten Layer is Needed**

- Convolution and pooling layers produce 2D/3D feature maps.
- Fully connected (dense) layers need a 1D vector as input.
- The Flatten layer reshapes the data so it can pass from one part to the other.

**How the Flatten Layer Works**

- **Take the feature maps:** After convolution and pooling, we have feature maps (for example, 2×2×3).
- **Unroll into one line:** All the numbers are placed one after another into a single row.
- **Produce a 1D vector:** The result is a long vector ready for the dense layers.

**The Role of the Flatten Layer**

- It connects the feature-extraction part to the decision-making part.
- It keeps all the feature values, just in a new shape.
- It does not change the values - only their arrangement.

**Why is the Flatten Layer Important?**

- Without it, feature maps cannot enter fully connected layers.
- It enables the final classification step.
- It is a simple but essential connector.

**Real-life example:** After convolution and pooling, a CNN has a feature map of size 2×2×2 (eight numbers arranged in grids). The Flatten layer unrolls these eight numbers into a single 1D vector [a, b, c, d, e, f, g, h]. This vector then enters the fully connected layer to decide the class. This illustrates the role and working of the Flatten layer.

**Q11. Discuss how Fully Connected layers combine extracted features to make a final prediction with suitable example.**

**What is a Fully Connected Layer?**

A 'Fully Connected' (dense) layer is a layer where every neuron is connected to every neuron in the previous layer. In a CNN, these layers come at the end, after the convolution, pooling, and flatten steps.

Their job is to take all the extracted features and combine them to make the final decision (prediction).

**Why Fully Connected Layers are Needed**

- Convolution and pooling layers extract features (edges, shapes, parts).
- But someone must combine these features to decide the final answer.
- Fully connected layers do this combining and decision-making.

**How Fully Connected Layers Work (Step by Step)**

- **Take the flattened features:** The 1D vector from the Flatten layer enters the layer.
- **Weigh and combine:** Each feature is multiplied by a learned weight, and all are added, so important features get more influence.
- **Apply activation:** An activation function processes the result.
- **Reach the output layer:** The final fully connected layer produces scores for each class.
- **Apply Softmax (for many classes):** These scores become probabilities, and the highest is chosen.

**How Features are Combined into a Prediction**

- The layer learns which combinations of features indicate which class.
- For example, 'whiskers + pointy ears + fur' together point to 'cat'.

**Why are Fully Connected Layers Important?**

- They make the final classification.
- They combine all extracted features meaningfully.
- They connect feature extraction to the output.

**Real-life example:** A CNN classifying animals has extracted features like 'whiskers', 'pointy ears', and 'four legs'. The fully connected layer weighs and combines these and finds they strongly match 'cat', giving 'cat' the highest probability via Softmax. This shows how fully connected layers combine features to make a final prediction.

**Q12. Describe the key contributions of AlexNet, VGGNet, GoogLeNet, and ResNet.**

**Introduction**

Over the years, several famous CNN architectures advanced the field of deep learning for images. Four important ones are AlexNet, VGGNet, GoogLeNet, and ResNet. Each made a key contribution. Let us describe them.

**AlexNet (2012)**

- It won the 2012 ImageNet competition by a large margin, proving deep CNNs are powerful.
- **Key contributions:** Used ReLU activation for faster training, used Dropout to reduce overfitting, and trained on GPUs.
- It started the modern deep-learning boom.

**VGGNet (2014)**

- It showed that using many small 3×3 filters stacked deeply works very well.
- **Key contributions:** A simple, uniform design that is very deep (16-19 layers), using only small filters.
- It proved that depth improves performance.

**GoogLeNet / Inception (2014)**

- It introduced the 'Inception module', which applies filters of several sizes at the same time.
- **Key contributions:** The Inception module captures features at multiple scales, and it is efficient with fewer parameters.
- It made networks deeper without huge computation.

**ResNet (2015)**

- It introduced 'skip connections' (residual connections) that let information skip layers.
- **Key contributions:** Skip connections solve the vanishing gradient problem, allowing very deep networks (over 100 layers).
- It made extremely deep networks trainable.

**Why are These Important?**

- Each solved a key challenge (depth, overfitting, efficiency, gradients).
- Together they shaped modern computer vision.
- They are milestones in CNN development.

**Real-life example:** For an image-recognition project, AlexNet first proved deep CNNs work, VGGNet showed depth with small filters, GoogLeNet added efficient multi-scale Inception modules, and ResNet's skip connections allowed a 150-layer network to train successfully. This shows the key contributions of these four architectures.

**Q13. Discuss the overall architecture and data flow of a CNN.**

**What is a CNN?**

CNN stands for Convolutional Neural Network - a deep-learning model designed for images. Its architecture is a stack of layers, each doing a specific job, arranged so data flows from the raw image to a final prediction.

**The Overall Architecture and Data Flow (Step by Step)**

- **1. Input layer:** The image enters as a matrix of pixel numbers (for colour images, three channels: R, G, B).
- **2. Convolution layer:** Filters slide over the image to detect features like edges, producing feature maps.
- **3. Activation (ReLU):** ReLU adds non-linearity, keeping positive values and turning negatives to zero.
- **4. Pooling layer:** The feature maps are shrunk (using max or average pooling), reducing size while keeping key features.
- **5. Repeated convolution + pooling:** These layers repeat, learning simple features first and complex features deeper.
- **6. Flatten layer:** The final feature maps are unrolled into a single 1D vector.
- **7. Fully connected layers:** These combine all features to make a decision.
- **8. Output layer (Softmax):** It produces probabilities for each class, and the highest is chosen as the prediction.

**How Data Flows**

- Raw pixels → features → smaller features → combined features → final class.
- Simple patterns are learned early; complex objects are recognised deep in the network.

**Why is This Architecture Important?**

- It extracts features automatically and efficiently.
- Its layered design builds understanding step by step.
- It achieves high accuracy on images.

**Real-life example:** To classify a photo of a dog, the image enters as pixels, convolution and ReLU detect edges, pooling shrinks the maps, deeper layers detect ears and eyes, flatten and fully connected layers combine them, and Softmax outputs 'dog' with the highest probability. This shows the overall architecture and data flow of a CNN.

**Q14. Discuss the role of ReLU activation after the convolution operation.**

**What is ReLU?**

ReLU stands for Rectified Linear Unit. It is an activation function that outputs the value if it is positive, and 0 if it is negative. Its formula is: f(z) = max(0, z).

In a CNN, ReLU is usually applied right after each convolution operation.

**Why ReLU is Used After Convolution**

- The convolution operation is a linear calculation (multiply and add).
- Stacking only linear operations cannot learn complex patterns.
- ReLU adds non-linearity, letting the network learn complex, curved patterns.

**The Role of ReLU After Convolution**

- **Adds non-linearity:** It allows the CNN to model complex relationships in images.
- **Removes negative values:** It turns negative feature-map values into 0, keeping only strong, positive activations.
- **Speeds up training:** It is simple to compute, so training is fast.
- **Avoids vanishing gradients:** Unlike sigmoid, ReLU does not squash large values, so gradients flow well in deep networks.

**How It Works on a Feature Map**

- After convolution, the feature map may contain positive and negative numbers.
- ReLU keeps the positives and sets negatives to zero.
- This highlights where features are strongly present.

**Why is ReLU Important?**

- Without it, deep CNNs could not learn complex features.
- It keeps training fast and stable.
- It is the most popular activation in CNNs.

**Real-life example:** After a convolution filter detects edges, its feature map has values like [−3, 5, −1, 8]. ReLU converts these to [0, 5, 0, 8], keeping only the strong edge signals and adding non-linearity. This lets the CNN build complex features in later layers - showing the role of ReLU after convolution.

**Q15. Demonstrate the working principle of the pooling layer in a CNN.**

**What is a Pooling Layer?**

The 'Pooling Layer' is a step in a CNN that reduces the size of a feature map by summarising small regions into single values. It keeps the important information while making the data smaller and the network more efficient.

**The Working Principle of Pooling (Step by Step)**

- **Step 1 - Choose a window size:** A small window is chosen, usually 2×2.
- **Step 2 - Choose a stride:** The window moves by a set number of pixels (often 2), so windows do not overlap.
- **Step 3 - Slide the window:** The window moves across the feature map, region by region.
- **Step 4 - Summarise each region:** For each window, pooling keeps one value:
  - Max Pooling keeps the largest value.
  - Average Pooling keeps the mean value.
- **Step 5 - Build the smaller map:** These summary values form a new, smaller feature map.

**Effect of Pooling**

- The feature map becomes smaller (for example, 4×4 becomes 2×2).
- Important features are preserved; minor details are dropped.

**Benefits of Pooling**

- Reduces computation and memory.
- Reduces overfitting.
- Makes the network robust to small position shifts.

**Why is Pooling Important?**

- It keeps CNNs efficient.
- It focuses on the strongest features.
- It improves generalization.

**Real-life example:** Take a 4×4 feature map. Using 2×2 max pooling with stride 2, the top-left window [[1, 3], [2, 4]] becomes 4 (the maximum). Repeating for all windows turns the 4×4 map into a 2×2 map, keeping the strongest features. This demonstrates the working principle of the pooling layer.

**Q16. Discuss how CNNs perform hierarchical feature extraction from simple edges to complete objects.**

**What is Hierarchical Feature Extraction?**

'Hierarchical' means arranged in levels, from simple to complex. So Hierarchical Feature Extraction means a CNN learns features in stages - starting with very simple patterns and gradually combining them into complete objects, layer by layer.

It is like building with blocks: small pieces combine into bigger structures.

**How CNNs Extract Features Hierarchically (Layer by Layer)**

- **Early layers - simple features:** The first convolution layers detect basic patterns like edges, lines, and corners.
- **Middle layers - shapes and textures:** The next layers combine edges into shapes, curves, and textures (like eyes or wheels).
- **Deeper layers - object parts:** Further layers combine shapes into recognisable parts (like a face's nose or a car's door).
- **Final layers - complete objects:** The deepest layers combine parts into whole objects (a full face or a full car).

**Why the Hierarchy Works**

- Each layer builds on the features from the layer before it.
- Simple features are reused to form complex ones.
- This mirrors how humans recognise things - from details to the whole.

**The Role of Depth**

- More layers allow more levels of combination.
- That is why deep networks recognise complex objects well.

**Why is This Important?**

- It lets CNNs understand images from the ground up.
- It enables recognition of complex objects.
- It removes the need for manual feature design.

**Real-life example:** A CNN recognising a car first detects edges (early layers), then combines them into shapes like circles (wheels) and rectangles (windows) in middle layers, then into parts like doors, and finally into a complete car in deep layers. This step-by-step build-up shows how CNNs perform hierarchical feature extraction.

**UNIT III**

**Q1. Define sequence data and explain why the order of elements is important, with suitable examples.**

**What is Sequence Data?**

'Sequence' means a series of things arranged one after another in a particular order. So Sequence Data means data where the elements come in a specific order, and that order carries meaning. Changing the order changes the meaning.

Examples include sentences (words in order), time-series (values over time), music (notes in order), and DNA (bases in order).

**Why the Order of Elements is Important**

- **Order carries meaning:** The same elements in a different order can mean something completely different.
- **Context depends on order:** Each element is understood in relation to the ones before and after it.
- **Prediction needs order:** To predict the next element, the model must know what came before.

**Examples Showing the Importance of Order**

- **Sentences:** 'Dog bites man' and 'Man bites dog' use the same words but mean opposite things because of order.
- **Time-series:** Stock prices over days only make sense in time order; shuffling the days destroys the trend.
- **Weather:** Temperature readings across a week show a pattern only if kept in order.

**Why Ordinary Networks Struggle**

- Normal (feedforward) networks treat inputs independently, ignoring order.
- Sequence data needs special models (like RNNs) that remember previous elements.

**Why is This Important?**

- Many real problems involve ordered data.
- Understanding order is key to language, time-series, and more.
- It explains why RNNs and LSTMs were created.

**Real-life example:** Consider predicting the next word in 'I am going to the ...'. The order of the earlier words tells the model a place-word like 'market' is likely next. If the words were shuffled to 'the to going am I', the meaning is lost and prediction fails. This shows why order matters in sequence data.

**Q2. Explain the basic equations used in an RNN with suitable example.**

**What is an RNN?**

RNN stands for Recurrent Neural Network. It is a network designed for sequence data. Its special feature is a hidden state (a memory) that carries information from previous steps to the current step, so it can understand order and context.

**The Basic Equations of an RNN**

An RNN works step by step through the sequence. At each time step 't', it uses two main equations:

- **Hidden state equation:** hₜ = f(Wₓ · xₜ + Wₕ · hₜ₋₁ + b)
  - xₜ is the current input.
  - hₜ₋₁ is the previous hidden state (memory).
  - Wₓ and Wₕ are weight matrices.
  - b is the bias, and f is an activation function (usually tanh).
  - This combines the new input with the past memory to update the memory.

- **Output equation:** yₜ = g(Wy · hₜ + c)
  - hₜ is the current hidden state.
  - Wy is the output weight, and c is the output bias.
  - g is an activation function (like Softmax).
  - This produces the output from the current memory.

**What the Equations Mean (in Simple Words)**

- The hidden state equation blends 'what I see now' with 'what I remember'.
- The output equation turns the updated memory into a prediction.
- The same weights are used at every step (shared weights).

**Why are These Equations Important?**

- They show how an RNN remembers and uses context.
- They enable processing of ordered data.
- They are the foundation for LSTM and GRU.

**Real-life example:** Predicting the next word in 'I love ...': at each step the RNN takes the current word xₜ and the previous memory hₜ₋₁, updates the hidden state hₜ, and outputs yₜ (the likely next word, say 'you'). The equations combine input and memory to make this possible - showing how RNN equations work.

**Q3. Assess the four steps of the BPTT algorithm.**

**What is BPTT?**

BPTT stands for Backpropagation Through Time. It is the method used to train an RNN. Because an RNN processes a sequence step by step and shares its weights across all steps, the normal backpropagation is extended 'through time' - across all the steps of the sequence.

**Why BPTT is Needed**

- An RNN's output at each step depends on earlier steps.
- To learn, the error must be sent back through all these time steps.
- BPTT handles this time-based error flow.

**The Four Steps of BPTT**

- **Step 1 - Forward pass through time:** The RNN processes the whole input sequence step by step, calculating the hidden states and outputs at every time step, and storing them.
- **Step 2 - Calculate the loss:** The outputs are compared with the correct answers, and the total error (loss) across all time steps is computed.
- **Step 3 - Backward pass through time:** The error is sent backward from the last time step to the first, calculating gradients (how much each weight contributed to the error) at every step using the chain rule.
- **Step 4 - Update the weights:** The gradients from all time steps are added together (because weights are shared), and the shared weights are updated using an optimizer like Gradient Descent.

**Assessment of BPTT**

- **Strength:** It correctly trains RNNs by accounting for time dependencies.
- **Weakness:** For long sequences, it is slow and memory-heavy, and can suffer vanishing or exploding gradients.
- **Solution:** Truncated BPTT and models like LSTM address these issues.

**Why is BPTT Important?**

- It is the core learning method for RNNs.
- It links errors across time to update shared weights.
- Understanding its limits explains why LSTM/GRU exist.

**Real-life example:** Training an RNN to predict the next word in a sentence, BPTT runs the forward pass across all words, computes the total error, sends it backward through every word, and updates the shared weights. Over many sentences, the RNN learns. This assesses the four steps of BPTT.

**Q4. Describe the three gates of an LSTM and their roles.**

**What is an LSTM?**

LSTM stands for Long Short-Term Memory. It is a special type of RNN designed to remember information over long sequences, solving the basic RNN's problem of forgetting distant information (the vanishing gradient problem).

It uses a memory cell and three 'gates' that control the flow of information.

**What are Gates?**

'Gates' are small structures that decide what information to keep, remove, or output. Each gate uses a sigmoid function that outputs values between 0 (block completely) and 1 (allow fully).

**The Three Gates of an LSTM and Their Roles**

- **1. Forget Gate:** It decides which old information from the memory should be thrown away. It looks at the previous output and current input and outputs a value between 0 and 1 for each piece of memory (0 = forget, 1 = keep).
- **2. Input Gate:** It decides which new information should be added to the memory. It selects the useful new details from the current input to store.
- **3. Output Gate:** It decides what part of the memory should be given as the output at the current step. It controls what the LSTM passes on to the next step and as the result.

**How They Work Together**

- The forget gate clears out unneeded old memory.
- The input gate adds important new memory.
- The output gate decides what to reveal.
- Together they let the LSTM remember what matters over long sequences.

**Why are LSTM Gates Important?**

- They solve the forgetting problem of basic RNNs.
- They enable learning of long-term dependencies.
- They power translation, speech, and text tasks.

**Real-life example:** Reading the sentence 'I grew up in France... so I speak fluent French', the forget gate discards unimportant words, the input gate stores the key fact 'France', and the output gate later uses it to predict 'French'. The three gates working together let the LSTM remember long-distance information - showing their roles.

**Q5. Assess the limitations of feedforward networks for sequence data.**

**What is a Feedforward Network?**

A 'Feedforward Network' is a basic neural network where data flows in one direction - from input to output - with no memory of previous inputs. Each input is treated independently.

While good for fixed, independent data (like a single image), it struggles with sequence data (like sentences or time-series).

**What is Sequence Data (Recap)?**

Sequence data has elements in a meaningful order, where each element depends on the ones before it - for example, words in a sentence.

**Limitations of Feedforward Networks for Sequence Data**

- **No memory:** They cannot remember previous inputs, so they lose context from earlier elements.
- **Ignore order:** They treat each input independently, missing the crucial order of the sequence.
- **Fixed input size:** They need a fixed-size input, but sequences vary in length (sentences differ in length).
- **No sharing across positions:** They do not reuse learning across time steps, unlike RNNs which share weights.
- **Cannot handle dependencies:** They cannot link a word at the start to one at the end.

**Impact of These Limitations**

- They perform poorly on language, speech, and time-series tasks.
- They cannot predict the next element based on prior context.
- They miss patterns that depend on order.

**Why RNNs are the Solution**

- RNNs add a hidden state (memory) to remember previous steps.
- They handle variable-length sequences and share weights across time.

**Why is This Assessment Important?**

- It explains why special models (RNN, LSTM) were created.
- It highlights the importance of memory and order.
- It guides the right model choice for sequence tasks.

**Real-life example:** To predict the next word in 'The sky is ...', a feedforward network sees only the current input with no memory of earlier words, so it cannot use context to predict 'blue'. An RNN remembers the earlier words and predicts correctly. This assesses the limitations of feedforward networks for sequence data.

**Q6. Describe the role of shared weights in an RNN.**

**What are Shared Weights?**

In an RNN, 'Shared Weights' means the same set of weights (and biases) is used at every time step as the network processes the sequence. Instead of having different weights for each position, the RNN reuses one set across the whole sequence.

**How Shared Weights Work**

- The RNN processes the sequence step by step.
- At each step, it applies the same weight matrices (Wₓ, Wₕ, Wy) to the input and hidden state.
- Only the inputs and the hidden state change from step to step; the weights stay the same.

**The Role and Benefits of Shared Weights**

- **Fewer parameters:** Reusing weights means far fewer values to learn, making the network smaller and faster to train.
- **Handles any length:** Because the same weights are reused, the RNN can process sequences of any length.
- **Consistency across positions:** A pattern learned at one position is recognised at any other position (like recognising a word wherever it appears).
- **Generalization:** It helps the network generalise across the sequence.

**How Shared Weights Affect Training**

- During BPTT, the gradients from all time steps are added together to update the single shared weight set.
- This links learning across the entire sequence.

**Why are Shared Weights Important?**

- They make RNNs efficient and compact.
- They allow variable-length input.
- They enable position-independent pattern learning.

**Real-life example:** An RNN reading a sentence uses the same weights for the 1st word, the 5th word, and the 20th word. So if it learns to recognise the word 'not' as important, it recognises it wherever it appears in any sentence, of any length. This shows the role of shared weights in an RNN.

**Q7. Differentiate between Full BPTT and Truncated BPTT.**

**What is BPTT (Recap)?**

BPTT stands for Backpropagation Through Time - the method used to train RNNs by sending the error backward across the time steps of a sequence. There are two versions: Full BPTT and Truncated BPTT. Let us compare them.

**What is Full BPTT?**

Full BPTT sends the error backward through the entire sequence, from the last step all the way to the first.

- It considers all time steps when updating weights.
- It captures long-range dependencies fully.
- But for long sequences it is slow and uses a lot of memory.

**What is Truncated BPTT?**

Truncated BPTT breaks the long sequence into smaller chunks and sends the error backward only within each chunk (a limited number of steps).

- It processes a few steps at a time, not the whole sequence.
- It is faster and uses much less memory.
- But it may miss very long-range dependencies.

**Key Differences**

- **Backward range:** Full BPTT goes through the whole sequence; Truncated goes through a fixed short window.
- **Speed:** Full is slow; Truncated is fast.
- **Memory:** Full is memory-heavy; Truncated is memory-light.
- **Long dependencies:** Full captures them fully; Truncated may miss the longest ones.
- **Use:** Full for short sequences; Truncated for long sequences.

**Why is This Comparison Important?**

- Long sequences make Full BPTT impractical.
- Truncated BPTT makes training long sequences possible.
- The choice balances accuracy and efficiency.

**Real-life example:** Training an RNN on a very long document, Full BPTT would try to backpropagate through thousands of words - slow and memory-heavy. Truncated BPTT instead processes 20 words at a time, updating weights within each chunk, making training fast and practical. This differentiates Full and Truncated BPTT.

**Q8. Explain the vanishing gradient problem in RNNs.**

**What is a Gradient (Recap)?**

A 'gradient' tells the network how much to adjust each weight to reduce error. During training (backpropagation), gradients are passed backward through the layers or time steps to update the weights.

**What is the Vanishing Gradient Problem?**

The 'Vanishing Gradient Problem' happens when the gradients become extremely small (close to zero) as they are passed backward through many time steps. When gradients vanish, the early layers or early time steps learn almost nothing.

In simple words, the network 'forgets' information from far back because the learning signal fades away.

**Why It Happens in RNNs**

- RNNs process long sequences step by step.
- During BPTT, gradients are multiplied repeatedly at each step.
- If these multiplied values are less than 1, they shrink rapidly toward zero after many steps.
- So the influence of early inputs disappears.

**Effects of the Vanishing Gradient Problem**

- The RNN cannot learn long-term dependencies.
- Early words in a long sentence are effectively forgotten.
- Training becomes slow and ineffective for long sequences.

**Solutions to the Problem**

- **LSTM and GRU:** They use gates to preserve important information over long sequences.
- **ReLU activation:** Helps reduce shrinking compared with sigmoid/tanh.
- **Better initialization and gradient techniques.**

**Why is This Important?**

- It explains a major weakness of basic RNNs.
- It motivated the creation of LSTM and GRU.
- It affects tasks needing long-term memory.

**Real-life example:** An RNN reading 'I grew up in France ... [many words] ... so I speak fluent ___' should predict 'French'. But due to the vanishing gradient, the signal from 'France' fades over the long gap, so the basic RNN forgets it. An LSTM solves this with its gates. This explains the vanishing gradient problem in RNNs.

**Q9. Compare and contrast the four RNN input-output architectures.**

**Introduction**

RNNs are flexible and can be arranged in different ways depending on how many inputs and outputs are needed. There are four main input-output architectures. Let us compare them.

**1. One-to-One**

- One input produces one output.
- It is the simplest form, like a standard neural network (no real sequence).
- Example: a single image classified into one label.

**2. One-to-Many**

- One input produces a sequence of outputs.
- Example: image captioning - one image produces a sentence (many words).

**3. Many-to-One**

- A sequence of inputs produces one output.
- Example: sentiment analysis - a whole sentence (many words) gives one label (positive/negative).

**4. Many-to-Many**

- A sequence of inputs produces a sequence of outputs.
- Two forms exist: equal length (input and output aligned) and different length (encoder-decoder).
- Example: machine translation - an input sentence produces an output sentence.

**Comparison Summary**

- **One-to-One:** single input, single output (no sequence).
- **One-to-Many:** single input, sequence output (captioning).
- **Many-to-One:** sequence input, single output (sentiment).
- **Many-to-Many:** sequence input, sequence output (translation).

**Why is This Comparison Important?**

- Different tasks need different structures.
- Choosing the right one fits the problem.
- It shows the flexibility of RNNs.

**Real-life example:** For sentiment analysis of a review, a Many-to-One RNN reads many words and outputs one label. For translating that review, a Many-to-Many RNN reads the sentence and outputs a translated sentence. For captioning a photo of the product, One-to-Many is used. This compares the four RNN input-output architectures.

**Q10. Illustrate the unrolling of an RNN through time.**

**What is an RNN (Recap)?**

An RNN is a network for sequence data that uses a hidden state (memory) and a loop - it feeds its output back into itself for the next step. This loop makes it recurrent.

**What is Unrolling?**

'Unrolling' (or unfolding) means drawing out the RNN's loop across time, showing it as a chain of copies - one copy for each time step of the sequence. Instead of one looping cell, we see the same cell repeated for step 1, step 2, step 3, and so on.

**Why We Unroll an RNN**

- The loop is hard to visualise and train directly.
- Unrolling shows how the same cell processes each element in order.
- It makes it clear how information (the hidden state) flows from one step to the next.
- It is essential for understanding BPTT (training through time).

**How Unrolling Works (Step by Step)**

- **Step 1:** Take input x₁, combine with the initial hidden state h₀ to produce h₁ and output y₁.
- **Step 2:** Take input x₂ and the previous hidden state h₁ to produce h₂ and output y₂.
- **Step 3:** Take input x₃ and h₂ to produce h₃ and output y₃.
- And so on for the whole sequence.

**The Key Point**

- The same weights are used in every unrolled copy (shared weights).
- The hidden state carries memory forward through the chain.

**Why is Unrolling Important?**

- It reveals how RNNs handle sequences.
- It shows the flow of memory across time.
- It is the basis for BPTT.

**Real-life example:** For the sentence 'I love NLP' with three words, the RNN is unrolled into three copies: the first processes 'I' (h₁), the second processes 'love' using h₁ (h₂), and the third processes 'NLP' using h₂ (h₃). The hidden state carries meaning forward through the chain. This illustrates the unrolling of an RNN through time.

**Q11. Examine the exploding gradient problem in RNNs.**

**What is a Gradient (Recap)?**

A 'gradient' tells the network how much to change each weight to reduce error. During training, gradients are passed backward through the time steps of an RNN to update the weights.

**What is the Exploding Gradient Problem?**

The 'Exploding Gradient Problem' happens when the gradients become extremely large as they are passed backward through many time steps. Instead of shrinking (as in vanishing gradients), they grow bigger and bigger.

When gradients explode, the weight updates become huge, and the network becomes unstable.

**Why It Happens in RNNs**

- During BPTT, gradients are multiplied repeatedly at each time step.
- If these multiplied values are greater than 1, they grow rapidly across many steps.
- After many steps, the gradient becomes enormous.

**Effects of the Exploding Gradient Problem**

- **Unstable training:** The weights jump around wildly and never settle.
- **Very large weights:** The model's numbers may become too big to handle (overflow, NaN values).
- **Poor learning:** The network fails to converge to a good solution.

**Solutions to the Problem**

- **Gradient Clipping:** The most common fix - limit (clip) the gradient to a maximum value before updating the weights.
- **Smaller learning rate:** Take smaller steps to reduce the damage of large gradients.
- **Better initialization:** Set starting weights carefully.
- **LSTM/GRU:** Their gated design helps control gradient flow.

**Why is This Important?**

- It is a major training problem for RNNs.
- Gradient clipping makes stable training possible.
- Understanding it helps train deep sequence models.

**Real-life example:** While training an RNN on long text, the gradients suddenly grow to huge values, and the loss jumps to infinity (NaN) - a sign of exploding gradients. Applying gradient clipping limits the gradient size, and training becomes stable again. This examines the exploding gradient problem in RNNs.

**Q12. Differentiate between reset and update gates of a GRU.**

**What is a GRU?**

GRU stands for Gated Recurrent Unit. It is a simplified type of RNN (similar to LSTM) that uses gates to control information flow and remember important details over long sequences. Unlike LSTM's three gates, the GRU uses just two: the reset gate and the update gate. Let us compare them.

**What is the Reset Gate?**

The 'Reset Gate' decides how much of the past information (previous hidden state) to forget when computing the new candidate memory.

- If the reset gate is near 0, the GRU ignores the past and focuses on the current input.
- If it is near 1, the past is used fully.
- **Role:** It controls how much old memory to drop for the new content.

**What is the Update Gate?**

The 'Update Gate' decides how much of the past information to keep versus how much new information to add to the final hidden state.

- If the update gate is near 1, most of the old memory is kept.
- If it is near 0, mostly new information is used.
- **Role:** It balances old memory and new information for the output.

**Key Differences**

- **Reset gate:** controls how much past to forget when forming new candidate memory.
- **Update gate:** controls how much old memory to keep versus new to add.
- **Focus:** Reset deals with the candidate content; Update deals with the final blend.
- **Effect:** Reset handles short-term relevance; Update handles long-term retention.

**Why are These Gates Important?**

- Together they let the GRU remember important information and forget the rest.
- They solve the vanishing gradient problem like the LSTM, but with fewer parts.
- They make the GRU efficient and effective.

**Real-life example:** Reading a long review, the reset gate lets the GRU drop irrelevant earlier words when forming new memory, while the update gate keeps the crucial sentiment word 'excellent' in memory to the end. The two gates working differently let the GRU manage memory well - showing the difference between reset and update gates.

**Q13. Illustrate how an RNN hidden state stores previous information.**

**What is a Hidden State?**

In an RNN, the 'Hidden State' is a set of numbers that acts as the network's memory. It stores a summary of the information seen so far in the sequence and is passed from one time step to the next.

It is the reason an RNN can understand context and order.

**How the Hidden State Stores Previous Information (Step by Step)**

- **Start:** The hidden state begins with an initial value (usually zeros), h₀.
- **At each step:** The RNN combines the current input (xₜ) with the previous hidden state (hₜ₋₁) to produce a new hidden state (hₜ). The equation is: hₜ = f(Wₓ · xₜ + Wₕ · hₜ₋₁ + b).
- **Carrying memory forward:** This new hidden state hₜ contains a blend of the current input and everything remembered before.
- **Passing on:** hₜ is passed to the next step, so memory flows through the whole sequence.

**Why the Hidden State is Like Memory**

- It is updated at every step, absorbing new information.
- It keeps a compressed record of all previous inputs.
- It lets the RNN use past context to understand the present and predict the future.

**Limitation**

- Over very long sequences, basic RNN hidden states can forget distant information (vanishing gradient). LSTM/GRU improve this.

**Why is This Important?**

- The hidden state is what makes RNNs 'remember'.
- It enables context understanding in sequences.
- It is the core idea behind sequence modelling.

**Real-life example:** Reading 'I am very happy today', the RNN updates its hidden state at each word: after 'I am very', the hidden state remembers a positive build-up, so when 'happy' arrives, the context is understood. The hidden state carried the earlier words forward - illustrating how it stores previous information.

**Q14. Explain the purpose of BPTT in RNN training.**

**What is BPTT?**

BPTT stands for Backpropagation Through Time. It is the training method for RNNs. Because an RNN processes a sequence step by step and shares its weights across all steps, BPTT extends ordinary backpropagation 'through time' - across every step of the sequence.

**The Purpose of BPTT in RNN Training**

- **To calculate the error's effect across time:** BPTT works out how much each weight contributed to the error at every time step of the sequence.
- **To update shared weights correctly:** Since the same weights are reused at all steps, BPTT gathers the error signals from all steps and combines them to update the single shared weight set.
- **To learn time dependencies:** It lets the RNN learn how earlier inputs affect later outputs, capturing the order and context of the sequence.
- **To reduce the loss:** By adjusting weights based on the total error over time, it makes the RNN's predictions more accurate.

**How BPTT Achieves This (Briefly)**

- Do a forward pass through the whole sequence, storing states and outputs.
- Calculate the total error across all time steps.
- Send the error backward through time, computing gradients at each step.
- Add the gradients and update the shared weights.

**Why BPTT is Essential**

- Without it, the RNN could not learn from sequences.
- It links errors across time, which normal backpropagation cannot.
- It trains the shared weights that make RNNs work.

**Limitation**

- For long sequences it is slow and can cause vanishing/exploding gradients, which Truncated BPTT and LSTM/GRU address.

**Why is This Important?**

- BPTT is the engine of RNN learning.
- It enables understanding of ordered data.
- It underlies all sequence-model training.

**Real-life example:** To train an RNN to predict the next word in sentences, BPTT runs each sentence forward, measures the total prediction error, sends it backward through every word, and updates the shared weights. Over many sentences, the RNN learns language patterns. This explains the purpose of BPTT in RNN training.

**Q15. Compare LSTM and GRU based on their key features.**

**Introduction**

LSTM and GRU are both advanced types of RNNs that use gates to remember important information over long sequences and to solve the vanishing gradient problem. They are similar but differ in structure. Let us compare them.

**What is LSTM?**

LSTM stands for Long Short-Term Memory. It uses a separate memory cell and three gates: the forget gate, the input gate, and the output gate.

- It has more parts, making it powerful but more complex.
- It handles very long dependencies very well.

**What is GRU?**

GRU stands for Gated Recurrent Unit. It is a simpler version that uses two gates: the reset gate and the update gate, and has no separate memory cell.

- It has fewer parts, making it simpler and faster.
- It performs almost as well as LSTM on many tasks.

**Comparison Based on Key Features**

- **Number of gates:** LSTM has three; GRU has two.
- **Memory cell:** LSTM has a separate cell state; GRU does not (it merges memory into the hidden state).
- **Complexity:** LSTM is more complex; GRU is simpler.
- **Speed:** GRU trains faster (fewer parameters); LSTM is slower.
- **Data needs:** GRU works well on smaller data; LSTM can be better on large, complex data.
- **Performance:** Both are strong; results are often similar.

**When to Use Which**

- Use GRU for faster training and smaller data.
- Use LSTM for very long sequences and complex tasks.

**Why is This Comparison Important?**

- Both solve the RNN memory problem.
- The choice balances speed and power.
- Understanding them guides model selection.

**Real-life example:** For a quick sentiment-analysis model on a small dataset, a GRU is chosen for speed and simplicity. For a complex machine-translation system on huge data, an LSTM is chosen for its stronger long-term memory. Both use gates to remember key information - showing the comparison of LSTM and GRU.

**UNIT IV**

**Q1. Discuss the working of the Generator in a GAN and describe how it generates realistic data from random noise.**

**What is a GAN?**

GAN stands for Generative Adversarial Network. It is a deep-learning model made of two networks that compete with each other: the Generator and the Discriminator. Together they learn to create realistic fake data (like images).

**What is the Generator?**

The 'Generator' is the part of a GAN whose job is to create new, fake data that looks real. It starts from random noise (meaningless random numbers) and transforms it into realistic data, such as a fake but believable image.

**How the Generator Works (Step by Step)**

- **Step 1 - Start with random noise:** The generator takes a vector of random numbers (called the latent vector or noise) as input.
- **Step 2 - Pass through layers:** This noise passes through several neural network layers that gradually shape it.
- **Step 3 - Produce fake data:** The output is a piece of generated data, for example a fake image.
- **Step 4 - Get feedback:** The discriminator judges whether this output looks real or fake.
- **Step 5 - Improve:** Based on the feedback, the generator adjusts its weights to make more realistic data next time.

**How It Learns to Make Realistic Data**

- The generator tries to fool the discriminator into thinking its fakes are real.
- The discriminator gives feedback on how convincing the fakes are.
- Over many rounds, the generator improves until its fakes look genuinely real.
- This competition (adversarial training) drives the generator to high quality.

**Why is the Generator Important?**

- It is the creative part that produces new data.
- It powers image generation, art, and data creation.
- It learns to model the real data distribution.

**Real-life example:** To create fake human faces, the generator starts with random noise and passes it through its layers to produce a face image. At first the faces look strange, but as the discriminator gives feedback, the generator improves until it produces realistic faces that do not belong to any real person. This shows how the generator turns random noise into realistic data.

**Q2. Illustrate the self-attention mechanism in Transformers.**

**What is Self-Attention?**

'Self' means within the same sentence, and 'Attention' means focusing on important parts. So Self-Attention is a mechanism that lets each word in a sentence look at all the other words and decide which ones are most important for understanding it.

It is the core idea that makes Transformers powerful.

**Why Self-Attention is Needed**

- To understand a word, we must know its context (the other words).
- Self-attention lets every word gather information from all other words at once.
- This captures relationships even between far-apart words.

**How Self-Attention Works (Step by Step)**

- **Step 1 - Create Query, Key, and Value:** For each word, three vectors are made - a Query (Q), a Key (K), and a Value (V).
- **Step 2 - Compare words:** Each word's Query is compared with every word's Key to get attention scores (how relevant each other word is).
- **Step 3 - Turn scores into weights:** The scores are passed through Softmax to become weights that add up to 1.
- **Step 4 - Weighted sum of Values:** Each word's new representation is a weighted sum of all the Value vectors, using these weights.
- **Step 5 - Output:** The result is a context-aware representation of each word.

**In Simple Terms**

- Each word asks (Query) 'which words matter to me?'
- It checks all the Keys, gives more weight to relevant words, and blends their Values.

**Why is Self-Attention Important?**

- It captures context and word relationships.
- It handles long-distance links well.
- It allows fast, parallel processing, unlike RNNs.

**Real-life example:** In 'The animal did not cross the road because it was tired', self-attention lets the word 'it' compare with all words and give a high attention weight to 'animal', correctly linking them. This context-aware linking illustrates the self-attention mechanism in Transformers.

**Q3. Explain the architecture of BERT.**

**What is BERT?**

BERT stands for Bidirectional Encoder Representations from Transformers. It is a powerful NLP model made by Google. Its key strength is that it understands a word using context from both sides - the words before AND after it.

**The Architecture of BERT**

- **Based on Transformer encoders:** BERT is built by stacking many Transformer encoder layers (it uses only the encoder part, not the decoder).
- **Input embeddings:** BERT's input combines three embeddings for each token:
  - Token embeddings (the word itself),
  - Segment embeddings (which sentence the word belongs to),
  - Position embeddings (the word's position).
- **Special tokens:** It adds a [CLS] token at the start (used for classification) and a [SEP] token to separate sentences.
- **Stacked encoder layers:** Each layer uses multi-head self-attention and a feed-forward network to build deep, context-aware representations.
- **Bidirectional attention:** Unlike older models, BERT looks at both left and right context at the same time.
- **Output:** For each token, BERT outputs a rich vector that reflects its meaning in context.

**Two Common Sizes**

- **BERT-Base:** 12 encoder layers.
- **BERT-Large:** 24 encoder layers (more powerful).

**How BERT is Trained (Briefly)**

- **Masked Language Model:** Some words are hidden, and BERT learns to predict them from context.
- **Next Sentence Prediction:** BERT learns whether one sentence logically follows another.

**Why is BERT's Architecture Important?**

- Bidirectional context gives deep understanding.
- It set records on many NLP tasks.
- It can be fine-tuned for specific tasks.

**Real-life example:** For the word 'bank' in 'I sat by the river bank', BERT's stacked encoders and bidirectional self-attention read both 'river' (left) and the sentence context to understand 'bank' means a riverside, not a money bank. This shows how BERT's architecture produces context-aware understanding.

**Q4. Define Deep Reinforcement Learning and describe its process.**

**What is Deep Reinforcement Learning?**

Let us break it down. 'Reinforcement Learning' is a type of machine learning where an agent learns by trial and error, receiving rewards for good actions and penalties for bad ones. 'Deep' means using deep neural networks. So Deep Reinforcement Learning (Deep RL) means combining reinforcement learning with deep neural networks so an agent can learn complex tasks from high-dimensional data (like images).

**Key Terms in Deep RL**

- **Agent:** The learner or decision-maker.
- **Environment:** The world the agent interacts with.
- **State:** The current situation of the environment.
- **Action:** A move the agent can make.
- **Reward:** Feedback (positive or negative) after an action.
- **Policy:** The agent's strategy for choosing actions.

**The Process of Deep Reinforcement Learning (Step by Step)**

- **Step 1 - Observe the state:** The agent looks at the current state of the environment.
- **Step 2 - Choose an action:** Using a deep neural network (its policy), the agent selects an action.
- **Step 3 - Receive a reward:** The environment gives a reward and moves to a new state.
- **Step 4 - Learn from feedback:** The agent updates its neural network to prefer actions that led to higher rewards.
- **Step 5 - Repeat:** This loop repeats many times, and the agent gradually learns the best strategy.

**The Role of Deep Neural Networks**

- They let the agent handle complex inputs like images or game screens.
- They approximate the value of actions or the best policy.

**Why is Deep RL Important?**

- It solves complex decision-making problems.
- It powers game-playing AI, robotics, and automation.
- It learns directly from experience.

**Real-life example:** In a video game, a Deep RL agent observes the game screen (state), chooses a move (action), and receives points (reward). Using a deep neural network, it learns over many games which moves earn the most points, eventually playing expertly. This defines Deep RL and shows its process.

**Q5. Illustrate the working of the discriminator in a GAN with example.**

**What is a GAN (Recap)?**

GAN stands for Generative Adversarial Network. It has two competing networks: the Generator (which creates fake data) and the Discriminator (which judges data). They train together, each improving the other.

**What is the Discriminator?**

The 'Discriminator' is the part of a GAN that acts like a judge or detective. Its job is to look at a piece of data and decide whether it is real (from the actual dataset) or fake (created by the generator).

It outputs a probability - close to 1 means 'real', close to 0 means 'fake'.

**How the Discriminator Works (Step by Step)**

- **Step 1 - Receive data:** The discriminator is given a piece of data - either a real example or a fake one from the generator.
- **Step 2 - Analyse it:** It passes the data through its neural network layers to study its features.
- **Step 3 - Make a judgement:** It outputs a probability of the data being real.
- **Step 4 - Compare with the truth:** Its judgement is checked against whether the data was actually real or fake.
- **Step 5 - Learn:** It updates its weights to get better at telling real from fake.

**The Adversarial Relationship**

- The discriminator tries to catch the generator's fakes.
- The generator tries to fool the discriminator.
- This competition pushes both to improve until the fakes look real.

**Why is the Discriminator Important?**

- It gives feedback that trains the generator.
- It sets the quality bar for fake data.
- Without it, the generator could not learn to be realistic.

**Real-life example:** A generator creates a fake face image. The discriminator examines it and, early in training, easily labels it 'fake' (probability 0.1). It also correctly labels real faces as 'real'. As training continues, the generator improves, and the discriminator must work harder to tell fakes from real faces. This illustrates the working of the discriminator in a GAN.

**Q6. Discuss the role of positional encoding in Transformers.**

**Why Positional Encoding is Needed**

Transformers read all the words of a sentence at the same time (in parallel), not one by one. This makes them fast, but creates a problem: the model does not naturally know the order of the words. Yet order is very important - 'dog bites man' differs from 'man bites dog'.

**What is Positional Encoding?**

'Positional' means related to position, and 'Encoding' means turning information into numbers. So Positional Encoding is a method that adds information about each word's position in the sentence to its word embedding.

- Each position gets a unique numerical pattern.
- This pattern is added to the word's vector.
- Now the vector carries both meaning and position.

**How It Works (Briefly)**

- Positions (1st, 2nd, 3rd word...) are given encodings, often created using sine and cosine functions of different frequencies.
- Each position's encoding is added to the corresponding word embedding.
- The combined vector enters the Transformer.

**The Role of Positional Encoding**

- **Provides word order:** It tells the Transformer which word comes where.
- **Preserves sequence structure:** It restores the order lost by parallel processing.
- **Helps attention:** It lets attention consider the relative positions of words.

**Why is Positional Encoding Important?**

- Without it, the Transformer would treat a sentence as an unordered bag of words.
- It restores the crucial information of order.
- It helps the model understand meaning correctly.

**Real-life example:** For 'The cat chased the dog' versus 'The dog chased the cat', the same words appear but in different order. Positional encoding gives each word a position pattern, so the Transformer knows which noun came first and understands the two sentences differently. This shows the role of positional encoding in Transformers.

**Q7. Describe the training process of BERT.**

**What is BERT (Recap)?**

BERT stands for Bidirectional Encoder Representations from Transformers. It understands words using context from both sides. Before it can be used, BERT is 'pre-trained' on huge amounts of text using two special tasks.

**The Two Pre-training Tasks of BERT**

- **1. Masked Language Model (MLM):** Some words in the input are randomly hidden (masked), about 15% of them. BERT must predict these hidden words using the surrounding context (both left and right). This teaches BERT deep, bidirectional understanding.
- **2. Next Sentence Prediction (NSP):** BERT is given two sentences and must decide whether the second sentence logically follows the first. This teaches BERT the relationships between sentences.

**The Training Process (Step by Step)**

- **Step 1 - Gather huge text data:** BERT is trained on enormous text (like Wikipedia and books).
- **Step 2 - Prepare inputs:** Words are tokenized, special tokens ([CLS], [SEP]) are added, and about 15% of tokens are masked.
- **Step 3 - Apply MLM:** BERT predicts the masked words from context and learns from its mistakes.
- **Step 4 - Apply NSP:** BERT predicts whether sentence B follows sentence A.
- **Step 5 - Update weights:** Using backpropagation, BERT adjusts its weights to improve both tasks.
- **Step 6 - Repeat:** This continues until BERT deeply understands language.

**Pre-training and Fine-tuning**

- The above is 'pre-training' (general language learning).
- Later, BERT is 'fine-tuned' on a specific task with a small labelled dataset.

**Why is BERT's Training Important?**

- It gives BERT powerful, general language understanding.
- The two tasks teach word-level and sentence-level meaning.
- It enables strong performance after fine-tuning.

**Real-life example:** During training, BERT sees 'The [MASK] is shining brightly' and learns to predict 'sun' from context (MLM). It also sees two sentences and learns whether they follow each other (NSP). Through millions of such examples, BERT learns language deeply. This describes the training process of BERT.

**Q8. Explain the architecture and working of a Deep Q-Network (DQN).**

**What is a DQN?**

DQN stands for Deep Q-Network. It is a Deep Reinforcement Learning method that combines Q-Learning (a reinforcement learning technique) with a deep neural network. It lets an agent learn the best actions in complex environments, such as video games, directly from high-dimensional inputs like screen images.

**What is Q-Learning (Background)?**

- Q-Learning learns a 'Q-value' for each action in each state - the expected future reward of taking that action.
- Traditionally, Q-values are stored in a table, but this fails when there are too many states (like every possible game screen).
- DQN replaces the table with a neural network that estimates Q-values.

**The Architecture of a DQN**

- **Input:** The current state (for example, game screen pixels).
- **Deep neural network:** Processes the state and outputs a Q-value for each possible action.
- **Output:** The estimated Q-values; the action with the highest Q-value is usually chosen.
- **Replay buffer (memory):** Stores past experiences (state, action, reward, next state) to train on later.
- **Target network:** A second, slowly-updated network that stabilises training.

**How a DQN Works (Step by Step)**

- **Step 1 - Observe the state:** The agent sees the current state.
- **Step 2 - Estimate Q-values:** The network predicts Q-values for all actions.
- **Step 3 - Choose an action:** The agent usually picks the highest-Q action, but sometimes explores randomly (exploration).
- **Step 4 - Get reward and next state:** The environment gives a reward and a new state.
- **Step 5 - Store experience:** The experience is saved in the replay buffer.
- **Step 6 - Train:** Random samples from the buffer are used to update the network toward better Q-values.

**Why is DQN Important?**

- It handles huge, complex state spaces.
- It powers game-playing AI (like Atari games).
- It advanced deep reinforcement learning.

**Real-life example:** A DQN learning to play a game takes the screen as input, estimates Q-values for moves like left, right, and jump, and chooses the best. It stores its experiences and trains on them, gradually learning to score high. This explains the architecture and working of a DQN.

**Q9. Illustrate the architecture and working of a Conditional GAN (cGAN).**

**What is a Conditional GAN (cGAN)?**

A 'Conditional GAN' is a special type of GAN where the generation is controlled by an extra piece of information called a 'condition' (usually a label). While a normal GAN creates random data, a cGAN creates data of a specific requested type.

'Conditional' means the output depends on a given condition.

**Why cGAN is Needed**

- A normal GAN generates random samples - you cannot choose what it makes.
- A cGAN lets you control the output by giving a label (for example, 'generate the digit 7').

**The Architecture of a cGAN**

- **Generator:** Takes random noise PLUS a condition (label) as input, and produces fake data matching that condition.
- **Discriminator:** Takes a data sample PLUS the same condition, and judges whether the data is real AND matches the condition.
- **Condition (label):** Extra information (like a class label) fed to both networks.

**How a cGAN Works (Step by Step)**

- **Step 1 - Provide noise and condition:** The generator receives random noise and a label (for example, 'cat').
- **Step 2 - Generate conditioned data:** The generator produces data matching the label (a cat image).
- **Step 3 - Discriminator checks:** The discriminator receives the data and the label, and decides if it is both real and matching the label.
- **Step 4 - Learn together:** The generator improves at making label-matching data; the discriminator improves at spotting mismatches and fakes.

**Why is cGAN Important?**

- It gives control over what is generated.
- It enables targeted generation (specific classes).
- It powers tasks like image-to-image translation and labelled image generation.

**Real-life example:** To generate images of specific handwritten digits, a cGAN is given noise plus the label '7', and it produces an image of the digit 7. If asked for '3', it produces a 3. The discriminator checks that the image is real AND matches the requested digit. This illustrates the architecture and working of a Conditional GAN.

**Q10. Discuss applications of GANs in image generation and enhancement.**

**What is a GAN (Recap)?**

GAN stands for Generative Adversarial Network - a model with a Generator (creates fake data) and a Discriminator (judges data) that train together to produce realistic data. GANs are especially powerful for images. Let us discuss their applications in image generation and enhancement.

**Applications in Image Generation**

- **Creating realistic faces:** GANs generate photorealistic human faces that do not belong to any real person.
- **Art and design generation:** They create original artwork, patterns, and designs.
- **Generating training data:** They produce synthetic images to expand small datasets.
- **Text-to-image generation:** They create images from text descriptions.

**Applications in Image Enhancement**

- **Super-resolution:** GANs turn low-resolution, blurry images into sharp, high-resolution ones.
- **Image denoising:** They remove noise and grain from images.
- **Image inpainting:** They fill in missing or damaged parts of an image realistically.
- **Colorization:** They add realistic colour to old black-and-white photos.
- **Style transfer:** They change an image's style (for example, turning a photo into a painting).

**Why GANs are Good at These Tasks**

- The generator learns to produce highly realistic images.
- The discriminator's feedback pushes quality higher.
- Together they capture fine visual details.

**Why are These Applications Important?**

- They save time and cost in creating and fixing images.
- They enable new creative and practical tools.
- They improve data availability for training.

**Real-life example:** An old, blurry, black-and-white family photo is restored using GANs: super-resolution sharpens it, inpainting repairs torn areas, and colorization adds natural colours. The result is a clear, colour photo. This shows the applications of GANs in image generation and enhancement.

**Q11. Explain the fine-tuning of BERT for NLP tasks.**

**What is BERT (Recap)?**

BERT is a powerful pre-trained NLP model that understands language using context from both sides. After it is pre-trained on huge text (general language learning), it is adapted to specific tasks through a process called fine-tuning.

**What is Fine-tuning?**

'Fine-tuning' means taking the already pre-trained BERT model and training it a little more on a specific task using a smaller labelled dataset. Instead of learning language from scratch, BERT just adjusts to the new task.

**Why Fine-tuning is Useful**

- Pre-training gave BERT general language knowledge.
- Fine-tuning specialises this knowledge for one task.
- It needs far less data and time than training from scratch.

**How Fine-tuning Works (Step by Step)**

- **Step 1 - Start with pre-trained BERT:** Begin with BERT that already understands language.
- **Step 2 - Add a task-specific layer:** A small output layer is added on top for the specific task (for example, a classification layer).
- **Step 3 - Provide labelled task data:** A labelled dataset for the task is prepared (for example, reviews labelled positive/negative).
- **Step 4 - Train on the task:** BERT and the new layer are trained together on this data, slightly adjusting BERT's weights.
- **Step 5 - Use the fine-tuned model:** The specialised BERT is now ready for the task.

**Tasks BERT Can Be Fine-tuned For**

- Sentiment analysis, question answering, named entity recognition, text classification, and more.

**Why is Fine-tuning Important?**

- It reuses BERT's powerful knowledge (transfer learning).
- It gives high accuracy with little data.
- It saves time and computing cost.

**Real-life example:** To build a sentiment analyser, pre-trained BERT is fine-tuned on a few thousand movie reviews labelled positive or negative. A classification layer is added, and BERT is trained briefly on this data. The result is a highly accurate sentiment model built quickly. This explains the fine-tuning of BERT for NLP tasks.

**Q12. Describe applications of Deep Reinforcement Learning in gaming, robotics, and automation.**

**What is Deep Reinforcement Learning (Recap)?**

Deep Reinforcement Learning (Deep RL) combines reinforcement learning (learning by trial and error using rewards) with deep neural networks. An agent learns the best actions by interacting with an environment and receiving rewards. Deep RL is used in many real areas. Let us describe its applications in gaming, robotics, and automation.

**Applications in Gaming**

- **Playing games at expert level:** Deep RL agents learn to play games (like chess, Go, and video games) by playing millions of times.
- **Learning strategies:** They discover winning strategies humans may not think of.
- **Example:** AlphaGo used Deep RL to beat world champions at the game of Go.

**Applications in Robotics**

- **Learning movements:** Robots learn to walk, grasp objects, and balance through trial and error.
- **Adapting to environments:** Robots adjust to new or changing surroundings.
- **Example:** A robotic arm learns to pick up and place objects accurately by practising and receiving rewards.

**Applications in Automation**

- **Self-driving vehicles:** Deep RL helps cars learn to steer, brake, and navigate safely.
- **Industrial control:** It optimises factory processes and energy use.
- **Resource management:** It manages systems like data centres and traffic signals efficiently.
- **Example:** A traffic-control system learns to time signals to reduce congestion.

**Why Deep RL Suits These Areas**

- These tasks involve sequential decisions and feedback.
- Deep RL learns from experience without exact instructions.
- Deep neural networks handle complex inputs like images and sensor data.

**Why are These Applications Important?**

- They solve complex, real-world decision problems.
- They enable intelligent, self-improving systems.
- They advance AI in practical fields.

**Real-life example:** In automation, a self-driving car uses Deep RL to learn safe driving: it observes the road (state), takes actions (steer, brake), and earns rewards for safe, smooth driving. Over time it drives skilfully. Similar learning helps game AIs and robots. This describes applications of Deep RL in gaming, robotics, and automation.

**FILL IN THE BLANKS**

**1.** The variable that is predicted by a supervised learning model is called the __________ variable.
**Answer:** Target

**2.** GoogLeNet introduced the __________ module.
**Answer:** Inception

**3.** The process of converting categorical values into numerical form is called __________ encoding.
**Answer:** Categorical

**4.** A model that performs well on training data but poorly on unseen data suffers from __________.
**Answer:** Overfitting

**5.** A digital image is made up of a grid of small units called __________.
**Answer:** Pixels

**6.** The process of passing input data through the layers of a neural network to produce an output is called __________ propagation.
**Answer:** Forward

**7.** PCA is used for __________ reduction.
**Answer:** Dimensionality

**8.** The pooling method that calculates the mean value of each window is called __________.
**Answer:** Average Pooling

**9.** In supervised learning, data contains features and correct __________.
**Answer:** Labels

**10.** The number of pixels by which a filter moves across an image is called __________.
**Answer:** Stride

**11.** The first step in the machine learning workflow is __________.
**Answer:** Data Collection

**12.** The technique of dividing data into multiple parts for repeated training and validation is called __________.
**Answer:** Cross-validation

**13.** A __________ is an additional value added to adjust the output before applying the activation function.
**Answer:** Bias

**14.** K-Means algorithm is commonly used for __________.
**Answer:** Clustering

**15.** Adding a border of zeros around an image before convolution is called __________.
**Answer:** Padding

**16.** Supervised learning is mainly divided into classification and __________.
**Answer:** Regression

**17.** Identifying unusual or abnormal data points is called __________ detection.
**Answer:** Anomaly

**18.** The CNN architecture that won the 2012 ImageNet competition by a large margin was __________.
**Answer:** AlexNet

**19.** The process of dividing a dataset into training and testing portions is called __________.
**Answer:** Train-test split

**20.** Standardization commonly transforms numerical features to have a mean of __________ and standard deviation of one.
**Answer:** Zero

**21.** The pooling method that keeps the largest value from each window is called __________.
**Answer:** Max Pooling

**22.** Machine Learning is a branch of __________ that allows computers to learn from data without being explicitly programmed for every task.
**Answer:** Artificial Intelligence

**23.** The Flatten layer converts a 2D or 3D feature map into a __________.
**Answer:** 1D vector

**24.** In Reinforcement Learning, the learner or decision-maker is referred to as __________.
**Answer:** Agent

**25.** The process of propagating the error backward through a neural network to update weights is called __________.
**Answer:** Backpropagation

**26.** A digital image can be represented as a __________ of numerical values.
**Answer:** Matrix

**MULTIPLE CHOICE QUESTIONS**

**1.** What is the main objective of GAN training?
A. To classify images
B. To reduce dataset size
C. To generate realistic data
D. To sort data
**Answer:** C. To generate realistic data

**2.** Which strategy allows an RL agent to sometimes choose a random action to discover better choices?
A. Classification
B. Exploration
C. Encoding
D. Normalization
**Answer:** B. Exploration

**3.** LSTM stands for:
A. Long Short-Term Memory
B. Linear Short-Term Machine
C. Long Sequence Training Model
D. Long State Transfer Model
**Answer:** A. Long Short-Term Memory

**4.** What is the role of positional encoding in a Transformer?
A. To reduce the vocabulary size
B. To provide information about token order
C. To remove unnecessary tokens
D. To increase the number of layers
**Answer:** B. To provide information about token order

**5.** Which technique initializes weights so that repeated terms remain close to a suitable range?
A. Dropout
B. Max Pooling
C. Feature Scaling
D. Better Initialization
**Answer:** D. Better Initialization

**6.** In an LSTM, which gate controls what information should be removed from the cell state?
A. Input gate
B. Forget gate
C. Output gate
D. Update gate
**Answer:** B. Forget gate

**7.** BERT is primarily designed for which type of data?
A. Numerical tables only
B. Text
C. Audio only
D. Sensor readings only
**Answer:** B. Text

**8.** Which technique limits the size of a gradient before updating the weights?
A. Padding
B. Dropout
C. Data Normalization
D. Gradient Clipping
**Answer:** D. Gradient Clipping

**9.** Which architecture uses separate encoder and decoder components for sequence-to-sequence tasks?
A. Autoencoder
B. Encoder-decoder architecture
C. CNN
D. K-Means
**Answer:** B. Encoder-decoder architecture

**10.** Full BPTT on a very long sequence is generally:
A. Fast and memory-free
B. Independent of sequence length
C. Slow and memory-heavy
D. Used only for images
**Answer:** C. Slow and memory-heavy

**11.** Which mechanism allows a Transformer to focus on important parts of the input?
A. Classification
B. Sampling
C. Pooling
D. Self-attention
**Answer:** D. Self-attention

**12.** In reinforcement learning, what does an agent receive after taking an action?
A. Reward
B. Feature vector
C. Token
D. Gradient
**Answer:** A. Reward

**13.** Which component of a Transformer helps convert input tokens into numerical representations?
A. Token embedding
B. Replay buffer
C. Reward function
D. Q-table
**Answer:** A. Token embedding

**14.** Which RNN architecture is designed to learn long-term dependencies in sequential data?
A. LSTM
B. K-Means
C. CNN
D. Decision Tree
**Answer:** A. LSTM

**15.** What problem can occur when gradients become extremely small during RNN training?
A. Vanishing gradient problem
B. Over-sampling problem
C. Data duplication problem
D. Feature selection problem
**Answer:** A. Vanishing gradient problem

**16.** Which of the following is a component commonly associated with a Transformer encoder?
A. Feed-forward network
B. Replay buffer
C. Reward table
D. Generator
**Answer:** A. Feed-forward network

**17.** Which technique shortens the backward window during training?
A. Full BPTT
B. Forward Pass
C. Truncated BPTT
D. Gradient Boosting
**Answer:** C. Truncated BPTT

**18.** Which part of a GAN creates new samples from random input?
A. Discriminator
B. Generator
C. Encoder
D. Classifier
**Answer:** B. Generator

**19.** GRU stands for:
A. General Recurrent Unit
B. Generalized Random Unit
C. Gated Recurrent Unit
D. Gradient Recurrent Utility
**Answer:** C. Gated Recurrent Unit

**20.** A smaller learning rate can help reduce the damage caused by:
A. Long inputs
B. Large gradient updates
C. Missing values
D. Extra features
**Answer:** B. Large gradient updates

**21.** What is the main purpose of fine-tuning a pre-trained NLP model?
A. Adapt it to a specific task
B. Remove all learned knowledge
C. Convert text into images
D. Stop the training permanently
**Answer:** A. Adapt it to a specific task

**22.** What is a major feature of the Transformer architecture?
A. It processes only images
B. It can process sequence elements efficiently
C. It does not use numerical data
D. It requires no training
**Answer:** B. It can process sequence elements efficiently

**23.** Query, Key and Value are associated with which mechanism in Transformers?
A. Attention
B. Pooling
C. Q-learning
D. GAN loss
**Answer:** A. Attention

**24.** Which is an example of a task where long-range dependencies can be important?
A. Machine translation
B. File compression
C. Image cropping
D. Sorting numbers
**Answer:** A. Machine translation

**25.** In BERT, what does the bidirectional nature mainly allow the model to use?
A. Only previous words
B. Only next words
C. Context from both directions
D. Only numerical features
**Answer:** C. Context from both directions
