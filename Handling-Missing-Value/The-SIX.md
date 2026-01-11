# 1️⃣ Dropping Missing Data

### **When to use (real-world)**

* Missing rows < **5%**
* Missing is **completely random**
* Dataset is **large**
* Rows are **independent**
* Early **baseline / quick experiment**

### **When NOT to use**

* Small dataset
* Time series / logs
* Missing correlates with target
* Minority or important group affected

### **Interview-style answer**

> “I drop missing data only when missingness is rare, random, and deleting rows introduces less bias than guessing values.”

---

# 2️⃣ Constant Value Imputation

### **When to use (real-world)**

* Missing value itself has **meaning**
* Categorical features
* Tree-based models
* Streaming / real-time pipelines
* You want deterministic behavior

### **When NOT to use**

* Linear or distance-based models
* When constant overlaps with valid values

### **Interview-style answer**

> “I use constant imputation when missingness represents a real state, like ‘Unknown’, and especially with tree-based models.”

---

# 3️⃣ Statistical Imputation (Mean / Median / Mode)

### **When to use (real-world)**

* Missing percentage is **low**
* Missing is **random**
* Need a **fast baseline**
* Numerical → mean/median
* Categorical → mode

### **When NOT to use**

* Highly skewed data (mean)
* High missing percentage
* When missingness carries signal

### **Interview-style answer**

> “I use mean or median imputation as a baseline when missingness is random and small, choosing median for robustness to outliers.”

---

# 4️⃣ Group-Based (Conditional) Imputation

### **When to use (real-world)**

* Strong relationship between feature and group
* Demographics, geography, categories
* Business logic depends on context
* Enough data per group

### **When NOT to use**

* Small or sparse groups
* Unstable group distributions
* Leakage risk

### **Interview-style answer**

> “I use group-based imputation when the feature clearly depends on a category, like salary by job role, to reduce bias from global averages.”

---

# 5️⃣ Time-Based Imputation (Forward / Backward Fill)

### **When to use (real-world)**

* Time series data
* Slowly changing signals
* Logs, sensors, monitoring systems
* Real-time or streaming data

### **When NOT to use**

* Highly volatile signals
* Large time gaps
* First block of missing values

### **Interview-style answer**

> “I use forward or backward fill when temporal continuity matters and values change gradually over time.”

---

# 6️⃣ Missingness as a Feature (Indicator Method)

### **When to use (real-world)**

* Missingness is **predictive**
* Risk, fraud, credit, healthcare models
* MNAR (Not Missing at Random)
* Tree-based or complex models

### **When NOT to use**

* Purely random missingness
* Very small datasets
* Strong multicollinearity risk

### **Interview-style answer**

> “I add missingness indicators when the absence of data itself carries behavioral or business signal.”

---

# 🧠 One-Line Master Rule (Top-1% Thinking)

> **Drop when data is abundant and random.
> Impute when data is valuable.
> Flag when missingness tells a story.**
