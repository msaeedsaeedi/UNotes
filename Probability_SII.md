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
