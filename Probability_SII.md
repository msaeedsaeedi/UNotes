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

## 🔹 **1.3 Cumulative Distribution Function (CDF)**

### 🔸 Definition:

The **Cumulative Distribution Function (CDF)** of a random variable $ X $, denoted by $ F(x) $, gives the **probability that $ X $ takes a value less than or equal to $ x $:**

$$
F(x) = P(X \le x)
$$

> ✔️ This definition works for both **discrete** and **continuous** random variables.

---

## ✅ Properties of a CDF

| Property | Description |
|---------|-------------|
| **1.** $ 0 \le F(x) \le 1 $ | CDF is always between 0 and 1 |
| **2.** $ F(x) $ is **non-decreasing** | As $ x $ increases, $ F(x) $ does not decrease |
| **3.** $ \lim_{x \to -\infty} F(x) = 0 $ | Left tail → probability = 0 |
| **4.** $ \lim_{x \to \infty} F(x) = 1 $ | Right tail → total probability = 1 |
| **5.** For **continuous RV**, CDF is **continuous** |
| **6.** For **discrete RV**, CDF is **stepwise / jump function** |

---

## 🟪 For **Discrete Random Variables**

$$
F(x) = \sum_{t \le x} P(X = t)
$$

### 🧠 Example:

Toss 2 fair coins. Let $ X $ = number of heads. We already know:

| $ x $ | 0   | 1   | 2   |
|--------|-----|-----|-----|
| $ p(x) $ | 1/4 | 2/4 | 1/4 |

Compute CDF $ F(x) $:

| $ x $ | $ F(x) = P(X \le x) $ |
|--------|--------------------------|
| $ x < 0 $ | 0 |
| 0 | $ 1/4 $ |
| 1 | $ 1/4 + 2/4 = 3/4 $ |
| 2 | $ 1 $ |
| $ x > 2 $ | 1 |

Plot: The graph will look like a **staircase**.

---

## 🟨 For **Continuous Random Variables**

$$
F(x) = \int_{-\infty}^{x} f(t) \, dt
$$

### 🧠 Example:

Let $ f(x) = 1 $, for $ 0 \le x \le 1 $. (Uniform Distribution)

$$
F(x) = \begin{cases}
0 & x < 0 \\
\int_0^x 1 dt = x & 0 \le x \le 1 \\
1 & x > 1
\end{cases}
$$

✅ Check:
- $ F(0.4) = 0.4 $
- $ P(0.2 \le X \le 0.5) = F(0.5) - F(0.2) = 0.5 - 0.2 = 0.3 $

---

## 🔁 Recover PMF/PDF from CDF

| Type       | Formula to recover          |
|------------|-----------------------------|
| **Discrete**  | $ P(X = x) = F(x) - F(x^-) $ *(jump height)* |
| **Continuous**| $ f(x) = \frac{d}{dx} F(x) $ *(derivative)*  |

---

## 🎯 Practice Problems (Optional):

If you'd like, I can give you problems like:

> Given a stepwise CDF, determine the PMF.  
> Given a continuous CDF (e.g., $ F(x) = 1 - e^{-\lambda x} $), find the PDF and then calculate $ P(a < X < b) $.

Awesome! Let's now tackle a super important topic:

---

## ✅ **1.4: Expectation and Variance**

These are the **first and second moments** of a random variable — they measure **central tendency** and **spread**, respectively.

Your teacher may ask:
- Definitions for both discrete and continuous cases
- Full derivations
- Properties
- Applications in real-world scenarios
- Questions that combine expectation and variance with CDF/PMF/PDF

Let’s break it down step by step 👇

---

## 🔹 1.4.1 Expectation (Mean)

### 🔸 Definition:
The **expectation (mean)** of a random variable $ X $ is a **weighted average of all possible values** of $ X $.

---

### 🟪 For Discrete Random Variables:
$$
E[X] = \sum_x x \cdot p(x)
$$

Where:
- $ x $ = possible values of RV
- $ p(x) $ = PMF

---

### 🟨 For Continuous Random Variables:
$$
E[X] = \int_{-\infty}^{\infty} x \cdot f(x) \, dx
$$

Where:
- $ f(x) $ = PDF

---

### 🧠 Example 1 (Discrete):
Let $ X $ be the outcome of rolling a fair die.

$$
E[X] = \sum_{x=1}^{6} x \cdot \frac{1}{6} = \frac{1+2+3+4+5+6}{6} = 3.5
$$

---

### 🧠 Example 2 (Continuous):
Let $ f(x) = 2x $, $ 0 \le x \le 1 $.  
(Valid PDF: check that $ \int_0^1 2x dx = 1 $)

Now:
$$
E[X] = \int_0^1 x \cdot 2x \, dx = \int_0^1 2x^2 dx = \left[\frac{2x^3}{3}\right]_0^1 = \frac{2}{3}
$$

---

## 🔹 1.4.2 Variance

### 🔸 Definition:
Variance measures the **spread** of the random variable around the mean.

---

### Formula:
$$
\text{Var}(X) = E[(X - \mu)^2] = E[X^2] - (E[X])^2
$$

Where:
- $ \mu = E[X] $

---

### 🟪 For Discrete:
$$
\text{Var}(X) = \sum_x (x - \mu)^2 \cdot p(x) = \sum_x x^2 p(x) - (E[X])^2
$$

---

### 🟨 For Continuous:
$$
\text{Var}(X) = \int_{-\infty}^{\infty} (x - \mu)^2 f(x) \, dx = \int x^2 f(x) dx - (E[X])^2
$$

---

### 🧠 Example (Rolling a fair die):

We already have $ E[X] = 3.5 $

$$
E[X^2] = \sum_{x=1}^{6} x^2 \cdot \frac{1}{6} = \frac{1^2 + 2^2 + \dots + 6^2}{6} = \frac{91}{6}
$$

$$
\text{Var}(X) = E[X^2] - (E[X])^2 = \frac{91}{6} - (3.5)^2 = \frac{91}{6} - \frac{49}{4} = \frac{364 - 294}{24} = \frac{70}{24} = 2.9167
$$

---

## 🔁 Recap with a Table

| Concept   | Discrete Formula                | Continuous Formula                    |
|-----------|----------------------------------|----------------------------------------|
| $ E[X] $ | $ \sum x \cdot p(x) $          | $ \int x \cdot f(x) \, dx $          |
| $ E[X^2] $ | $ \sum x^2 \cdot p(x) $        | $ \int x^2 \cdot f(x) \, dx $        |
| $ \text{Var}(X) $ | $ E[X^2] - (E[X])^2 $        | $ E[X^2] - (E[X])^2 $                |
| $ \sigma $ (SD) | $ \sqrt{\text{Var}(X)} $ | $ \sqrt{\text{Var}(X)} $             |

---

## 🎯 Common Pitfalls:
- Don’t forget to square **only** after integrating or summing.
- Expectation is **linear**, but variance is **not**.
- Always validate the **domain** and **PDF/PMF sum or integral** first.

## ✅ **1.5: Properties of Expectation and Variance**

We'll cover:
- Linearity of Expectation
- Variance of a Linear Combination
- Scaling and Shifting Rules
- Expectations and Variances of Sums
- Independent variable properties

---

## 🔷 1.5.1 Properties of Expectation

Expectation is **linear**, whether the variables are independent or not.

### 📌 Property 1: **Linearity**
$$
E[aX + b] = aE[X] + b
$$
- $ a, b \in \mathbb{R} $ (constants)
- Holds for **both discrete and continuous** random variables

### 🧠 Example:
Let $ E[X] = 5 $

Then,
$$
E[3X + 2] = 3 \cdot 5 + 2 = 17
$$

---

### 📌 Property 2: Expectation of a Sum
$$
E[X + Y] = E[X] + E[Y]
$$
- True **regardless of independence**

$$
E\left[\sum_{i=1}^n X_i\right] = \sum_{i=1}^n E[X_i]
$$

---

### 📌 Property 3: Expectation of a Constant
$$
E[c] = c
$$
If $ X $ is always equal to $ c $, then its expected value is $ c $.

---

### 📌 Property 4: Expectation of a Product (If Independent)
$$
E[XY] = E[X] \cdot E[Y] \quad \text{if } X, Y \text{ are independent}
$$

This does **not** hold if $ X, Y $ are dependent.

---

## 🔶 1.5.2 Properties of Variance

Variance is **not** linear like expectation. Be careful!

---

### 📌 Property 1: Variance of a Constant
$$
\text{Var}(c) = 0
$$

---

### 📌 Property 2: Scaling Rule
$$
\text{Var}(aX) = a^2 \cdot \text{Var}(X)
$$

- Scaling affects variance **quadratically**

---

### 📌 Property 3: Shifting Rule
$$
\text{Var}(X + c) = \text{Var}(X)
$$

- Adding a constant shifts the data but doesn't change the spread

---

### 📌 Property 4: Variance of a Linear Combination
Let $ Y = aX + b $

$$
\text{Var}(aX + b) = a^2 \cdot \text{Var}(X)
$$

---

### 📌 Property 5: Variance of Sum (Independent)
$$
\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y) \quad \text{if } X, Y \text{ are independent}
$$

$$
\text{Var}\left(\sum_{i=1}^n X_i\right) = \sum_{i=1}^n \text{Var}(X_i) \quad \text{(for independent variables)}
$$

---

### 📌 Property 6: If Not Independent
$$
\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y) + 2 \cdot \text{Cov}(X, Y)
$$

We’ll explore **Covariance** in more detail in joint distributions.

---

## 🎯 Summary Table

| Operation                      | Expectation                      | Variance                          |
|-------------------------------|----------------------------------|-----------------------------------|
| $ E[aX + b] $               | $ aE[X] + b $                  | $ a^2 \text{Var}(X) $           |
| $ E[X + Y] $                | $ E[X] + E[Y] $                | $ \text{Var}(X) + \text{Var}(Y) $ *(if ind.)* |
| $ E[c] $                    | $ c $                          | $ 0 $                           |
| $ \text{Var}(X + c) $       | -                                | $ \text{Var}(X) $               |
| $ \text{Var}(X + Y) $       | -                                | $ \text{Var}(X) + \text{Var}(Y) + 2\text{Cov}(X,Y) $ |

---

## 🧠 Typical Exam Question:
> Let $ E[X] = 3, \text{Var}(X) = 4 $. Let $ Y = 5X + 2 $. Find $ E[Y] $, $ \text{Var}(Y) $.

**Solution**:
- $ E[Y] = 5E[X] + 2 = 5(3) + 2 = 17 $
- $ \text{Var}(Y) = 25 \cdot \text{Var}(X) = 25 \cdot 4 = 100 $

## ✅ **1.6: Moments (About the Mean and Origin)**

Moments describe the **shape** and **features** of a probability distribution:
- **Central moments** focus on spread around the **mean**
- **Raw moments** are about spread around the **origin (0)**

---

## 🔹 1.6.1 What is a Moment?

The $ r $-th moment of a random variable $ X $ is defined as:

### 🔸 About the Origin:
$$
\mu'_r = E[X^r]
$$

### 🔸 About the Mean (Central Moment):
$$
\mu_r = E[(X - \mu)^r]
$$
Where $ \mu = E[X] $

---

## 🔸 Interpretation of First Few Moments:

| Moment | About Origin            | About Mean (Central)             | Interpretation                  |
|--------|--------------------------|----------------------------------|---------------------------------|
| 1st    | $ E[X] $              | $ 0 $                          | Mean (location of distribution) |
| 2nd    | $ E[X^2] $            | $ \text{Var}(X) $              | Spread (variance)               |
| 3rd    | $ E[X^3] $            | $ E[(X - \mu)^3] $             | Skewness (symmetry)             |
| 4th    | $ E[X^4] $            | $ E[(X - \mu)^4] $             | Kurtosis (peakedness)           |

---

## 🔹 1.6.2 Raw Moments (About Origin)

$$
\mu'_1 = E[X], \quad \mu'_2 = E[X^2], \quad \mu'_3 = E[X^3], \quad \mu'_4 = E[X^4]
$$

These are easier to compute directly from PMF/PDF.

---

### 🧠 Example (Discrete):
Let $ X $ have values $ 1, 2, 3 $ with probabilities $ \frac{1}{6}, \frac{1}{2}, \frac{1}{3} $

**Step 1: First raw moment**
$$
\mu'_1 = E[X] = 1 \cdot \frac{1}{6} + 2 \cdot \frac{1}{2} + 3 \cdot \frac{1}{3} = \frac{1}{6} + 1 + 1 = \frac{13}{6}
$$

**Step 2: Second raw moment**
$$
\mu'_2 = E[X^2] = 1^2 \cdot \frac{1}{6} + 2^2 \cdot \frac{1}{2} + 3^2 \cdot \frac{1}{3} = \frac{1}{6} + 2 + 3 = \frac{31}{6}
$$

---

## 🔹 1.6.3 Central Moments (About Mean)

$$
\mu_2 = E[(X - \mu)^2] = \text{Var}(X)
$$

$$
\mu_3 = E[(X - \mu)^3] \quad \text{(Skewness)}
$$

$$
\mu_4 = E[(X - \mu)^4] \quad \text{(Kurtosis)}
$$

---

### 🧠 Example (Using Earlier Data):

Let’s reuse:
- $ \mu = \mu'_1 = \frac{13}{6} $
- $ \mu'_2 = \frac{31}{6} $

Now compute:
$$
\mu_2 = \text{Var}(X) = E[X^2] - (E[X])^2 = \frac{31}{6} - \left(\frac{13}{6}\right)^2 = \frac{31}{6} - \frac{169}{36}
$$

To subtract:
$$
\frac{31}{6} = \frac{186}{36}, \quad \Rightarrow \mu_2 = \frac{186 - 169}{36} = \frac{17}{36}
$$

---

## 🎯 Summary

| Moment      | Formula                              | Use                         |
|-------------|---------------------------------------|------------------------------|
| Raw moment  | $ \mu'_r = E[X^r] $                | Simpler to compute           |
| Central moment | $ \mu_r = E[(X - \mu)^r] $         | Describes distribution shape |
| Variance    | $ \mu_2 $                          | Spread                       |
| Skewness    | $ \mu_3 $                          | Asymmetry                    |
| Kurtosis    | $ \mu_4 $                          | Peakedness                   |

## ✅ **1.7: Moment Generating Functions (MGF)**

MGFs are not just theoretical—they’re used to:
- Derive **all moments** of a distribution
- Identify distributions (like a fingerprint)
- Prove convergence in probability theory

Let’s understand this step-by-step:

---

## 🔹 1.7.1 Definition

For a random variable $ X $, the **Moment Generating Function (MGF)** is:

$$
M_X(t) = E[e^{tX}]
$$

> If the MGF exists in a neighborhood around $ t = 0 $, then:
$$
\text{The } r\text{-th moment of } X = M_X^{(r)}(0) = \left.\frac{d^r}{dt^r} M_X(t)\right|_{t=0}
$$

---

## 🔸 1.7.2 Why is it Called “Moment Generating”?

MGF **generates moments** by differentiating:
- First derivative gives **first moment** (mean)
- Second derivative gives **second raw moment**
- And so on

---

### 🔸 Properties of MGF:

| Property | Description |
|----------|-------------|
| $ M_X(0) = 1 $ | Always holds |
| $ M_{aX + b}(t) = e^{bt} \cdot M_X(at) $ | Linear transformation |
| If $ X $ and $ Y $ are independent → $ M_{X+Y}(t) = M_X(t) \cdot M_Y(t) $ | Used for sums |

---

## 🔹 1.7.3 Step-by-Step Example (Discrete)

Let’s find MGF of a discrete RV:

### 🎲 Example: Let $ X $ take values $ 0, 1 $ with $ P(X=0)=0.4, \ P(X=1)=0.6 $

Step 1: Write the definition:
$$
M_X(t) = E[e^{tX}] = \sum_x e^{tx} \cdot P(X = x)
$$

Step 2: Plug values:
$$
M_X(t) = e^{t \cdot 0} \cdot 0.4 + e^{t \cdot 1} \cdot 0.6 = 0.4 + 0.6e^t
$$

---

### ✅ Mean from MGF:
Differentiate and plug $ t = 0 $

$$
M'_X(t) = 0.6e^t \quad \Rightarrow M'_X(0) = 0.6
\Rightarrow E[X] = 0.6
$$

---

### ✅ Second Moment:
$$
M''_X(t) = 0.6e^t \Rightarrow M''_X(0) = 0.6
\Rightarrow E[X^2] = 0.6
$$

### ✅ Variance:
$$
\text{Var}(X) = E[X^2] - (E[X])^2 = 0.6 - (0.6)^2 = 0.6 - 0.36 = 0.24
$$

---

## 🔹 1.7.4 Step-by-Step Example (Continuous)

### 🔍 Let $ X \sim \text{Exponential}(\lambda) $, PDF:  
$$
f(x) = \lambda e^{-\lambda x}, \quad x \geq 0
$$

Find MGF:
$$
M_X(t) = E[e^{tX}] = \int_0^\infty e^{tx} \cdot \lambda e^{-\lambda x} \, dx
= \lambda \int_0^\infty e^{(t - \lambda)x} \, dx
$$

This converges **only when $ t < \lambda $**:
$$
M_X(t) = \frac{\lambda}{\lambda - t}
$$

From here:
- $ M'_X(0) = \frac{\lambda}{(\lambda - 0)^2} = \frac{1}{\lambda} $
- So, $ E[X] = \frac{1}{\lambda} $
- And $ \text{Var}(X) = \frac{1}{\lambda^2} $

---

## 🎯 Summary

| Feature | Formula / Insight |
|--------|-------------------|
| Definition | $ M_X(t) = E[e^{tX}] $ |
| 1st moment | $ M'_X(0) = E[X] $ |
| 2nd moment | $ M''_X(0) = E[X^2] $ |
| Variance | $ M''_X(0) - (M'_X(0))^2 $ |
| MGF of sum | $ M_{X+Y}(t) = M_X(t) \cdot M_Y(t) $ (if independent) |

---

## 🧠 Tips:
- **Always check convergence range** of MGF.
- When asked about MGF in exams, **differentiate clearly** and show evaluation at $ t = 0 $.
- For known distributions, memorize MGFs for speed (Bernoulli, Binomial, Poisson, etc.)

## ✅ **1.8: Cumulant Generating Functions (CGF)**

Cumulants are an alternative to moments and give **deeper insights** into the distribution's structure—like **skewness**, **kurtosis**, etc.

---

## 🔹 1.8.1 What is the Cumulant Generating Function?

The **Cumulant Generating Function (CGF)** is the natural logarithm of the MGF:

$$
K_X(t) = \ln M_X(t)
$$

- If the MGF exists in a neighborhood around $ t = 0 $, then the CGF is also defined.
- Cumulants are generated by **differentiating the CGF**, just like how moments are from the MGF.

---

## 🔹 1.8.2 First Few Cumulants

$$
\kappa_1 = K'_X(0) = \text{Mean}
$$  
$$
\kappa_2 = K''_X(0) = \text{Variance}
$$  
$$
\kappa_3 = K^{(3)}_X(0) = \text{Measure of Skewness (shape)}
$$  
$$
\kappa_4 = K^{(4)}_X(0) = \text{Related to Kurtosis}
$$

> So, **first cumulant = mean**, **second = variance**, and **third & fourth** describe **shape** of the distribution.

---

## 🔹 1.8.3 Why Do We Use CGF?

| Purpose | Explanation |
|--------|-------------|
| 🧠 Simpler Algebra | Log of products = sum of logs, so easier with sums of RVs |
| ➕ Additive Property | Cumulants of sum = sum of cumulants |
| 🎯 Shape Insights | Higher-order cumulants describe distribution shape (like skewness & kurtosis) |
| 💡 Less Sensitive | Cumulants are often more stable than moments in extreme values |

---

## 🔍 Example: Use CGF to Find Mean and Variance

Let’s say you already found an MGF:

$$
M_X(t) = 0.4 + 0.6e^t
$$

So the CGF is:

$$
K_X(t) = \ln(0.4 + 0.6e^t)
$$

To find cumulants:

### Step 1: Differentiate once (mean)
$$
K'_X(t) = \frac{d}{dt} \ln(0.4 + 0.6e^t) = \frac{0.6e^t}{0.4 + 0.6e^t}
$$
$$
K'_X(0) = \frac{0.6}{0.4 + 0.6} = 0.6 \Rightarrow \kappa_1 = \text{Mean} = 0.6
$$

---

### Step 2: Differentiate again (variance)
Apply quotient rule:
$$
K''_X(t) = \frac{(0.6e^t)(0.4 + 0.6e^t) - (0.6e^t)^2}{(0.4 + 0.6e^t)^2}
$$

At $ t = 0 $:
$$
K''_X(0) = \frac{0.6(0.4 + 0.6) - 0.36}{(1)^2} = 0.6 - 0.36 = 0.24
\Rightarrow \kappa_2 = \text{Variance}
$$

---

## 🎯 Summary Table

| Cumulant | Formula | Meaning |
|----------|---------|---------|
| $ \kappa_1 $ | $ K'_X(0) $ | Mean |
| $ \kappa_2 $ | $ K''_X(0) $ | Variance |
| $ \kappa_3 $ | $ K^{(3)}_X(0) $ | Skewness indicator |
| $ \kappa_4 $ | $ K^{(4)}_X(0) $ | Kurtosis indicator |

---

## 🧠 Tips:
- **Moments and cumulants** match for the first two (mean and variance).
- Cumulants are **additive for independent RVs**, so they’re useful in sum-based problems.
- You **don’t need to memorize higher derivatives**—focus on how to use CGF for mean/variance.

## ✅ **1.9: Measures of Central Tendency for Random Variables**

We’ve already talked about **expectation (mean)** as a measure of central tendency. Now, we’ll cover:

- Median  
- Mode  
- Quartiles  

These are often overlooked for random variables, but **your teacher might ask** them in a tricky way—so we’ll go **step-by-step**.

---

## 🔹 1.9.1 Mean (Quick Recap)

| Type | Formula |
|------|---------|
| Discrete | $ \mu = E[X] = \sum x \cdot P(X=x) $ |
| Continuous | $ \mu = E[X] = \int x \cdot f(x) \, dx $ |

Mean is the **expected center**, but it’s sensitive to **extreme values**.

---

## 🔹 1.9.2 Median of a Random Variable

**Definition:** The median is the value $ m $ such that:

$$
P(X \leq m) \geq 0.5 \quad \text{and} \quad P(X \geq m) \geq 0.5
$$

> Median is the **middle** of the distribution and **less sensitive** to outliers than the mean.

---

### 🔸 Example (Discrete)

Let $ X $ have this PMF:

| $ X $ | 1 | 2 | 3 | 4 | 5 |
|--------|---|---|---|---|---|
| $ P(X=x) $ | 0.1 | 0.2 | 0.4 | 0.2 | 0.1 |

Compute CDF:

| $ x $ | CDF $ P(X \leq x) $ |
|--------|-----------------------|
| 1 | 0.1 |
| 2 | 0.3 |
| 3 | 0.7 |
| 4 | 0.9 |
| 5 | 1.0 |

➡️ Median is the **first value where CDF ≥ 0.5**, so median = **3**

---

### 🔸 Example (Continuous)

Let $ X \sim \text{Uniform}(0, 2) $

Then PDF:
$$
f(x) = \frac{1}{2}, \quad 0 \leq x \leq 2
$$

To find median:

$$
P(X \leq m) = \int_0^m \frac{1}{2} dx = \frac{m}{2} = 0.5
\Rightarrow m = 1
$$

➡️ Median = **1**

---

## 🔹 1.9.3 Mode of a Random Variable

**Definition:** The mode is the value $ x $ at which the **PMF or PDF** is maximized.

---

### 🔸 Discrete Example

Same PMF:

| $ X $ | 1 | 2 | 3 | 4 | 5 |
|--------|---|---|---|---|---|
| $ P(X=x) $ | 0.1 | 0.2 | 0.4 | 0.2 | 0.1 |

Here, max probability is at $ x = 3 $

➡️ Mode = **3**

---

### 🔸 Continuous Example

Let $ X \sim \text{Exponential}(\lambda) $, PDF:

$$
f(x) = \lambda e^{-\lambda x}, \quad x \geq 0
$$

This function is **maximum at $ x = 0 $**

➡️ Mode = **0**

---

## 🔹 1.9.4 Quartiles of a Random Variable

Quartiles split the distribution into four parts.

- $ Q_1 $: First quartile (25% of values ≤ this)
- $ Q_2 $: Median (50%)
- $ Q_3 $: Third quartile (75%)

---

### 🔸 Discrete Example

From earlier:

| $ x $ | 1 | 2 | 3 | 4 | 5 |
|--------|---|---|---|---|---|
| $ P(X=x) $ | 0.1 | 0.2 | 0.4 | 0.2 | 0.1 |
| CDF | 0.1 | 0.3 | 0.7 | 0.9 | 1.0 |

- $ Q_1 $: First value with CDF ≥ 0.25 → **2**
- $ Q_2 $: Median → **3**
- $ Q_3 $: First value with CDF ≥ 0.75 → **4**

---

### 🔸 Continuous Example: Uniform(0, 2)

PDF: $ f(x) = \frac{1}{2} $

To find $ Q_1 $:

$$
P(X \leq Q_1) = 0.25 = \int_0^{Q_1} \frac{1}{2} dx = \frac{Q_1}{2}
\Rightarrow Q_1 = 0.5
$$

Similarly:

- $ Q_2 = 1 $ (median)
- $ Q_3 = 1.5 $

---

## 🎯 Summary Table

| Measure | Meaning | How to Find |
|--------|---------|-------------|
| **Mean** | Average | $ E[X] $ |
| **Median** | Middle | Solve $ P(X \leq m) = 0.5 $ |
| **Mode** | Most probable | Max of PMF/PDF |
| **Quartiles** | 25%, 50%, 75% points | Solve $ P(X \leq Q_i) = i/4 $ |

---

## 🧠 Tips for Exams:
- Use **CDFs** to find medians and quartiles (discrete or continuous).
- If the PMF is **symmetrical**, mean = median = mode.
- Quartiles are especially useful when asked for **IQR (Interquartile Range) = Q3 - Q1**.

---

That completes **Part 1** of your syllabus in full detail! 🎉  
We covered:

- Discrete & Continuous RVs  
- PMF/PDF, CDF  
- Expectation, Variance  
- Properties  
- Moments  
- MGF & CGF  
- Median, Mode, Quartiles  

## ✅ **2.1: Joint Distributions of Discrete and Continuous Random Variables**

When studying multiple random variables together (like $ X $ and $ Y $), we use **joint distributions** to understand how they behave together.

---

## 🔷 2.1.1 Joint Probability Mass Function (Joint PMF) — *Discrete Case*

If $ X $ and $ Y $ are discrete random variables, their **joint PMF** is:

$$
P(X = x, Y = y) = \text{Probability that } X = x \text{ and } Y = y
$$

It satisfies:
1. $ P(X = x_i, Y = y_j) \geq 0 $
2. $ \sum_i \sum_j P(X = x_i, Y = y_j) = 1 $

---

### 🔸 Example (Joint PMF Table)

Let’s say $ X \in \{1, 2\}, Y \in \{0, 1\} $, and:

| $ P(X = x, Y = y) $ | $ Y = 0 $ | $ Y = 1 $ |
|------------------------|------------|------------|
| $ X = 1 $           | 0.2        | 0.3        |
| $ X = 2 $           | 0.1        | 0.4        |

Check:
$$
0.2 + 0.3 + 0.1 + 0.4 = 1 ✅
$$

---

## 🔷 2.1.2 Joint Probability Density Function (Joint PDF) — *Continuous Case*

If $ X $ and $ Y $ are continuous random variables, then their **joint PDF** is a function $ f(x, y) $ such that:

$$
P((X, Y) \in A) = \iint_A f(x, y) \, dx\,dy
$$

It must satisfy:

1. $ f(x, y) \geq 0 $
2. $ \iint_{-\infty}^\infty f(x, y)\,dx\,dy = 1 $

---

### 🔸 Example (Joint PDF)

Let:

$$
f(x, y) = 
\begin{cases}
4xy, & 0 \leq x \leq 1,\, 0 \leq y \leq 1 \\
0, & \text{otherwise}
\end{cases}
$$

Let’s verify it’s a valid joint PDF:

$$
\iint_0^1 \int_0^1 4xy\,dx\,dy = \int_0^1 \left[2x^2 y\right]_0^1 dy = \int_0^1 2y\,dy = \left[y^2\right]_0^1 = 1 ✅
$$

---

## 🧠 Real-Life Interpretation

Let’s say:
- $ X $ = time someone studies per day
- $ Y $ = number of assignments completed

A joint distribution shows how **time and performance** relate.

For instance:
- $ P(X = 2, Y = 4) = 0.1 $ means there's a 10% chance the student studies 2 hours and completes 4 assignments.

---

## 🎯 Summary Table

| Concept | Discrete | Continuous |
|--------|----------|------------|
| Joint Function | $ P(X = x, Y = y) $ | $ f(x, y) $ |
| Total Sum | $ \sum_x \sum_y P(x, y) = 1 $ | $ \iint f(x, y)\,dx\,dy = 1 $ |
| Probability in Region | Sum of entries | Double integral over region |

## ✅ **2.2: Marginal Distributions**

**Marginal distribution** gives us the probability distribution of a single random variable *ignoring* the other one.

Basically:  
> From the **joint distribution**, we "sum out" or "integrate out" the other variable.

---

## 🔷 2.2.1 Marginal Distribution (Discrete Case)

Given the **joint PMF** $ P(X = x_i, Y = y_j) $, the **marginal PMF** of $ X $ is:

$$
P_X(x_i) = \sum_j P(X = x_i, Y = y_j)
$$

Similarly, the **marginal PMF** of $ Y $ is:

$$
P_Y(y_j) = \sum_i P(X = x_i, Y = y_j)
$$

---

### 🔸 Example (From a Joint PMF Table)

| $ P(X = x, Y = y) $ | $ Y = 0 $ | $ Y = 1 $ | Marginal $ P_X(x) $ |
|------------------------|------------|------------|------------------------|
| $ X = 1 $           | 0.2        | 0.3        | 0.2 + 0.3 = **0.5**    |
| $ X = 2 $           | 0.1        | 0.4        | 0.1 + 0.4 = **0.5**    |
| Marginal $ P_Y(y) $ | 0.3        | 0.7        |                        |

$$
\text{Check: } \sum P_X(x) = 0.5 + 0.5 = 1 ✅,\quad \sum P_Y(y) = 0.3 + 0.7 = 1 ✅
$$

---

## 🔷 2.2.2 Marginal Distribution (Continuous Case)

Given a **joint PDF** $ f(x, y) $, the **marginal PDF** of $ X $ is:

$$
f_X(x) = \int_{-\infty}^{\infty} f(x, y) \, dy
$$

And for $ Y $:

$$
f_Y(y) = \int_{-\infty}^{\infty} f(x, y) \, dx
$$

---

### 🔸 Example

Let:
$$
f(x, y) = 4xy, \quad 0 \leq x \leq 1,\ 0 \leq y \leq 1
$$

Find the marginal PDF of $ X $:

$$
f_X(x) = \int_0^1 4xy \, dy = 4x \int_0^1 y \, dy = 4x \cdot \left[ \frac{y^2}{2} \right]_0^1 = 4x \cdot \frac{1}{2} = 2x
$$

So,
$$
f_X(x) = 
\begin{cases}
2x, & 0 \leq x \leq 1 \\
0, & \text{otherwise}
\end{cases}
$$

Similarly:
$$
f_Y(y) = \int_0^1 4xy \, dx = 4y \int_0^1 x \, dx = 4y \cdot \frac{1}{2} = 2y
$$

---

## 🧠 Real-Life Analogy

Suppose you record data about:
- $ X $ = number of hours studied
- $ Y $ = number of assignments submitted

If you only care about **how many hours were studied**, no matter how many assignments were done, you'd compute the **marginal distribution of $ X $** by **summing over** $ Y $.

---

## ✅ Quick Summary

| Type | Joint | Marginal of X | Marginal of Y |
|------|-------|----------------|----------------|
| Discrete | $ P(x, y) $ | $ \sum_y P(x, y) $ | $ \sum_x P(x, y) $ |
| Continuous | $ f(x, y) $ | $ \int f(x, y)\,dy $ | $ \int f(x, y)\,dx $ |

## ✅ **2.3: Conditional Distributions**

Conditional distributions tell us how the probability of one variable behaves *under the condition* that we know the value of the other variable.

---

## 🔷 2.3.1 Discrete Case — Conditional PMF

Let $ X $ and $ Y $ be discrete random variables with a known **joint PMF** $ P(X = x, Y = y) $.

Then the **conditional probability** of $ X = x $ given $ Y = y $ is:

$$
P(X = x \mid Y = y) = \frac{P(X = x, Y = y)}{P_Y(y)} \quad \text{(if } P_Y(y) > 0 \text{)}
$$

Likewise:
$$
P(Y = y \mid X = x) = \frac{P(X = x, Y = y)}{P_X(x)}
$$

---

### 🔸 Example

Using the same table from earlier:

| $ P(X = x, Y = y) $ | $ Y = 0 $ | $ Y = 1 $ | $ P_X(x) $ |
|------------------------|------------|------------|---------------|
| $ X = 1 $           | 0.2        | 0.3        | 0.5           |
| $ X = 2 $           | 0.1        | 0.4        | 0.5           |
| $ P_Y(y) $          | 0.3        | 0.7        |               |

Now:
- $ P(X = 1 \mid Y = 1) = \frac{0.3}{0.7} = \frac{3}{7} $
- $ P(Y = 0 \mid X = 2) = \frac{0.1}{0.5} = \frac{1}{5} $

✅ Always check the denominator is not zero.

---

## 🔷 2.3.2 Continuous Case — Conditional PDF

Let $ f(x, y) $ be a joint PDF. Then:

$$
f_{X \mid Y}(x \mid y) = \frac{f(x, y)}{f_Y(y)} \quad \text{(if } f_Y(y) > 0 \text{)}
$$

Similarly:

$$
f_{Y \mid X}(y \mid x) = \frac{f(x, y)}{f_X(x)}
$$

---

### 🔸 Example

Given:

$$
f(x, y) = 4xy,\quad 0 \le x, y \le 1
$$
Previously we found:
- $ f_X(x) = 2x $
- $ f_Y(y) = 2y $

Now:

$$
f_{X \mid Y}(x \mid y) = \frac{f(x, y)}{f_Y(y)} = \frac{4xy}{2y} = 2x
\quad \text{(as long as } y > 0\text{)}
$$

$$
f_{Y \mid X}(y \mid x) = \frac{4xy}{2x} = 2y
\quad \text{(as long as } x > 0\text{)}
$$

💡 Notice: The conditional PDFs are the same as marginals in this case — this hints at independence (we’ll get to that next!).

---

## 🎯 Interpretation in Real Life

Imagine you want to know:
> “What is the distribution of **hours studied (X)** given that a student submitted **4 assignments (Y = 4)**?”

You’d use the **conditional distribution** of $ X \mid Y = 4 $.

This helps us **narrow down** the behavior of one variable when another is fixed.

---

## 🔁 Comparison Summary

| Type | Conditional Formula |
|------|---------------------|
| Discrete | $ P(X = x \mid Y = y) = \frac{P(X = x, Y = y)}{P_Y(y)} $ |
| Continuous | $ f_{X \mid Y}(x \mid y) = \frac{f(x, y)}{f_Y(y)} $ |

## ✅ **2.4: Independence of Random Variables**

Two random variables are **independent** if *knowing the value of one gives no information about the other*.  
In other words:  
> The behavior of one does **not depend** on the other.

---

## 🔷 2.4.1 Independence — Discrete Case

Let $ X $ and $ Y $ be discrete random variables.

### 👉 Definition:

$ X $ and $ Y $ are **independent** if and only if:

$$
P(X = x, Y = y) = P_X(x) \cdot P_Y(y) \quad \text{for all } x, y
$$

That is, the **joint PMF** equals the **product of the marginals**.

---

### 🔸 Example:

From earlier:

| $ P(X = x, Y = y) $ | $ Y = 0 $ | $ Y = 1 $ | $ P_X(x) $ |
|------------------------|------------|------------|--------------|
| $ X = 1 $           | 0.2        | 0.3        | 0.5          |
| $ X = 2 $           | 0.1        | 0.4        | 0.5          |
| $ P_Y(y) $          | 0.3        | 0.7        |              |

Check:  
$ P(X = 1, Y = 0) = 0.2 $  
$ P_X(1) \cdot P_Y(0) = 0.5 \cdot 0.3 = 0.15 \ne 0.2 $

❌ So, **not independent**

---

## 🔷 2.4.2 Independence — Continuous Case

Let $ X $ and $ Y $ be continuous random variables.

### 👉 Definition:

$ X $ and $ Y $ are **independent** if and only if:

$$
f(x, y) = f_X(x) \cdot f_Y(y) \quad \text{for all } x, y
$$

So again, the **joint PDF** must be the **product of marginals**.

---

### 🔸 Example:

Let:
$$
f(x, y) = 4xy,\quad 0 \le x, y \le 1
$$

From earlier:
- $ f_X(x) = 2x $
- $ f_Y(y) = 2y $

Now:
$$
f(x, y) = 4xy = 2x \cdot 2y = f_X(x) \cdot f_Y(y)
$$

✅ So, **independent**

---

## 🔁 Shortcut: Conditional Distribution Test

Another way to check independence:

$$
P(X = x \mid Y = y) = P_X(x) \quad \text{(for discrete)}
$$
$$
f_{X \mid Y}(x \mid y) = f_X(x) \quad \text{(for continuous)}
$$

If the **conditional distribution equals the marginal**, the variables are **independent**.

---

## 🎯 Real-Life Example

Let:
- $ X $ = number of hours a student sleeps
- $ Y $ = marks in a math quiz

If we find that knowing how much they sleep **does not change** the probability distribution of their marks, then $ X $ and $ Y $ are **independent**.

But usually, there **is** some dependence in real life!

---

## ✅ Summary Table

| Type | Independence Condition |
|------|------------------------|
| Discrete | $ P(X = x, Y = y) = P_X(x) \cdot P_Y(y) $ |
| Continuous | $ f(x, y) = f_X(x) \cdot f_Y(y) $ |

## ✅ **2.5: Variance and Covariance**

---

## 🔷 2.5.1 Variance Recap (for a Single RV)

For a single random variable $ X $, we define:

$$
\operatorname{Var}(X) = E[(X - \mu_X)^2] = E[X^2] - (E[X])^2
$$

It tells us **how much the values of X deviate from the mean**.

---

## 🔷 2.5.2 Covariance — Measuring Linear Relationship

Covariance tells us **how two random variables vary together**.

$$
\operatorname{Cov}(X, Y) = E[(X - \mu_X)(Y - \mu_Y)]
$$

Alternate formula:

$$
\operatorname{Cov}(X, Y) = E[XY] - E[X]E[Y]
$$

---

### 🟩 Interpretation:

- **Positive Covariance**: When $ X $ increases, $ Y $ tends to increase.
- **Negative Covariance**: When $ X $ increases, $ Y $ tends to decrease.
- **Zero Covariance**: No linear relationship.

> Covariance gives the **direction** of the relationship, but **not strength or scale**.

---

### 🔸 Example (Discrete Case)

| $ (X, Y) $ | $ P(X, Y) $ |
|-------------|---------------|
| (1, 1)       | 0.25          |
| (1, 3)       | 0.25          |
| (3, 1)       | 0.25          |
| (3, 3)       | 0.25          |

Find:
- $ E[X] = 0.25(1 + 1 + 3 + 3) = 2 $
- $ E[Y] = 0.25(1 + 3 + 1 + 3) = 2 $
- $ E[XY] = 0.25(1 + 3 + 3 + 9) = 4 $

Then:
$$
\operatorname{Cov}(X, Y) = E[XY] - E[X]E[Y] = 4 - (2)(2) = 0
$$

✅ So X and Y are **uncorrelated**.

---

### 🔸 Example (Continuous Case)

Let:
$$
f(x, y) = 4xy,\quad 0 \le x, y \le 1
$$

We’ve already found:
- $ E[X] = \frac{2}{3} $, $ E[Y] = \frac{2}{3} $

Now:
$$
E[XY] = \int_0^1 \int_0^1 x y \cdot 4xy \, dx\,dy = \int_0^1 \int_0^1 4x^2y^2 \, dx\,dy
$$

Compute:
- $ \int_0^1 x^2 dx = \frac{1}{3} $, $ \int_0^1 y^2 dy = \frac{1}{3} $
- So $ E[XY] = 4 \cdot \frac{1}{3} \cdot \frac{1}{3} = \frac{4}{9} $

Now:
$$
\operatorname{Cov}(X, Y) = E[XY] - E[X]E[Y] = \frac{4}{9} - \frac{4}{9} = 0
$$

Again, **uncorrelated**.

---

## 🔷 2.5.3 Properties of Covariance

1. **Symmetry**:  
   $$
   \operatorname{Cov}(X, Y) = \operatorname{Cov}(Y, X)
   $$

2. **Cov(X, X) = Var(X)**

3. **Linearity**:  
   For constants $ a, b, c, d $:

   $$
   \operatorname{Cov}(aX + b, cY + d) = ac \cdot \operatorname{Cov}(X, Y)
   $$

---

## 🔷 2.5.4 Variance of a Sum

$$
\operatorname{Var}(X + Y) = \operatorname{Var}(X) + \operatorname{Var}(Y) + 2 \cdot \operatorname{Cov}(X, Y)
$$

⚠️ Use this when computing variance of totals (e.g., total score of 2 subjects).

---

## 🔁 Summary

| Concept       | Formula |
|---------------|---------|
| $ \operatorname{Var}(X) $ | $ E[X^2] - (E[X])^2 $ |
| $ \operatorname{Cov}(X, Y) $ | $ E[XY] - E[X]E[Y] $ |
| $ \operatorname{Var}(X+Y) $ | $ \operatorname{Var}(X) + \operatorname{Var}(Y) + 2\operatorname{Cov}(X, Y) $ |
