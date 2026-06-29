# Glossary: FAEAP

## What is a Glossary?

A glossary is an alphabetical list of terms or words found in or relating to a specific subject, text, or dialect, with explanations; a brief dictionary. This glossary explains technical terms used in the FAEAP project in beginner-friendly language.

## Why is a Glossary Important?

### Understanding
1. **Clarity**: Ensures consistent understanding of terms
2. **Learning**: Helps new team members learn quickly
3. **Communication**: Facilitates clear communication
4. **Documentation**: Provides reference for documentation

### Accessibility
1. **Beginner-Friendly**: Makes technical content accessible
2. **Cross-Disciplinary**: Helps experts from different fields
3. **Stakeholders**: Helps non-technical stakeholders
4. **Reviewers**: Helps reviewers understand terminology

## Glossary Terms

### A

#### Accuracy
**What it is**: The percentage of correct predictions made by a model. For example, if a model correctly identifies 95 out of 100 audio samples as authentic or manipulated, its accuracy is 95%.

**Why it's needed**: Measures how well the model performs its task.

**How it works**: Calculated as (correct predictions) / (total predictions) × 100.

**Advantages**: Simple to understand and calculate.

**Disadvantages**: Can be misleading if classes are imbalanced.

**Alternatives**: Precision, recall, F1-score.

**Why we selected it**: Standard metric for classification tasks.

**Future improvements**: Use balanced accuracy for imbalanced datasets.

---

#### Acoustic Environment
**What it is**: The physical surroundings where audio is recorded, including room size, surfaces, and background noise.

**Why it's needed**: Different environments affect audio quality and characteristics.

**How it works**: Environments can be quiet (studio), noisy (street), or reverberant (large hall).

**Advantages**: Understanding environment helps with audio analysis.

**Disadvantages**: Complex to model accurately.

**Alternatives**: None - fundamental concept.

**Why we selected it**: Important for forensic audio analysis.

**Future improvements**: Use environmental classification in model.

---

#### Activation Function
**What it is**: A mathematical operation that determines the output of a neural network node. It introduces non-linearity, allowing the network to learn complex patterns.

**Why it's needed**: Without activation functions, neural networks would only learn linear relationships.

**How it works**: Common functions include ReLU (returns positive values), sigmoid (squashes values between 0 and 1), and tanh (squashes values between -1 and 1).

**Advantages**: Enables learning of complex patterns.

**Disadvantages**: Choice of function affects training stability.

**Alternatives**: Different activation functions (ReLU, sigmoid, tanh, softmax).

**Why we selected it**: Essential for neural network operation.

**Future improvements**: Experiment with newer activation functions.

---

#### ADAM Optimizer
**What it is**: An optimization algorithm for training neural networks. It adapts the learning rate for each parameter based on estimates of first and second moments of gradients.

**Why it's needed**: Helps neural networks learn faster and more effectively.

**How it works**: Combines ideas from momentum and RMSprop optimization.

**Advantages**: Fast convergence, works well in practice.

**Disadvantages**: Can sometimes converge to suboptimal solutions.

**Alternatives**: SGD, RMSprop, Adagrad.

**Why we selected it**: Standard optimizer for deep learning.

**Future improvements**: Try newer optimizers like AdamW.

---

#### Annotation
**What it is**: The process of labeling data with information that helps models learn. For example, labeling audio as "authentic" or "manipulated" and specifying where manipulation occurs.

**Why it's needed**: Models need labeled data to learn patterns.

**How it works**: Human experts or automated systems add labels to data.

**Advantages**: Provides supervision for learning.

**Disadvantages**: Time-consuming and expensive.

**Alternatives**: Weak supervision, self-supervised learning.

**Why we selected it**: Essential for supervised learning.

**Future improvements**: Use semi-supervised learning to reduce annotation needs.

---

#### Attention Mechanism
**What it is**: A component in neural networks that allows the model to focus on specific parts of the input. For example, focusing on the region where audio manipulation occurs.

**Why it's needed**: Helps models identify important parts of the input.

**How it works**: Learns weights that indicate the importance of different input parts.

**Advantages**: Improves interpretability and performance.

**Disadvantages**: Adds computational complexity.

**Alternatives**: None - fundamental mechanism.

**Why we selected it**: Critical for localization and explainability.

**Future improvements**: Explore cross-attention mechanisms.

---

#### Audio Authentication
**What it is**: The process of verifying whether an audio recording is authentic or has been manipulated.

**Why it's needed**: Ensures integrity of audio evidence in forensic investigations.

**How it works**: AI models analyze audio for signs of manipulation.

**Advantages**: Automated, faster than manual analysis.

**Disadvantages**: May produce false positives/negatives.

**Alternatives**: Manual forensic analysis.

**Why we selected it**: Core task of FAEAP.

**Future improvements**: Improve accuracy and reduce false positives.

---

#### Audio Event
**What it is**: A specific sound occurrence in audio, such as a gunshot, scream, explosion, or vehicle crash.

**Why it's needed**: AI-generated audio events are a common manipulation technique.

**How it works**: Events have characteristic acoustic patterns.

**Advantages**: Can be detected and classified by AI models.

**Disadvantages**: Some events are similar to natural sounds.

**Alternatives**: None - fundamental concept.

**Why we selected it**: Focus of manipulation detection.

**Future improvements**: Expand to more event types.

---

#### Audio Forensics
**What it is**: The field of analyzing audio recordings for legal and investigative purposes. It includes authentication, enhancement, and interpretation of audio evidence.

**Why it's needed**: Audio evidence is used in criminal investigations, court proceedings, and other legal contexts.

**How it works**: Forensic analysts use specialized tools and techniques to analyze audio.

**Advantages**: Provides scientific basis for audio evidence.

**Disadvantages**: Traditional methods are time-consuming and require expertise.

**Alternatives**: None - established field.

**Why we selected it**: Domain of FAEAP application.

**Future improvements**: Integrate AI with traditional methods.

---

#### AudioMAE
**What it is**: Audio Masked Autoencoder, a self-supervised learning model for audio. It learns by predicting masked parts of audio spectrograms.

**Why it's needed**: Provides pre-trained audio representations for forensic tasks.

**How it works**: Trained on large audio datasets using masked prediction.

**Advantages**: State-of-the-art audio representations, efficient.

**Disadvantages**: Requires fine-tuning for specific tasks.

**Alternatives**: CLAP, BEATs, WavLM, AST.

**Why we selected it**: Best balance of performance and efficiency.

**Future improvements**: Explore newer foundation models.

---

#### Augmentation
**What it is**: The process of creating modified versions of data to increase dataset diversity and improve model generalization. For audio, this includes time stretching, pitch shifting, and adding noise.

**Why it's needed**: Helps models generalize to new data.

**How it works**: Applies random transformations to training data.

**Advantages**: Improves model robustness, reduces overfitting.

**Disadvantages**: Can create unrealistic data if not careful.

**Alternatives**: None - standard technique.

**Why we selected it**: Essential for training robust models.

**Future improvements**: Use advanced augmentation techniques.

---

### B

#### Backbone Network
**What it is**: The main neural network architecture that extracts features from input data. In FAEAP, AudioMAE serves as the backbone.

**Why it's needed**: Provides feature extraction for task-specific heads.

**How it works**: Processes input to produce high-dimensional representations.

**Advantages**: Reusable across different tasks.

**Disadvantages**: Backbone choice affects overall performance.

**Alternatives**: Different backbone architectures.

**Why we selected it**: AudioMAE provides excellent audio features.

**Future improvements**: Explore ensemble of backbones.

---

#### Batch Processing
**What it is**: Processing multiple samples simultaneously rather than one at a time. Improves computational efficiency.

**Why it's needed**: Speeds up training and inference.

**How it works**: Groups samples into batches and processes them together.

**Advantages**: Faster processing, better GPU utilization.

**Disadvantages**: Requires more memory.

**Alternatives**: Sequential processing.

**Why we selected it**: Standard practice for efficiency.

**Future improvements**: Optimize batch size for performance.

---

#### Batch Size
**What it is**: The number of samples processed together in one iteration of training.

**Why it's needed**: Affects training speed and model performance.

**How it works**: Larger batches use more samples per iteration.

**Advantages**: Larger batches are faster, smaller batches may generalize better.

**Disadvantages**: Too large may cause memory issues, too small may be slow.

**Alternatives**: Dynamic batch sizing.

**Why we selected it**: Important hyperparameter for training.

**Future improvements**: Use adaptive batch sizing.

---

#### Binary Classification
**What it is**: A classification task with only two possible outcomes. In FAEAP, authentic vs. manipulated.

**Why it's needed**: Detection task is binary classification.

**How it works**: Model outputs probability for each class.

**Advantages**: Simple to implement and evaluate.

**Disadvantages**: Not suitable for multi-class problems.

**Alternatives**: Multi-class classification.

**Why we selected it**: Detection is a binary task.

**Future improvements**: None - appropriate for detection.

---

#### Bit Depth
**What it is**: The number of bits used to represent each audio sample. Higher bit depth means better audio quality. Common values are 16-bit, 24-bit, and 32-bit.

**Why it's needed**: Affects audio quality and file size.

**How it works**: More bits = more precise amplitude representation.

**Advantages**: Higher bit depth = better quality.

**Disadvantages**: Higher bit depth = larger file size.

**Alternatives**: None - audio property.

**Why we selected it**: Important for dataset quality.

**Future improvements**: Use 24-bit for high quality.

---

#### BLEU Score
**What it is**: A metric for evaluating text generation quality. Measures similarity between generated and reference text.

**Why it's needed**: Not directly used in FAEAP but relevant for text-to-audio models.

**How it works**: Calculates n-gram overlap between texts.

**Advantages**: Standard metric for text generation.

**Disadvantages**: Not suitable for audio tasks.

**Alternatives**: ROUGE, METEOR.

**Why we selected it**: Not selected - for reference only.

**Future improvements**: Not applicable.

---

### C

#### Chain of Custody
**What it is**: The documentation of the seizure, custody, control, transfer, analysis, and disposition of physical or electronic evidence. Critical for legal admissibility.

**Why it's needed**: Ensures evidence integrity in legal proceedings.

**How it works**: Every person who handles evidence documents their actions.

**Advantages**: Provides legal proof of evidence integrity.

**Disadvantages**: Requires strict documentation procedures.

**Alternatives**: None - legal requirement.

**Why we selected it**: Essential for forensic applications.

**Future improvements**: Automate with blockchain.

---

#### Classification
**What it is**: The task of predicting the category or class of input data. In FAEAP, classifying manipulation types (gunshot, scream, etc.).

**Why it's needed**: Identifies what type of manipulation occurred.

**How it works**: Model learns patterns for each class.

**Advantages**: Provides detailed forensic information.

**Disadvantages**: Requires labeled data for each class.

**Alternatives**: Clustering (unsupervised).

**Why we selected it**: Essential for forensic analysis.

**Future improvements**: Add hierarchical classification.

---

#### CLAP
**What it is**: Contrastive Language-Audio Pretraining, a foundation model that learns from audio-text pairs.

**Why it's needed**: Provides rich audio representations with text understanding.

**How it works**: Trained to match audio with text descriptions.

**Advantages**: Multi-modal understanding, state-of-the-art performance.

**Disadvantages**: Larger model, text modality not needed for forensics.

**Alternatives**: AudioMAE, BEATs, WavLM.

**Why we selected it**: Considered but rejected in favor of AudioMAE.

**Future improvements**: Consider if text context becomes valuable.

---

#### CNN (Convolutional Neural Network)
**What it is**: A type of neural network designed for processing grid-like data such as images. Can be applied to audio spectrograms.

**Why it's needed**: Traditional approach for audio classification.

**How it works**: Uses convolutional layers to extract local patterns.

**Advantages**: Effective for pattern recognition, well-understood.

**Disadvantages**: Less effective than transformers for audio.

**Alternatives**: Transformers, RNNs.

**Why we selected it**: Not selected - transformers preferred.

**Future improvements**: Use as baseline for comparison.

---

#### Confusion Matrix
**What it is**: A table that shows the performance of a classification model. Rows represent actual classes, columns represent predicted classes.

**Why it's needed**: Shows detailed classification performance.

**How it works**: Counts correct and incorrect predictions for each class.

**Advantages**: Reveals which classes are confused with each other.

**Disadvantages**: Can be large for many classes.

**Alternatives**: Accuracy, precision, recall.

**Why we selected it**: Essential for multi-class evaluation.

**Future improvements**: Use normalized confusion matrix.

---

#### Cross-Entropy Loss
**What it is**: A loss function used for classification tasks. Measures the difference between predicted and actual class probabilities.

**Why it's needed**: Trains classification models effectively.

**How it works**: Penalizes incorrect predictions more heavily.

**Advantages**: Works well for classification, differentiable.

**Disadvantages**: Can be sensitive to class imbalance.

**Alternatives**: Hinge loss, focal loss.

**Why we selected it**: Standard loss for classification.

**Future improvements**: Use focal loss for imbalanced data.

---

#### Cross-Validation
**What it is**: A technique for evaluating model performance by splitting data into multiple train/test splits and averaging results.

**Why it's needed**: Provides more reliable performance estimates.

**How it works**: Divides data into k folds, trains on k-1 folds, tests on remaining fold.

**Advantages**: Reduces variance of performance estimate.

**Disadvantages**: Computationally expensive.

**Alternatives**: Single train/test split.

**Why we selected it**: Use for model evaluation.

**Future improvements**: Use stratified cross-validation.

---

### D

#### Dataset
**What it is**: A collection of data used for training and evaluating machine learning models. FAEAP creates FAEAD (Forensic Audio Evidence Authentication Dataset).

**Why it's needed**: Models need data to learn patterns.

**How it works**: Contains samples with labels and metadata.

**Advantages**: Enables model training and evaluation.

**Disadvantages**: Time-consuming to create and curate.

**Alternatives**: Use existing datasets.

**Why we selected it**: Custom dataset needed for forensic tasks.

**Future improvements**: Expand dataset with more samples.

---

#### Data Augmentation
**What it is**: See "Augmentation".

---

#### Deep Learning
**What it is**: A subset of machine learning that uses neural networks with many layers (deep networks) to learn complex patterns from data.

**Why it's needed**: Enables learning of complex audio patterns.

**How it works**: Networks learn hierarchical representations.

**Advantages**: State-of-the-art performance on many tasks.

**Disadvantages**: Requires large datasets and computational resources.

**Alternatives**: Traditional machine learning.

**Why we selected it**: Essential for audio forensics.

**Future improvements**: Explore newer architectures.

---

#### Deepfake
**What it is**: AI-generated or manipulated media that appears authentic. In audio, AI-generated speech or sounds.

**Why it's needed**: AI deepfakes are a major threat to audio evidence.

**How it works**: Uses AI models to generate realistic audio.

**Advantages**: For attackers: easy to create fake audio.

**Disadvantages**: For defenders: difficult to detect.

**Alternatives**: None - threat type.

**Why we selected it**: Primary threat FAEAP addresses.

**Future improvements**: Adapt to new deepfake techniques.

---

#### Detection
**What it is**: The task of identifying whether audio has been manipulated (binary classification).

**Why it's needed**: First step in forensic analysis.

**How it works**: Model predicts authentic or manipulated.

**Advantages**: Provides quick assessment of audio authenticity.

**Disadvantages**: Doesn't provide details about manipulation.

**Alternatives**: None - core task.

**Why we selected it**: Essential forensic task.

**Future improvements**: Improve accuracy and reduce false positives.

---

#### Dropout
**What it is**: A regularization technique that randomly drops (sets to zero) neurons during training to prevent overfitting.

**Why it's needed**: Prevents model from memorizing training data.

**How it works**: Randomly deactivates neurons each training iteration.

**Advantages**: Reduces overfitting, improves generalization.

**Disadvantages**: Can slow down training.

**Alternatives**: L1/L2 regularization, batch normalization.

**Why we selected it**: Standard regularization technique.

**Future improvements**: Tune dropout rates for optimal performance.

---

### E

#### Embedding
**What it is**: A high-dimensional vector representation of data. Audio embeddings capture audio features in a numerical form.

**Why it's needed**: Converts audio to numerical form for processing.

**How it works**: Neural network learns to map audio to vectors.

**Advantages**: Captures semantic meaning, efficient processing.

**Disadvantages**: High-dimensional, requires interpretation.

**Alternatives**: Raw audio, hand-crafted features.

**Why we selected it**: Standard for deep learning on audio.

**Future improvements**: Use contrastive learning for better embeddings.

---

#### Epoch
**What it is**: One complete pass through the entire training dataset during model training.

**Why it's needed**: Multiple epochs allow model to learn from data repeatedly.

**How it works**: Training iterates through dataset multiple times.

**Advantages**: Improves learning with multiple passes.

**Disadvantages**: Too many epochs can cause overfitting.

**Alternatives**: Early stopping.

**Why we selected it**: Standard training concept.

**Future improvements**: Use early stopping to prevent overfitting.

---

#### Evaluation Metrics
**What it is**: Measures used to assess model performance. Examples include accuracy, precision, recall, F1-score.

**Why it's needed**: Quantifies how well model performs.

**How it works**: Compare predictions to ground truth.

**Advantages**: Provides objective performance assessment.

**Disadvantages**: Different metrics may give different conclusions.

**Alternatives**: None - essential concept.

**Why we selected it**: Essential for model assessment.

**Future improvements**: Use multiple metrics for comprehensive evaluation.

---

#### Explainability
**What it is**: The ability to understand and explain how a model makes its predictions. Critical for court admissibility.

**Why it's needed**: Forensic analysts need to understand model decisions.

**How it works**: Techniques like attention visualization, feature importance.

**Advantages**: Increases trust, enables legal acceptance.

**Disadvantages**: May reduce model performance.

**Alternatives**: Black-box models.

**Why we selected it**: Essential for forensic applications.

**Future improvements**: Improve explainability techniques.

---

### F

#### F1-Score
**What it is**: The harmonic mean of precision and recall. Provides a single metric that balances both.

**Why it's needed**: Balances precision and recall in one metric.

**How it works**: F1 = 2 × (precision × recall) / (precision + recall).

**Advantages**: Good for imbalanced datasets.

**Disadvantages**: Doesn't consider true negatives.

**Alternatives**: Accuracy, balanced accuracy.

**Why we selected it**: Standard metric for classification.

**Future improvements**: Use macro/micro F1 for multi-class.

---

#### False Negative
**What it is**: When a model incorrectly predicts a negative class when the true class is positive. In forensics, failing to detect manipulation.

**Why it's needed**: Critical error in forensics (missed manipulation).

**How it works**: Model predicts authentic when audio is manipulated.

**Advantages**: None - this is an error.

**Disadvantages**: Serious consequence in forensics.

**Alternatives**: None - error type.

**Why we selected it**: Important error to minimize.

**Future improvements**: Optimize for high recall to reduce false negatives.

---

#### False Positive
**What it is**: When a model incorrectly predicts a positive class when the true class is negative. In forensics, incorrectly flagging authentic audio as manipulated.

**Why it's needed**: Important error in forensics (false accusation).

**How it works**: Model predicts manipulated when audio is authentic.

**Advantages**: None - this is an error.

**Disadvantages**: Wastes analyst time, potential legal issues.

**Alternatives**: None - error type.

**Why we selected it**: Important error to minimize.

**Future improvements**: Optimize for high precision to reduce false positives.

---

#### Feature Extraction
**What it is**: The process of transforming raw data into numerical features that represent important characteristics. For audio, features include MFCCs, spectrograms, etc.

**Why it's needed**: Converts audio to numerical form for processing.

**How it works**: Algorithms extract relevant audio characteristics.

**Advantages**: Captures important information, reduces data size.

**Disadvantages**: May lose some information.

**Alternatives**: Raw audio processing.

**Why we selected it**: Essential for audio analysis.

**Future improvements**: Use deep learning for automatic feature extraction.

---

#### Fine-Tuning
**What it is**: The process of taking a pre-trained model and training it further on a specific task. Adapts general model to specific domain.

**Why it's needed**: Adapts pre-trained models to forensic tasks.

**How it works**: Train pre-trained model on forensic dataset with smaller learning rate.

**Advantages**: Faster training, less data needed, better performance.

**Disadvantages**: May overfit if not careful.

**Alternatives**: Train from scratch.

**Why we selected it**: Standard approach for transfer learning.

**Future improvements**: Explore parameter-efficient fine-tuning.

---

#### Foundation Model
**What it is**: A large-scale pre-trained model that can be adapted to many different tasks. Examples include AudioMAE, CLAP, GPT.

**Why it's needed**: Provides powerful pre-trained representations.

**How it works**: Trained on massive datasets, then fine-tuned for specific tasks.

**Advantages**: State-of-the-art performance, reduces training time.

**Disadvantages**: Large computational requirements.

**Alternatives**: Train models from scratch.

**Why we selected it**: AudioMAE is our foundation model.

**Future improvements**: Explore newer foundation models.

---

#### Frame-Level
**What it is**: Analysis or prediction at the level of individual audio frames (typically 10-50ms segments). Provides temporal precision.

**Why it's needed**: Enables precise temporal localization.

**How it works**: Divide audio into frames, process each frame.

**Advantages**: Provides temporal precision.

**Disadvantages**: Computationally more expensive.

**Alternatives**: Clip-level analysis.

**Why we selected it**: Essential for localization.

**Future improvements**: Optimize frame-level processing.

---

### G

#### GPU (Graphics Processing Unit)
**What it is**: A specialized processor designed for parallel processing. Essential for training deep learning models.

**Why it's needed**: Dramatically speeds up neural network training and inference.

**How it works**: Performs many calculations simultaneously.

**Advantages**: Much faster than CPU for deep learning.

**Disadvantages**: Expensive, requires specific programming.

**Alternatives**: CPU (much slower).

**Why we selected it**: Essential for deep learning.

**Future improvements**: Use cloud GPUs for scalability.

---

#### Gradient Descent
**What it is**: An optimization algorithm that iteratively adjusts model parameters to minimize loss. Moves parameters in direction of steepest descent.

**Why it's needed**: Trains neural networks by minimizing loss.

**How it works**: Calculates gradient of loss, updates parameters opposite to gradient.

**Advantages**: Simple, effective optimization.

**Disadvantages**: Can get stuck in local minima.

**Alternatives**: Adam, RMSprop, other optimizers.

**Why we selected it**: Fundamental optimization concept.

**Future improvements**: Use advanced optimizers like Adam.

---

#### Ground Truth
**What it is**: The correct or true labels for data. Used to train and evaluate models.

**Why it's needed**: Provides supervision for learning and evaluation.

**How it works**: Human experts or trusted sources provide correct labels.

**Advantages**: Enables supervised learning and evaluation.

**Disadvantages**: Expensive to obtain, may contain errors.

**Alternatives**: Weak supervision, self-supervised learning.

**Why we selected it**: Essential for supervised learning.

**Future improvements**: Use semi-supervised learning to reduce needs.

---

### H

#### Hyperparameter
**What it is**: A parameter whose value is set before training begins, as opposed to parameters learned during training. Examples include learning rate, batch size, number of layers.

**Why it's needed**: Controls model training behavior and architecture.

**How it works**: Set before training, affects training process.

**Advantages**: Allows control over model training.

**Disadvantages**: Requires tuning for optimal performance.

**Alternatives**: AutoML for automatic hyperparameter tuning.

**Why we selected it**: Essential for model training.

**Future improvements**: Use hyperparameter optimization.

---

### I

#### Inference
**What it is**: The process of using a trained model to make predictions on new data. Also called prediction or deployment.

**Why it's needed**: Applies trained model to real forensic cases.

**How it works**: Feed new audio through trained model.

**Advantages**: Enables practical use of model.

**Disadvantages**: May be slow for large models.

**Alternatives**: None - essential concept.

**Why we selected it**: Essential for practical application.

**Future improvements**: Optimize for faster inference.

---

#### IoU (Intersection over Union)
**What it is**: A metric for measuring overlap between predicted and actual regions. Used for localization evaluation.

**Why it's needed**: Measures accuracy of temporal localization.

**How it works**: IoU = (intersection) / (union) of predicted and actual regions.

**Advantages**: Standard metric for localization tasks.

**Disadvantages**: Doesn't consider temporal precision within region.

**Alternatives**: MAE, precision, recall.

**Why we selected it**: Standard metric for localization.

**Future improvements**: Use weighted IoU for forensic importance.

---

### J

#### JSON (JavaScript Object Notation)
**What it is**: A lightweight data interchange format. Easy for humans to read and write, easy for machines to parse and generate.

**Why it's needed**: Standard format for storing and exchanging data.

**How it works**: Uses key-value pairs to represent data.

**Advantages**: Human-readable, widely supported.

**Disadvantages**: Not as compact as binary formats.

**Alternatives**: XML, YAML, CSV.

**Why we selected it**: Standard for metadata storage.

**Future improvements**: Use compression for large JSON files.

---

#### JWT (JSON Web Token)
**What it is**: A compact, URL-safe way to represent claims to be transferred between two parties. Used for authentication.

**Why it's needed**: Secure authentication for API access.

**How it works**: Encoded JSON with signature for verification.

**Advantages**: Stateless, secure, standard.

**Disadvantages**: Token size can be large.

**Alternatives**: Session-based authentication.

**Why we selected it**: Standard for API authentication.

**Future improvements**: Use short-lived tokens with refresh.

---

### K

#### K-Fold Cross-Validation
**What it is**: See "Cross-Validation".

---

#### Knowledge Distillation
**What it is**: A technique where a large model (teacher) teaches a smaller model (student) to mimic its behavior.

**Why it's needed**: Creates smaller, faster models while maintaining performance.

**How it works**: Student model learns from teacher's predictions.

**Advantages**: Smaller, faster models with good performance.

**Disadvantages**: Requires training two models.

**Alternatives**: Pruning, quantization.

**Why we selected it**: Not selected - potential future optimization.

**Future improvements**: Use for model compression.

---

### L

#### Learning Rate
**What it is**: A hyperparameter that controls how much the model changes in response to estimated error each time the model weights are updated.

**Why it's needed**: Controls speed and stability of training.

**How it works**: Larger learning rate = faster but less stable training.

**Advantages**: Controls training dynamics.

**Disadvantages**: Too large = unstable, too small = slow.

**Alternatives**: Learning rate scheduling.

**Why we selected it**: Critical hyperparameter for training.

**Future improvements**: Use learning rate schedulers.

---

#### Localization
**What it is**: The task of identifying where in audio manipulation occurs. Provides temporal boundaries.

**Why it's needed**: Forensic analysts need to know when manipulation happened.

**How it works**: Model predicts manipulation probability for each time segment.

**Advantages**: Provides precise temporal information.

**Disadvantages**: More complex than detection.

**Alternatives**: None - core forensic task.

**Why we selected it**: Essential for forensic analysis.

**Future improvements**: Improve precision below 100ms.

---

#### Log-Mel Spectrogram
**What it is**: A representation of audio that shows frequency content over time. Uses mel scale (perceptual scale) and logarithmic amplitude.

**Why it's needed**: Standard input representation for audio models.

**How it works**: Computes spectrogram, applies mel filterbank, takes log.

**Advantages**: Captures perceptually relevant features.

**Disadvantages**: Loses phase information.

**Alternatives**: MFCC, raw audio.

**Why we selected it**: Standard for audio models.

**Future improvements**: Explore raw audio input.

---

#### Loss Function
**What it is**: A function that measures how well a model's predictions match the true labels. Used to train models by minimizing loss.

**Why it's needed**: Provides objective for model training.

**How it works**: Calculates difference between predictions and labels.

**Advantages**: Guides model learning.

**Disadvantages**: Choice affects training behavior.

**Alternatives**: Different loss functions for different tasks.

**Why we selected it**: Essential for model training.

**Future improvements**: Use custom loss functions for forensics.

---

### M

#### MAE (Mean Absolute Error)
**What it is**: The average absolute difference between predicted and actual values. Used for regression tasks and localization.

**Why it's needed**: Measures accuracy of temporal localization.

**How it works**: MAE = average(|predicted - actual|).

**Advantages**: Intuitive, robust to outliers.

**Disadvantages**: Doesn't consider relative error.

**Alternatives**: MSE, RMSE.

**Why we selected it**: Standard metric for localization.

**Future improvements**: Use weighted MAE for forensic importance.

---

#### Machine Learning
**What it is**: A field of AI that enables systems to learn from data without being explicitly programmed.

**Why it's needed**: Enables automated pattern recognition from data.

**How it works**: Algorithms learn patterns from labeled or unlabeled data.

**Advantages**: Automates complex tasks, adapts to new data.

**Disadvantages**: Requires large datasets, can be opaque.

**Alternatives**: Rule-based systems.

**Why we selected it**: Foundation of FAEAP.

**Future improvements**: Explore newer ML techniques.

---

#### Mel Frequency Cepstral Coefficients (MFCC)
**What it is**: Features that represent the short-term power spectrum of sound. Widely used in speech and audio processing.

**Why it's needed**: Traditional audio feature representation.

**How it works**: Extracts cepstral coefficients from mel-scale spectrogram.

**Advantages**: Well-understood, effective for speech.

**Disadvantages**: Less effective than deep learning for complex tasks.

**Alternatives**: Deep learning features, raw audio.

**Why we selected it**: Not selected - deep learning preferred.

**Future improvements**: Use as baseline feature.

---

#### Mel Scale
**What it is**: A perceptual scale of pitches judged by listeners to be equal in distance from one another. Approximates human hearing.

**Why it's needed**: Captures perceptually relevant audio features.

**How it works**: Maps linear frequency scale to perceptual scale.

**Advantages**: Better matches human perception.

**Disadvantages**: Non-linear transformation.

**Alternatives**: Linear frequency scale.

**Why we selected it**: Standard for audio processing.

**Future improvements**: None - appropriate choice.

---

#### Metadata
**What it is**: Data that provides information about other data. For audio, includes recording device, environment, duration, etc.

**Why it's needed**: Provides context for forensic analysis.

**How it works**: Stored alongside audio files.

**Advantages**: Enables detailed analysis and tracking.

**Disadvantages**: Requires careful management.

**Alternatives**: None - essential concept.

**Why we selected it**: Essential for forensic applications.

**Future improvements**: Use standardized metadata schemas.

---

#### Metric
**What it is**: A standard of measurement. In ML, metrics quantify model performance.

**Why it's needed**: Objectively assesses model performance.

**How it works**: Compares predictions to ground truth.

**Advantages**: Provides objective assessment.

**Disadvantages**: Different metrics may give different conclusions.

**Alternatives**: None - essential concept.

**Why we selected it**: Essential for evaluation.

**Future improvements**: Use forensic-specific metrics.

---

#### MFCC
**What it is**: See "Mel Frequency Cepstral Coefficients".

---

#### Multi-Task Learning
**What it is**: A learning paradigm where multiple tasks are learned simultaneously using a shared representation.

**Why it's needed**: Improves efficiency and performance through shared learning.

**How it works**: Shared encoder with task-specific heads.

**Advantages**: Parameter efficiency, improved generalization.

**Disadvantages**: More complex training.

**Alternatives**: Single-task learning.

**Why we selected it**: Core architecture of FAEAP.

**Future improvements**: Explore task relationships.

---

### N

#### Neural Network
**What it is**: A computing system inspired by biological neural networks. Composed of interconnected nodes (neurons) organized in layers.

**Why it's needed**: Enables learning complex patterns from data.

**How it works**: Neurons process inputs, pass outputs to next layer.

**Advantages**: Universal function approximators.

**Disadvantages**: Require large data, computationally expensive.

**Alternatives**: Traditional ML algorithms.

**Why we selected it**: Foundation of deep learning.

**Future improvements**: Explore novel architectures.

---

#### Normalization
**What it is**: The process of scaling data to a standard range. Common ranges are [0, 1] or [-1, 1].

**Why it's needed**: Ensures stable training and consistent feature scales.

**How it works**: Subtracts mean, divides by standard deviation.

**Advantages**: Improves training stability.

**Disadvantages**: Requires computing statistics.

**Alternatives**: Standardization, min-max scaling.

**Why we selected it**: Standard preprocessing step.

**Future improvements**: Use layer normalization in models.

---

### O

#### Overfitting
**What it is**: When a model learns the training data too well, including noise and outliers, and performs poorly on new data.

**Why it's needed**: Problem to avoid in model training.

**How it works**: Model memorizes training data instead of learning general patterns.

**Advantages**: None - this is a problem.

**Disadvantages**: Poor generalization to new data.

**Alternatives**: Regularization, dropout, early stopping.

**Why we selected it**: Important problem to address.

**Future improvements**: Use strong regularization techniques.

---

### P

#### Parameter
**What it is**: A variable that is learned during model training. Weights and biases in neural networks are parameters.

**Why it's needed**: Parameters define the model's behavior.

**How it works**: Adjusted during training to minimize loss.

**Advantages**: Enable model to learn from data.

**Disadvantages**: More parameters = more computational cost.

**Alternatives**: Fixed parameters (not learned).

**Why we selected it**: Essential concept for deep learning.

**Future improvements**: Use parameter-efficient fine-tuning.

---

#### Patch
**What it is**: A small segment or region of input data. In AudioMAE, patches are segments of the spectrogram.

**Why it's needed**: Divides input into processable units.

**How it works**: Spectrogram divided into grid of patches.

**Advantages**: Enables transformer processing.

**Disadvantages**: May lose fine-grained information.

**Alternatives**: Raw audio processing.

**Why we selected it**: Part of AudioMAE architecture.

**Future improvements**: Optimize patch size.

---

#### Precision
**What it is**: The fraction of positive predictions that are actually positive. Measures how many predicted manipulations are real manipulations.

**Why it's needed**: Measures reliability of positive predictions.

**How it works**: Precision = true positives / (true positives + false positives).

**Advantages**: Important when false positives are costly.

**Disadvantages**: Doesn't consider false negatives.

**Alternatives**: Recall, F1-score.

**Why we selected it**: Important for forensics (avoid false accusations).

**Future improvements**: Optimize for high precision.

---

#### Pre-training
**What it is**: Training a model on a large dataset before fine-tuning it on a specific task. Provides general representations.

**Why it's needed**: Provides strong initial representations.

**How it works**: Train on large general dataset, then fine-tune on specific task.

**Advantages**: Better performance, less task-specific data needed.

**Disadvantages**: Requires large pre-training dataset.

**Alternatives**: Train from scratch.

**Why we selected it**: AudioMAE is pre-trained.

**Future improvements**: Explore self-supervised pre-training.

---

#### PyTorch
**What it is**: An open-source machine learning library for Python. Popular for deep learning research and production.

**Why it's needed**: Framework for implementing and training neural networks.

**How it works**: Provides tensors, automatic differentiation, neural network modules.

**Advantages**: Pythonic, research-friendly, good ecosystem.

**Disadvantages**: Less mature deployment than TensorFlow.

**Alternatives**: TensorFlow, JAX.

**Why we selected it**: Preferred framework for research.

**Future improvements**: Use PyTorch 2.0 for better performance.

---

### Q

#### Quantization
**What it is**: Reducing the precision of model parameters (e.g., from 32-bit to 8-bit) to reduce model size and speed up inference.

**Why it's needed**: Reduces computational requirements for deployment.

**How it works**: Converts high-precision parameters to low-precision.

**Advantages**: Smaller model, faster inference.

**Disadvantages**: May reduce accuracy.

**Alternatives**: Pruning, knowledge distillation.

**Why we selected it**: Not selected - potential future optimization.

**Future improvements**: Use for model compression.

---

### R

#### Recall
**What it is**: The fraction of actual positives that are correctly predicted. Measures how many real manipulations are detected.

**Why it's needed**: Measures ability to detect manipulations.

**How it works**: Recall = true positives / (true positives + false negatives).

**Advantages**: Important when false negatives are costly.

**Disadvantages**: Doesn't consider false positives.

**Alternatives**: Precision, F1-score.

**Why we selected it**: Important for forensics (detect all manipulations).

**Future improvements**: Optimize for high recall.

---

#### Recall@K
**What it is**: Recall metric considering only top K predictions. Used when model outputs multiple predictions.

**Why it's needed**: Measures recall for top predictions.

**How it works**: Recall calculated using only top K predictions.

**Advantages**: Relevant for retrieval tasks.

**Disadvantages**: Not applicable for single prediction.

**Alternatives**: Standard recall.

**Why we selected it**: Not directly used in FAEAP.

**Future improvements**: Not applicable.

---

#### Rectified Linear Unit (ReLU)
**What it is**: An activation function that returns the input if positive, otherwise returns zero. Most common activation function.

**Why it's needed**: Introduces non-linearity efficiently.

**How it works**: f(x) = max(0, x).

**Advantages**: Simple, computationally efficient, reduces vanishing gradient.

**Disadvantages**: Can cause "dead neurons".

**Alternatives**: Leaky ReLU, sigmoid, tanh.

**Why we selected it**: Standard activation function.

**Future improvements**: Try newer activation functions.

---

#### REST API
**What it is**: An API that follows REST (Representational State Transfer) architectural style. Uses HTTP methods (GET, POST, PUT, DELETE).

**Why it's needed**: Standard way for frontend to communicate with backend.

**How it works**: HTTP requests to endpoints return JSON responses.

**Advantages**: Standard, stateless, scalable.

**Disadvantages**: Can be verbose for complex queries.

**Alternatives**: GraphQL, gRPC.

**Why we selected it**: Standard for web APIs.

**Future improvements**: Consider GraphQL for complex queries.

---

#### ROC-AUC
**What it is**: Area under the Receiver Operating Characteristic curve. Measures model's ability to distinguish between classes.

**Why it's needed**: Threshold-independent performance metric.

**How it works**: Plots true positive rate vs false positive rate at various thresholds.

**Advantages**: Threshold-independent, single metric.

**Disadvantages**: Doesn't consider class distribution.

**Alternatives**: Precision-Recall AUC.

**Why we selected it**: Standard metric for binary classification.

**Future improvements**: Use Precision-Recall AUC for imbalanced data.

---

### S

#### Sample Rate
**What it is**: The number of samples of audio carried per second. Measured in Hz. Common rates: 16kHz, 44.1kHz, 48kHz.

**Why it's needed**: Determines audio quality and file size.

**How it works**: Higher sample rate = better quality, larger file.

**Advantages**: Higher rate = better quality.

**Disadvantages**: Higher rate = larger file, more processing.

**Alternatives**: None - audio property.

**Why we selected it**: Important for dataset quality.

**Future improvements**: Use 16kHz for efficiency, 44.1kHz for quality.

---

#### Self-Supervised Learning
**What it is**: A type of machine learning where the model learns from unlabeled data by creating its own supervision signals from the data.

**Why it's needed**: Enables learning from large unlabeled datasets.

**How it works**: Model predicts masked parts, contrasts samples, etc.

**Advantages**: No labels needed, learns rich representations.

**Disadvantages**: May not learn task-specific features.

**Alternatives**: Supervised learning, unsupervised learning.

**Why we selected it**: AudioMAE uses self-supervised learning.

**Future improvements**: Explore contrastive learning.

---

#### SNR (Signal-to-Noise Ratio)
**What it is**: The ratio of signal power to noise power. Measures audio quality. Higher SNR = better quality.

**Why it's needed**: Measures audio quality for dataset and restoration.

**How it works**: SNR = 10 × log10(signal_power / noise_power).

**Advantages**: Standard quality metric.

**Disadvantages**: Doesn't consider perceptual quality.

**Alternatives**: PESQ, STOI, MOS.

**Why we selected it**: Standard metric for audio quality.

**Future improvements**: Use perceptual metrics for restoration.

---

#### Spectrogram
**What it is**: A visual representation of audio showing frequency content over time. X-axis is time, Y-axis is frequency, color is amplitude.

**Why it's needed**: Standard input representation for audio models.

**How it works**: Computes Fourier transform over sliding windows.

**Advantages**: Captures frequency content over time.

**Disadvantages**: Loses phase information.

**Alternatives**: MFCC, raw audio.

**Why we selected it**: Standard for audio models.

**Future improvements**: Explore raw audio input.

---

#### Split
**What it is**: Division of dataset into training, validation, and test sets.

**Why it's needed**: Separate data for training, tuning, and evaluation.

**How it works**: Randomly or stratified division of data.

**Advantages**: Prevents overfitting, enables fair evaluation.

**Disadvantages**: Requires sufficient data.

**Alternatives**: Cross-validation.

**Why we selected it**: Standard practice for ML.

**Future improvements**: Use stratified splits for class balance.

---

#### Stratified Split
**What it is**: A dataset split that maintains the class distribution in each split.

**Why it's needed**: Ensures balanced representation across splits.

**How it works**: Splits data while maintaining class proportions.

**Advantages**: Prevents class imbalance in splits.

**Disadvantages**: More complex than random split.

**Alternatives**: Random split.

**Why we selected it**: Ensures balanced evaluation.

**Future improvements**: Use for all dataset splits.

---

#### Supervised Learning
**What it is**: Machine learning where models learn from labeled data. Input-output pairs are provided.

**Why it's needed**: Enables learning specific tasks from examples.

**How it works**: Model learns mapping from inputs to labeled outputs.

**Advantages**: Directly learns task-specific patterns.

**Disadvantages**: Requires labeled data.

**Alternatives**: Unsupervised learning, self-supervised learning.

**Why we selected it**: Primary learning paradigm for FAEAP.

**Future improvements**: Use semi-supervised learning to reduce label needs.

---

### T

#### Task Head
**What it is**: A neural network component specific to a particular task. In multi-task learning, each task has its own head.

**Why it's needed**: Enables model to perform multiple tasks.

**How it works**: Shared encoder feeds into task-specific heads.

**Advantages**: Enables multi-task learning.

**Disadvantages**: Adds complexity.

**Alternatives**: Single-task models.

**Why we selected it**: Essential for multi-task architecture.

**Future improvements**: Explore task relationships.

---

#### Temporal Localization
**What it is**: See "Localization".

---

#### Test Set
**What it is**: A portion of dataset held out from training and used only for final evaluation.

**Why it's needed**: Provides unbiased evaluation of model performance.

**How it works**: Not used during training or hyperparameter tuning.

**Advantages**: Unbiased performance estimate.

**Disadvantages**: Reduces data available for training.

**Alternatives**: Cross-validation.

**Why we selected it**: Standard practice for evaluation.

**Future improvements**: Use independent test set from different source.

---

#### Token
**What it is**: A discrete unit of representation. In BEATs, audio is converted to discrete tokens.

**Why it's needed**: Discrete representation enables certain learning approaches.

**How it works**: Continuous audio mapped to discrete tokens.

**Advantages**: Enables token-based learning.

**Disadvantages**: May lose fine-grained information.

**Alternatives**: Continuous embeddings.

**Why we selected it**: Not selected - AudioMAE uses continuous features.

**Future improvements**: Consider token-based approaches.

---

#### Training Set
**What it is**: A portion of dataset used to train the model.

**Why it's needed**: Provides data for model learning.

**How it works**: Model learns patterns from training data.

**Advantages**: Enables model learning.

**Disadvantages**: Must be representative of all data.

**Alternatives**: None - essential concept.

**Why we selected it**: Essential for model training.

**Future improvements**: Ensure training set diversity.

---

#### Transformer
**What it is**: A neural network architecture that uses self-attention mechanisms to process sequential data. State-of-the-art for many tasks.

**Why it's needed**: Provides powerful sequence modeling.

**How it works**: Self-attention captures relationships between all positions.

**Advantages**: State-of-the-art performance, handles long sequences.

**Disadvantages**: Computationally expensive for long sequences.

**Alternatives**: RNNs, CNNs.

**Why we selected it**: AudioMAE uses transformer architecture.

**Future improvements**: Explore efficient transformer variants.

---

#### Transfer Learning
**What it is**: Taking a model trained on one task and applying it to another related task. Fine-tuning is a type of transfer learning.

**Why it's needed**: Leverages knowledge from pre-trained models.

**How it works**: Pre-trained model adapted to new task.

**Advantages**: Faster training, less data needed, better performance.

**Disadvantages**: May not transfer well if tasks are unrelated.

**Alternatives**: Train from scratch.

**Why we selected it**: Essential for using AudioMAE.

**Future improvements**: Explore domain adaptation techniques.

---

### U

#### Underfitting
**What it is**: When a model is too simple to capture the underlying patterns in the data. Performs poorly on both training and test data.

**Why it's needed**: Problem to avoid in model training.

**How it works**: Model fails to learn patterns from data.

**Advantages**: None - this is a problem.

**Disadvantages**: Poor performance on all data.

**Alternatives**: Increase model complexity, train longer.

**Why we selected it**: Important problem to address.

**Future improvements**: Ensure model capacity sufficient for task.

---

#### Unsupervised Learning
**What it is**: Machine learning where models learn from unlabeled data without explicit supervision.

**Why it's needed**: Enables learning from unlabeled data.

**How it works**: Model finds patterns in unlabeled data.

**Advantages**: No labels needed, can discover hidden patterns.

**Disadvantages**: May not learn task-specific features.

**Alternatives**: Supervised learning, self-supervised learning.

**Why we selected it**: Not primary paradigm for FAEAP.

**Future improvements**: Use for data exploration.

---

### V

#### Validation Set
**What it is**: A portion of dataset used to tune hyperparameters and select models during training.

**Why it's needed**: Provides unbiased evaluation during development.

**How it works**: Used to monitor training and tune hyperparameters.

**Advantages**: Prevents overfitting to training set.

**Disadvantages**: Reduces data available for training.

**Alternatives**: Cross-validation.

**Why we selected it**: Standard practice for model development.

**Future improvements**: Use for hyperparameter tuning.

---

#### Vector
**What it is**: A mathematical object with magnitude and direction. In ML, vectors represent data as arrays of numbers.

**Why it's needed**: Numerical representation of data.

**How it works**: Data converted to array of numbers.

**Advantages**: Enables mathematical operations.

**Disadvantages**: High-dimensional vectors hard to interpret.

**Alternatives**: None - fundamental concept.

**Why we selected it**: Essential for ML.

**Future improvements**: Use dimensionality reduction for interpretability.

---

### W

#### Weight Decay
**What it is**: A regularization technique that adds a penalty to the loss function based on the magnitude of model weights.

**Why it's needed**: Prevents overfitting by discouraging large weights.

**How it works**: Adds λ × sum(weights²) to loss.

**Advantages**: Simple, effective regularization.

**Disadvantages**: Requires tuning of λ parameter.

**Alternatives**: L1 regularization, dropout.

**Why we selected it**: Standard regularization technique.

**Future improvements**: Use AdamW with decoupled weight decay.

---

#### Weights
**What it is**: Learnable parameters in neural networks that determine the strength of connections between neurons.

**Why it's needed**: Weights define model behavior.

**How it works**: Adjusted during training to minimize loss.

**Advantages**: Enable model learning.

**Disadvantages**: Many weights require much computation.

**Alternatives**: Fixed weights (not learned).

**Why we selected it**: Essential concept for neural networks.

**Future improvements**: Use parameter-efficient methods.

---

### X

#### XGBoost
**What it is**: An optimized distributed gradient boosting library. Not used in FAEAP but popular for tabular data.

**Why it's needed**: Not needed for FAEAP - for reference only.

**How it works**: Gradient boosting on decision trees.

**Advantages**: State-of-the-art for tabular data.

**Disadvantages**: Not suitable for audio.

**Alternatives**: Random Forest, LightGBM.

**Why we selected it**: Not selected - for reference only.

**Future improvements**: Not applicable.

---

### Y

#### YAML
**What it is**: A human-readable data serialization language. Often used for configuration files.

**Why it's needed**: Human-readable configuration format.

**How it works**: Uses indentation and key-value pairs.

**Advantages**: Human-readable, widely supported.

**Disadvantages**: Indentation-sensitive (can cause errors).

**Alternatives**: JSON, TOML.

**Why we selected it**: Standard for configuration files.

**Future improvements**: Use for all configuration files.

---

### Z

#### Zero-Shot Learning
**What it is**: Learning to recognize classes without seeing any examples during training. Uses auxiliary information like text descriptions.

**Why it's needed**: Enables recognition of new classes without retraining.

**How it works**: Learns from descriptions or attributes.

**Advantages**: Handles new classes without retraining.

**Disadvantages**: May not perform as well as supervised.

**Alternatives**: Few-shot learning, supervised learning.

**Why we selected it**: Not selected - potential future work.

**Future improvements**: Explore for new manipulation types.

---

## Conclusion

This glossary provides beginner-friendly explanations of technical terms used in the FAEAP project. Each term includes what it is, why it's needed, how it works, advantages, disadvantages, alternatives, why it was selected, and future improvements. The glossary serves as a reference for team members, stakeholders, and reviewers to understand the technical concepts involved in building a forensic audio authentication platform.
