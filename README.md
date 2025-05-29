Trained and evaluated fully connected neural networks to predict discrete star types from a handful of numeric and categorical features (e.g., temperature, luminosity, radius, color, spectral class).

---

## 🔑 Key Steps

1. **Data Loading & Encoding**  
   - Read CSV files with Pandas.  
   - Convert categorical columns (`Star color`, `Spectral Class`) to integer labels using `LabelEncoder`.  

2. **Feature Scaling**  
   - Standardize all inputs to zero mean and unit variance with `StandardScaler`.  

3. **Train/Test Split**  
   - Perform an 80/20 random split, with a fixed seed for reproducibility (`random_state=42`).  

4. **Model Implementations**  
   - **From-scratch MLP** (`scratch_nn.py`):  
     - Configurable depth and hidden-layer size  
     - ReLU activations and softmax output  
     - Cross-entropy loss, batch gradient descent  
   - **Keras/TensorFlow MLP** (`keras_nn.py`):  
     - Two hidden layers (16 units each) with ReLU and L2 regularization  
     - Dropout (30%) for additional regularization  
     - Early stopping on validation loss  

5. **Training & Evaluation**  
   - **Scratch MLP**: 3 hidden layers of 32 units, learning rate 0.01, 500 epochs.  
   - **Keras MLP**: trained up to 1,000 epochs with early stopping.  
   - **Kaggle dataset performance**: up to **98%** test accuracy on star-type classification.  
   - (NASA dataset results are analyzed in `analysis/correlation_heatmap.py` but did not reach the same high accuracy.)
