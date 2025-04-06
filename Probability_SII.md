## 🔹 **1.1 Random Variables (RVs)**

### 🔸 What is a Random Variable?

A **Random Variable (RV)** is a variable that takes on numerical values based on the outcome of a random experiment.

There are **two types**:

| Type            | Description                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| **Discrete**    | Takes **countable** values (e.g., 0, 1, 2, …).                              |
| **Continuous**  | Takes **uncountably infinite** values within an interval (e.g., 1.3, 2.7). |

---

### 🔹 Examples

#### Discrete RV:
- Tossing a coin 3 times → Let $ X $ = number of heads.
  - Possible values of $ X $: {0, 1, 2, 3}
  
#### Continuous RV:
- Measuring the height of a person → Let $ Y $ = height in cm.
  - Possible values of $ Y $: Any real number between, say, 100 and 200.

---

### 🔸 Notation

- Random Variable: usually written in **uppercase** (e.g., $ X, Y $)
- Realized value: written in **lowercase** (e.g., $ x, y $)

> Example: If $ X $ is a random variable for dice roll, then $ P(X = 5) $ is the probability that the outcome is 5.

---

## 🔹 Key Differences (Discrete vs Continuous)

| Feature                 | Discrete RV                         | Continuous RV                          |
|-------------------------|-------------------------------------|----------------------------------------|
| Values                  | Countable (finite or infinite)      | Uncountably infinite                   |
| Representation          | **Probability Mass Function (PMF)** | **Probability Density Function (PDF)** |
| Total Probability       | $ \sum P(X = x) = 1 $             | $ \int f(x) \, dx = 1 $              |
| Probability at a point  | Non-zero $ P(X = x) > 0 $         | Zero $ P(X = x) = 0 $                |
| Example                 | Number of heads in 3 coin tosses    | Weight of a randomly chosen apple      |

---

### 📌 Important Realizations:

1. **Discrete RV**: We assign probability to each value.
   - $ P(X = x) $ is meaningful and non-zero.
2. **Continuous RV**: We assign probability over **intervals**, not single points.
   - $ P(X = x) = 0 $, but $ P(a \le X \le b) > 0 $

---

### 🎯 Quick Practice

**Q1:** Identify if the following RVs are discrete or continuous:

a. The number of messages you get in a day  
b. The temperature at noon in Islamabad  
c. The time it takes to solve a math problem  
d. The number of students in a class

👉 Answers:
- a: Discrete  
- b: Continuous  
- c: Continuous  
- d: Discrete

## 🔹 **1.2 Probability Mass Function (PMF)** – For Discrete Random Variables

### 🔸 Definition:

A **Probability Mass Function (PMF)** gives the probability that a **discrete** random variable is equal to a particular value.

$$
P(X = x) = p(x)
$$

It must satisfy:
1. $ p(x) \geq 0 $ for all $ x $
2. $ \sum_{x} p(x) = 1 $

---

### 🧠 Example 1: Tossing a fair coin twice

Let $ X $ be the number of heads.

- Sample space: {HH, HT, TH, TT}
- Values of $ X $: {0, 1, 2}
- PMF:

| $ x $ | 0   | 1   | 2   |
|--------|-----|-----|-----|
| $ p(x) $ | 1/4 | 2/4 | 1/4 |

$$
\sum p(x) = \frac{1}{4} + \frac{2}{4} + \frac{1}{4} = 1
$$

✅ This is a valid PMF.

---

### 🧠 Example 2: Rolling a fair die

Let $ X $ = outcome of the die.

- PMF: $ p(x) = \frac{1}{6} $ for $ x = 1, 2, 3, 4, 5, 6 $
- Not defined for other values.

---

## 🔹 **1.2 Probability Density Function (PDF)** – For Continuous Random Variables

### 🔸 Definition:

A **Probability Density Function (PDF)** is a function that describes the **relative likelihood** of a **continuous** random variable to take on a value within a certain interval.

$$
f(x) \ge 0 \quad \text{and} \quad \int_{-\infty}^{\infty} f(x)\,dx = 1
$$

👉 You **cannot** say $ P(X = x) $. Instead:

$$
P(a \le X \le b) = \int_a^b f(x) \, dx
$$

---

### 🧠 Example 1: Uniform Distribution over [0, 1]

$$
f(x) = \begin{cases}
1 & \text{if } 0 \le x \le 1 \\
0 & \text{otherwise}
\end{cases}
$$

Check:  
$$
\int_0^1 1 \, dx = 1 \Rightarrow \text{Valid PDF}
$$

Now:  
$$
P(0.2 \le X \le 0.5) = \int_{0.2}^{0.5} 1 \, dx = 0.5 - 0.2 = 0.3
$$

---

### 🧠 Example 2: Exponential Distribution (with $ \lambda = 1 $)

$$
f(x) = e^{-x}, \quad x \ge 0
$$

Check:  
$$
\int_0^\infty e^{-x} dx = 1
$$

This is a valid PDF.

---

## 📊 PMF vs PDF – Summary Table

| Feature               | PMF (Discrete)            | PDF (Continuous)                        |
|----------------------|---------------------------|-----------------------------------------|
| Definition            | $ P(X = x) $            | $ f(x) $ such that $ P(a \le X \le b) = \int_a^b f(x)\,dx $ |
| Total Probability     | $ \sum p(x) = 1 $       | $ \int f(x) dx = 1 $                  |
| Probability at a Point| Positive value possible   | Always 0                                |
| Example               | Dice roll, coin toss      | Height, weight, time                    |

---

### 🎯 Quick Check:

1. Is $ P(X = 1.5) $ meaningful for a **continuous** random variable?  
2. Can PMF ever be negative?  
3. What condition must a function satisfy to be a valid PDF?

👉 Answers:
1. ❌ No, $ P(X = 1.5) = 0 $ for continuous RVs  
2. ❌ No, PMF $ \ge 0 $  
3. ✅ $ f(x) \ge 0 $, and total area under curve = 1