# Probability Notes – Sessional II

---

## Part 1: Discrete and Continuous Random Variables

### 🔹 **1.1 Random Variables (RVs)**

#### 🔸 What is a Random Variable?

A **Random Variable (RV)** is a variable that takes on numerical values based on the outcome of a random experiment.

There are **two types**:

| Type            | Description                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| **Discrete**    | Takes **countable** values (e.g., 0, 1, 2, …).                              |
| **Continuous**  | Takes **uncountably infinite** values within an interval (e.g., 1.3, 2.7). |

---

#### 🔹 Examples

##### Discrete RV:
- Tossing a coin 3 times → Let $ X $ = number of heads.
  - Possible values of $ X $: {0, 1, 2, 3}
  
##### Continuous RV:
- Measuring the height of a person → Let $ Y $ = height in cm.
  - Possible values of $ Y $: Any real number between, say, 100 and 200.

---

#### 🔸 Notation

- Random Variable: usually written in **uppercase** (e.g., $ X, Y $)
- Realized value: written in **lowercase** (e.g., $ x, y $)

> Example: If $ X $ is a random variable for dice roll, then $ P(X = 5) $ is the probability that the outcome is 5.

---

### 🔹 Key Differences (Discrete vs Continuous)

| Feature                 | Discrete RV                         | Continuous RV                          |
|-------------------------|-------------------------------------|----------------------------------------|
| Values                  | Countable (finite or infinite)      | Uncountably infinite                   |
| Representation          | **Probability Mass Function (PMF)** | **Probability Density Function (PDF)** |
| Total Probability       | $ \sum P(X = x) = 1 $             | $ \int f(x) \, dx = 1 $              |
| Probability at a point  | Non-zero $ P(X = x) > 0 $         | Zero $ P(X = x) = 0 $                |
| Example                 | Number of heads in 3 coin tosses    | Weight of a randomly chosen apple      |

---

#### 📌 Important Realizations:

1. **Discrete RV**: We assign probability to each value.
   - $ P(X = x) $ is meaningful and non-zero.
2. **Continuous RV**: We assign probability over **intervals**, not single points.
   - $ P(X = x) = 0 $, but $ P(a \le X \le b) > 0 $

---

#### 🎯 Quick Practice

**Q1:** Identify if the following RVs are discrete or continuous:

a. The number of messages you get in a day  
b. The temperature at noon in Islamabad  
c. The time it takes to solve a math problem  
d. The number of students in a class

👉 **Answers**:
- a: Discrete  
- b: Continuous  
- c: Continuous  
- d: Discrete

---

### 🔹 **1.2 Probability Mass Function (PMF)** – For Discrete Random Variables

#### 🔸 Definition:

A **Probability Mass Function (PMF)** gives the probability that a **discrete** random variable is equal to a particular value.

$$
P(X = x) = p(x)
$$

It must satisfy:
1. $ p(x) \geq 0 $ for all $ x $
2. $ \sum_{x} p(x) = 1 $

---

#### 🧠 Example 1: Tossing a fair coin twice

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

#### 🧠 Example 2: Rolling a fair die

Let $ X $ = outcome of the die.

- PMF: $ p(x) = \frac{1}{6} $ for $ x = 1, 2, 3, 4, 5, 6 $
- Not defined for other values.

---

### 🔹 **1.2 Probability Density Function (PDF)** – For Continuous Random Variables

#### 🔸 Definition:

A **Probability Density Function (PDF)** is a function that describes the **relative likelihood** of a **continuous** random variable to take on a value within a certain interval.

$$
f(x) \ge 0 \quad \text{and} \quad \int_{-\infty}^{\infty} f(x)\,dx = 1
$$

👉 You **cannot** say $ P(X = x) $. Instead:

$$
P(a \le X \le b) = \int_a^b f(x) \, dx
$$

---

#### 🧠 Example 1: Uniform Distribution over [0, 1]

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

#### 🧠 Example 2: Exponential Distribution (with $ \lambda = 1 $)

$$
f(x) = e^{-x}, \quad x \ge 0
$$

Check:  
$$
\int_0^\infty e^{-x} dx = 1
$$

This is a valid PDF.

---

### 📊 PMF vs PDF – Summary Table

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

👉 **Answers**:
1. ❌ No, $ P(X = 1.5) = 0 $ for continuous RVs  
2. ❌ No, PMF $ \ge 0 $  
3. ✅ $ f(x) \ge 0 $, and total area under curve = 1

---

## Part 2: Joint Distributions of Discrete and Continuous Random Variables

### 🔹 **2.1 Joint Distributions**

#### 🔸 Discrete Case

If $ X $ and $ Y $ are discrete random variables, their **joint PMF** is:

$$
P(X = x, Y = y) = \text{Probability that } X = x \text{ and } Y = y
$$

It satisfies:
1. $ P(X = x_i, Y = y_j) \geq 0 $
2. $ \sum_i \sum_j P(X = x_i, Y = y_j) = 1 $

---

#### 🔸 Continuous Case

If $ X $ and $ Y $ are continuous random variables, then their **joint PDF** is a function $ f(x, y) $ such that:

$$
P((X, Y) \in A) = \iint_A f(x, y) \, dx\,dy
$$

It must satisfy:

1. $ f(x, y) \geq 0 $
2. $ \iint_{-\infty}^\infty f(x, y)\,dx\,dy = 1 $

---

## 🔹 **2.2 Marginal Distributions**

**Marginal distribution** gives us the probability distribution of a single random variable *ignoring* the other one.

Basically:  
> From the **joint distribution**, we "sum out" or "integrate out" the other variable.

---

### 🔷 2.2.1 Marginal Distribution (Discrete Case)

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

### 🔷 2.2.2 Marginal Distribution (Continuous Case)

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

## 🔹 **2.3 Conditional Distributions**

Conditional distributions tell us how the probability of one variable behaves *under the condition* that we know the value of the other variable.

---

### 🔷 2.3.1 Discrete Case — Conditional PMF

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
|------------------------|------------|------------|--------------|
| $ X = 1 $           | 0.2        | 0.3        | 0.5           |
| $ X = 2 $           | 0.1        | 0.4        | 0.5           |
| $ P_Y(y) $          | 0.3        | 0.7        |               |

Now:
- $ P(X = 1 \mid Y = 1) = \frac{0.3}{0.7} = \frac{3}{7} $
- $ P(Y = 0 \mid X = 2) = \frac{0.1}{0.5} = \frac{1}{5} $

✅ Always check the denominator is not zero.

---

### 🔷 2.3.2 Continuous Case — Conditional PDF

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

## 🔹 **2.4 Independence of Random Variables**

Two random variables are **independent** if *knowing the value of one gives no information about the other*.  
In other words:  
> The behavior of one does **not depend** on the other.

---

### 🔷 2.4.1 Independence — Discrete Case

Let $ X $ and $ Y $ be discrete random variables.

#### 👉 Definition:

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

### 🔷 2.4.2 Independence — Continuous Case

Let $ X $ and $ Y $ be continuous random variables.

#### 👉 Definition:

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

## 🔹 **2.5 Variance and Covariance**

---

### 🔷 2.5.1 Variance Recap (for a Single RV)

For a single random variable $ X $, we define:

$$
\operatorname{Var}(X) = E[(X - \mu_X)^2] = E[X^2] - (E[X])^2
$$

It tells us **how much the values of X deviate from the mean**.

---

### 🔷 2.5.2 Covariance — Measuring Linear Relationship

Covariance tells us **how two random variables vary together**.

$$
\operatorname{Cov}(X, Y) = E[(X - \mu_X)(Y - \mu_Y)]
$$

Alternate formula:

$$
\operatorname{Cov}(X, Y) = E[XY] - E[X]E[Y]
$$

---

#### 🟩 Interpretation:

- **Positive Covariance**: When $ X $ increases, $ Y $ tends to increase.
- **Negative Covariance**: When $ X $ increases, $ Y $ tends to decrease.
- **Zero Covariance**: No linear relationship.

> Covariance gives the **direction** of the relationship, but **not strength or scale**.

---

#### 🔸 Example (Discrete Case)

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

#### 🔸 Example (Continuous Case)

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

### 🔷 2.5.3 Properties of Covariance

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

### 🔷 2.5.4 Variance of a Sum

$$
\operatorname{Var}(X + Y) = \operatorname{Var}(X) + \operatorname{Var}(Y) + 2 \cdot \operatorname{Cov}(X, Y)
$$

⚠️ Use this when computing variance of totals (e.g., total score of 2 subjects).

---

## 🔹 **2.6 Correlation Coefficient**

---

### 🔷 2.6.1 What is the Correlation Coefficient?

The **correlation coefficient**, denoted by $ \rho_{X,Y} $ (rho), **standardizes covariance**.

$$
\rho_{X,Y} = \frac{\operatorname{Cov}(X, Y)}{\sigma_X \cdot \sigma_Y}
$$

Where:
- $ \sigma_X = \sqrt{\operatorname{Var}(X)} $
- $ \sigma_Y = \sqrt{\operatorname{Var}(Y)} $

This tells us **how strongly X and Y are linearly related**, and the value is **always between -1 and 1**.

---

### 🔷 2.6.2 Interpretation

| Value of $ \rho $ | Strength of Relationship |
|---------------------|--------------------------|
| $ \rho = 1 $      | Perfect positive linear relationship |
| $ \rho = -1 $     | Perfect negative linear relationship |
| $ \rho = 0 $      | No linear relationship (could still be non-linear) |
| $ \rho \approx 0.5 $ | Moderate positive linear relationship |
| $ \rho \approx -0.5 $ | Moderate negative linear relationship |

> **Key Point**: Correlation only captures **linear** dependence. Two variables may have **nonlinear dependence** and still have $ \rho = 0 $!

---

### 🔸 Example 1 (Discrete)

From previous example:

| (X, Y) | P(X, Y) |
|--------|---------|
| (1, 1) | 0.25    |
| (1, 3) | 0.25    |
| (3, 1) | 0.25    |
| (3, 3) | 0.25    |

We already found:

- $ E[X] = 2 $, $ E[Y] = 2 $
- $ E[XY] = 4 $
- $ \operatorname{Cov}(X, Y) = 4 - (2)(2) = 0 $

Next, compute:

$$
E[X^2] = 0.25(1^2 + 1^2 + 3^2 + 3^2) = 0.25(1 + 1 + 9 + 9) = 5
\Rightarrow \operatorname{Var}(X) = 5 - 4 = 1
$$

Similarly:
$$
\operatorname{Var}(Y) = 1
\Rightarrow \sigma_X = \sigma_Y = 1
$$

So:
$$
\rho_{X,Y} = \frac{0}{1 \cdot 1} = 0
$$

✅ No linear correlation.

---

### 🔸 Example 2 (Simple Correlated Pair)

Let:
- $ X \in \{1, 2, 3\} $, with $ P(X = x) = \frac{1}{3} $
- $ Y = 2X $

So:

| X | Y | P(X) |
|---|---|------|
| 1 | 2 | 1/3  |
| 2 | 4 | 1/3  |
| 3 | 6 | 1/3  |

Now compute:

- $ E[X] = \frac{1+2+3}{3} = 2 $
- $ E[Y] = \frac{2+4+6}{3} = 4 $
- $ E[XY] = \frac{1 \cdot 2 + 2 \cdot 4 + 3 \cdot 6}{3} = \frac{2 + 8 + 18}{3} = \frac{28}{3} $

Then:

$$
\operatorname{Cov}(X, Y) = \frac{28}{3} - (2)(4) = \frac{28}{3} - 8 = \frac{4}{3}
$$

Now:

- $ E[X^2] = \frac{1^2 + 2^2 + 3^2}{3} = \frac{14}{3} $
- $ \operatorname{Var}(X) = \frac{14}{3} - 4 = \frac{2}{3} $
- $ \operatorname{Var}(Y) = \operatorname{Var}(2X) = 4 \cdot \operatorname{Var}(X) = \frac{8}{3} $

Then:

$$
\rho_{X,Y} = \frac{\frac{4}{3}}{\sqrt{\frac{2}{3}} \cdot \sqrt{\frac{8}{3}}} = \frac{4}{\sqrt{2 \cdot 8}} = \frac{4}{\sqrt{16}} = 1
$$

✅ Perfect linear correlation.

---

### 🔷 2.6.3 Properties of Correlation

- $ -1 \le \rho_{X,Y} \le 1 $
- $ \rho_{X,Y} = \rho_{Y,X} $
- $ \rho_{X,Y} = 0 $ ⟹ **X and Y are uncorrelated**, but not necessarily independent
- **If X and Y are independent**, then $ \rho = 0 $ (but not the reverse!)

---

## 🔹 **2.7 Properties of Covariance, Variance, and Correlation**

We’ll go through them category-wise so it’s clean and easy to revise.

---

### 🔷 2.7.1 **Variance Properties**

Let $ X $ be a random variable and $ a, b $ be constants:

#### 🔹 1. **Variance of a Constant:**
$$
\operatorname{Var}(c) = 0
$$

A constant doesn’t vary, so its variance is 0.

---

#### 🔹 2. **Scaling:**
$$
\operatorname{Var}(aX) = a^2 \cdot \operatorname{Var}(X)
$$

Multiplying a random variable scales its variance **quadratically** (not linearly!).

---

#### 🔹 3. **Shift Doesn’t Affect Variance:**
$$
\operatorname{Var}(X + b) = \operatorname{Var}(X)
$$

Adding a constant only shifts the values, doesn’t change the spread.

---

#### 🔹 4. **Variance of a Sum (General Case):**
$$
\operatorname{Var}(X + Y) = \operatorname{Var}(X) + \operatorname{Var}(Y) + 2\operatorname{Cov}(X, Y)
$$

---

#### 🔹 5. **If X and Y are Independent:**
$$
\operatorname{Var}(X + Y) = \operatorname{Var}(X) + \operatorname{Var}(Y)
$$

Because:
$$
\operatorname{Cov}(X, Y) = 0 \quad \text{(if independent)}
$$

---

### 🔷 2.7.2 **Covariance Properties**

For constants $ a, b, c, d $, and random variables $ X, Y $:

#### 🔹 1. **Covariance is Symmetric:**
$$
\operatorname{Cov}(X, Y) = \operatorname{Cov}(Y, X)
$$

---

#### 🔹 2. **Covariance of Independent Variables:**
$$
X \perp Y \Rightarrow \operatorname{Cov}(X, Y) = 0
$$

But **not the reverse!**

---

#### 🔹 3. **Cov(X, X) = Var(X)**  
Self-covariance is variance.

---

#### 🔹 4. **Linearity (Scalar Multiplication):**
$$
\operatorname{Cov}(aX, bY) = ab \cdot \operatorname{Cov}(X, Y)
$$

---

#### 🔹 5. **Linearity (Addition/Subtraction):**
$$
\operatorname{Cov}(X + Y, Z) = \operatorname{Cov}(X, Z) + \operatorname{Cov}(Y, Z)
$$

In general, Cov is **linear in each argument**.

---

#### 🔹 6. **Covariance with Constant:**
$$
\operatorname{Cov}(X, c) = 0
$$

Because a constant has no variation.

---

### 🔷 2.7.3 **Correlation Properties**

Let $ \rho = \text{Corr}(X, Y) $:

#### 🔹 1. **Bounds:**
$$
-1 \leq \rho \leq 1
$$

#### 🔹 2. **Perfect Correlation:**
- $ \rho = 1 $: $ Y = aX + b $, with $ a > 0 $
- $ \rho = -1 $: $ Y = aX + b $, with $ a < 0 $

Linear relationships only.

---

#### 🔹 3. **Independence Implies Zero Correlation**  
But **zero correlation ≠ independence** (unless joint distribution is normal or special).

---

#### 🔹 4. **Invariant to Shifts and Scales:**

$$
\rho_{X,Y} = \rho_{aX+b, cY+d} \quad \text{(if } a, c > 0 \text{)}
$$

This makes correlation very powerful: **unit-less and standardized**.

---

### 📦 Example Question (Mixed Concepts)

> Let $ X, Y $ be RVs such that:
> - $ \operatorname{Var}(X) = 4 $, $ \operatorname{Var}(Y) = 9 $
> - $ \operatorname{Cov}(X, Y) = 6 $

#### Find:

- $ \operatorname{Var}(X + Y) $
- $ \rho_{X,Y} $

---

**Solution:**

$$
\operatorname{Var}(X+Y) = 4 + 9 + 2(6) = 25
$$

$$
\rho = \frac{\operatorname{Cov}(X,Y)}{\sigma_X \cdot \sigma_Y} = \frac{6}{\sqrt{4} \cdot \sqrt{9}} = \frac{6}{2 \cdot 3} = 1
$$

✅ Perfectly positively correlated!

---

### ✍️ Summary Table

| Concept | Property | Formula |
|--------|----------|---------|
| Variance | Scaling | $ \operatorname{Var}(aX) = a^2 \cdot \operatorname{Var}(X) $ |
| Covariance | Symmetry | $ \operatorname{Cov}(X,Y) = \operatorname{Cov}(Y,X) $ |
| Covariance | Linear Combination | $ \operatorname{Cov}(aX+b, cY+d) = ac \cdot \operatorname{Cov}(X, Y) $ |
| Correlation | Standardized | $ \rho = \frac{\operatorname{Cov}(X, Y)}{\sigma_X \sigma_Y} $ |
| Correlation | Range | $ -1 \le \rho \le 1 $ |
| Variance of Sum | General | $ \operatorname{Var}(X+Y) = \operatorname{Var}(X) + \operatorname{Var}(Y) + 2\operatorname{Cov}(X, Y) $ |

---

## 🔹 **2.8 Chebyshev’s Inequality**

Chebyshev's inequality gives us a **lower bound** for the probability that a random variable deviates from its mean.

---

### 🔷 2.8.1 **What is Chebyshev’s Inequality?**

Chebyshev’s inequality states that for any random variable $ X $ with mean $ \mu $ and variance $ \sigma^2 $:

$$
P(|X - \mu| \geq k \sigma) \leq \frac{1}{k^2}
$$

Where:
- $ k $ is any positive number
- $ \mu $ is the mean of $ X $
- $ \sigma $ is the standard deviation of $ X $

In words: **No more than $ \frac{1}{k^2} $ of the distribution lies more than $ k $ standard deviations away from the mean**.

---

### 🔷 2.8.2 **Interpretation**

- The inequality gives us a **worst-case bound** on the probability that a value falls a certain distance away from the mean.
- It’s **non-parametric**, meaning it works for any probability distribution (even those that are not normal).
- As $ k $ increases, the probability of deviation decreases rapidly (quadratically).

---

### 🔷 2.8.3 **Examples**

#### 🔸 Example 1: Basic Application

Let’s say we have a random variable $ X $ with:
- Mean $ \mu = 5 $
- Standard deviation $ \sigma = 2 $

We want to know the probability that $ X $ deviates by more than 3 units from the mean (i.e., $ |X - 5| \geq 3 $).

From Chebyshev’s inequality:
$$
P(|X - \mu| \geq 3) \leq \frac{1}{\left(\frac{3}{2}\right)^2} = \frac{1}{\left(1.5\right)^2} = \frac{1}{2.25} \approx 0.444
$$

So, the probability that $ X $ deviates more than 3 units from the mean is **at most 44.4%**.

---

#### 🔸 Example 2: Interpretation for Larger Deviations

Now, let’s see what happens when we look for a larger deviation, say $ 5 $ units.

We use $ k = \frac{5}{2} = 2.5 $.

Then:
$$
P(|X - \mu| \geq 5) \leq \frac{1}{(2.5)^2} = \frac{1}{6.25} = 0.16
$$

So, the probability that $ X $ deviates more than 5 units from the mean is **at most 16%**.

---

### 🔷 2.8.4 **Key Takeaways**

- Chebyshev’s inequality is very general and can be applied to any distribution, whether or not it’s normal.
- The inequality provides an **upper bound**, not the exact probability.
- As $ k $ increases, the bound becomes tighter (less probability).
- **The inequality is most useful** when we don’t know the exact form of the distribution (like in real-world situations).

---

### 🔷 Summary of Chebyshev's Inequality

For a random variable $ X $ with mean $ \mu $ and variance $ \sigma^2 $, Chebyshev's inequality states:

$$
P(|X - \mu| \geq k \sigma) \leq \frac{1}{k^2}
$$

- The bound decreases quadratically as $ k $ increases.
- The inequality holds for **all** distributions (even non-normal).
- It helps when we need a general estimate for tail probabilities in **non-parametric settings**.

---

### 📦 Example Question (Application)

> Given a distribution with $ \mu = 10 $ and $ \sigma = 4 $, use Chebyshev’s inequality to find the probability that the random variable lies within 6 units of the mean.

#### Solution:

We’re asked for the probability that the value of $ X $ lies within 6 units of the mean:
$$
P(|X - \mu| \geq 6) \Rightarrow k = \frac{6}{4} = 1.5
$$

So:
$$
P(|X - 10| \geq 6) \leq \frac{1}{(1.5)^2} = \frac{1}{2.25} = 0.444
$$

Thus, the probability that $ X $ deviates by **more than 6 units** from the mean is **at most 44.4%**.

---

## Part 3: Selected Discrete Distributions

### 🔹 **3.1 Bernoulli Distribution**

#### 🔸 PMF

$$
P(X = x) = p^x (1 - p)^{1 - x}, \quad \text{for } x \in \{0, 1\}
$$

---

### 🔸 3.1.2 Mean (Expected Value)

$$
\mathbb{E}[X] = 0 \cdot (1 - p) + 1 \cdot p = p
$$

So, the **mean of a Bernoulli random variable is $ p $**.

---

### 🔸 3.1.3 Variance

$$
\text{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2
$$

But for Bernoulli, since $ X^2 = X $ (because $ X \in \{0,1\} $):

$$
\text{Var}(X) = \mathbb{E}[X] - (\mathbb{E}[X])^2 = p - p^2 = p(1 - p)
$$

So, the **variance is $ p(1 - p) $**.

---

### 🔸 3.1.4 Moment Generating Function (MGF)

The MGF of a discrete random variable is:

$$
M_X(t) = \mathbb{E}[e^{tX}] = e^{0t}(1 - p) + e^{1t}(p) = (1 - p) + p e^t
$$

---

### 🔸 3.1.5 Skewness

$$
\text{Skewness} = \frac{1 - 2p}{\sqrt{p(1 - p)}}
$$

- If $ p = 0.5 $: symmetric (skewness = 0)
- If $ p < 0.5 $: right-skewed
- If $ p > 0.5 $: left-skewed

---

### 🔸 3.1.6 Kurtosis

$$
\text{Kurtosis} = \frac{1 - 6p(1 - p)}{p(1 - p)}
$$

This measures **"tailedness"** or how heavy the tails are compared to a normal distribution.

---

### 🧠 Trick Question Patterns

1. **If $ \mathbb{E}[X] = 0.3 $, what is $ \text{Var}(X) $?**

$$
\text{Var}(X) = p(1 - p) = 0.3 \cdot 0.7 = 0.21
$$

---

2. **Find skewness when $ \text{Var}(X) = 0.25 $**

If $ p(1 - p) = 0.25 $, then:

$$
p = 0.5 \Rightarrow \text{Skewness} = \frac{1 - 2(0.5)}{\sqrt{0.25}} = \frac{0}{0.5} = 0
$$

---

3. **MGF-based question:**

> Find $ \mathbb{E}[X] $ using MGF:
$$
M_X(t) = (1 - p) + p e^t \Rightarrow M'_X(t) = p e^t
\Rightarrow M'_X(0) = p
$$

---

### 🔹 **3.2 Binomial Distribution**

The **Binomial Distribution** models the number of successes in **$ n $** independent **Bernoulli trials**, each with probability of success $ p $.

---

#### 🔸 3.2.1 PMF (Probability Mass Function)

$$
P(X = x) = \binom{n}{x} p^x (1 - p)^{n - x}, \quad x = 0, 1, 2, ..., n
$$

- $ \binom{n}{x} $ is the number of ways to choose $ x $ successes from $ n $ trials.

---

#### 🔸 3.2.2 Expected Value (Mean)

$$
\mathbb{E}[X] = n \cdot p
$$

This is intuitive: if each trial has expected value $ p $, the total expected number of successes in $ n $ trials is $ n \cdot p $.

---

#### 🔸 3.2.3 Variance

$$
\text{Var}(X) = n \cdot p \cdot (1 - p)
$$

This shows variance depends on both number of trials and how "uncertain" each trial is.

---

#### 🔸 3.2.4 Moment Generating Function (MGF)

For $ X \sim \text{Binomial}(n, p) $, the MGF is:

$$
M_X(t) = \mathbb{E}[e^{tX}] = [(1 - p) + p e^t]^n
$$

> 💡 Use this to find moments:
- First derivative $ M'_X(t) $ gives **mean**
- Second derivative $ M''_X(t) $ helps with **variance**

---

#### 🔸 3.2.5 Skewness

$$
\text{Skewness} = \frac{1 - 2p}{\sqrt{np(1 - p)}}
$$

- Skewness tells us whether the distribution is symmetric or not.
- Symmetric when $ p = 0.5 $

---

#### 🔸 3.2.6 Kurtosis

$$
\text{Kurtosis} = \frac{1 - 6p(1 - p)}{np(1 - p)} + 3
$$

- Kurtosis > 3 means heavy tails (leptokurtic)
- Kurtosis < 3 means light tails (platykurtic)

---

### 🧠 Trick Question Patterns

1. **If $ X \sim \text{Binomial}(5, 0.4) $, find:**
   - $ \mathbb{E}[X] = 5 \cdot 0.4 = 2 $
   - $ \text{Var}(X) = 5 \cdot 0.4 \cdot 0.6 = 1.2 $

---

2. **MGF Application:**
   - $ M_X(t) = [(1 - p) + p e^t]^n $
   - Find $ \mathbb{E}[X] $ using:  
     $$
     M'_X(t) = n \cdot [(1 - p) + p e^t]^{n-1} \cdot p e^t \Rightarrow M'_X(0) = np
     $$

---

3. **Skewness-based reasoning:**
   - For large $ n $, skewness gets closer to 0 → distribution becomes symmetric.

---

4. **Maximum Probability Value:**
   - The mode (most probable value) of a Binomial Distribution is usually:
     $$
     \lfloor (n + 1)p \rfloor
     $$

---

5. **Cumulative Probabilities:**
   - $ P(X \leq x) $ often requires either:
     - Direct calculation using the PMF
     - Binomial tables / software

---

### 🔹 **3.3 Multinomial Distribution**

The **Multinomial Distribution** generalizes the Binomial Distribution from two categories (success/failure) to **$ k \geq 2 $** categories.

---

#### 🔸 3.3.1 PMF (Probability Mass Function)

$$
P(X_1 = x_1, \dots, X_k = x_k) = \frac{n!}{x_1! x_2! \cdots x_k!} p_1^{x_1} p_2^{x_2} \cdots p_k^{x_k}
$$

- where $ \sum_{i=1}^{k} x_i = n $
- $ x_i \in \{0, 1, ..., n\} $

---

#### 🔸 3.3.2 Expected Value

For each $ i \in \{1, 2, \dots, k\} $:

$$
\mathbb{E}[X_i] = n \cdot p_i
$$

Same as binomial intuition: in $ n $ trials, the expected number of times outcome $ i $ occurs is $ np_i $

---

#### 🔸 3.3.3 Variance

$$
\text{Var}(X_i) = n \cdot p_i \cdot (1 - p_i)
$$

Each outcome behaves like a binomial, but they’re not independent.

---

#### 🔸 3.3.4 Covariance

For $ i \neq j $:

$$
\text{Cov}(X_i, X_j) = -n \cdot p_i \cdot p_j
$$

This makes sense: if more trials result in category $ i $, fewer can result in category $ j $, creating negative covariance.

---

#### 🔸 3.3.5 Moment Generating Function (MGF)

The MGF of the multinomial vector $ \mathbf{X} = (X_1, ..., X_k) $ is:

$$
M_{\mathbf{X}}(t_1, t_2, ..., t_k) = \left( \sum_{i=1}^k p_i e^{t_i} \right)^n
$$

This is a **multi-variable MGF**, so moments are found using partial derivatives.

---

#### 🔸 3.3.6 Skewness & Kurtosis

- Typically **not defined** or **not commonly used** for the entire multinomial vector.
- But **each marginal** $ X_i \sim \text{Binomial}(n, p_i) $, so:
  - Skewness: $ \frac{1 - 2p_i}{\sqrt{np_i(1 - p_i)}} $
  - Kurtosis: $ \frac{1 - 6p_i(1 - p_i)}{np_i(1 - p_i)} + 3 $

---

### 🧠 Trick Question Patterns

---

#### 💡 Q1: Example Setup:

> A die is rolled 10 times. Let $ X_1 $ = number of 1’s, $ X_2 $ = number of 2’s, ..., $ X_6 $ = number of 6’s.

- $ \mathbf{X} \sim \text{Multinomial}(10; \frac{1}{6}, ..., \frac{1}{6}) $
- $ \mathbb{E}[X_i] = 10 \cdot \frac{1}{6} \approx 1.67 $
- $ \text{Var}(X_i) = 10 \cdot \frac{1}{6} \cdot \frac{5}{6} = \frac{50}{36} $
- $ \text{Cov}(X_i, X_j) = -10 \cdot \frac{1}{6} \cdot \frac{1}{6} = -\frac{10}{36} $

---

#### 💡 Q2: Constraint-based question:

> If $ X_1 + X_2 + X_3 = 10 $, find:
- $ \mathbb{E}[X_1 - X_2] = \mathbb{E}[X_1] - \mathbb{E}[X_2] = n(p_1 - p_2) $

---

#### 💡 Q3: MGF application:

> Use $ \left(\sum p_i e^{t_i}\right)^n $ to extract mixed moments like $ \mathbb{E}[X_1 X_2] $ by partial derivatives.

---

### 🔹 **3.4 Hypergeometric Distribution**

#### 🔸 PMF (Probability Mass Function)

If $ X $ is the number of successes in $ n $ draws, then:

$$
P(X = x) = \frac{\binom{K}{x} \binom{N - K}{n - x}}{\binom{N}{n}}
$$

Where:

- $ 0 \le x \le \min(K, n) $
- $ X \sim \text{Hypergeometric}(N, K, n) $

---

#### 🔸 3.4.2 Expected Value

$$
\mathbb{E}[X] = n \cdot \frac{K}{N}
$$

> Same intuition as binomial: sample size × success proportion in population.

---

#### 🔸 3.4.3 Variance

$$
\text{Var}(X) = n \cdot \frac{K}{N} \cdot \frac{N - K}{N} \cdot \frac{N - n}{N - 1}
$$

- The **extra term** $ \frac{N - n}{N - 1} $ is the **finite population correction** due to *no replacement*.

---

#### 🔸 3.4.4 MGF (Moment Generating Function)

There’s **no simple closed-form MGF** for Hypergeometric.  
Instead, moments are usually derived using direct expectation techniques.

---

#### 🔸 3.4.5 Skewness

$$
\text{Skewness} = \frac{(N - 2K)\sqrt{N - 1}(N - 2n)}{\sqrt{nK(N - K)(N - n)}(N - 2)}
$$

> Often omitted in simpler settings, but relevant for deep theoretical analysis.

---

#### 🔸 3.4.6 Kurtosis

No simple form, but it exists. Generally omitted unless explicitly asked.

---

### 🧠 Trick Question Patterns

---

#### 💡 Q1: Biased Drawing

> A batch of 20 bulbs contains 6 defective ones. If 5 bulbs are randomly selected without replacement, what's the probability that exactly 2 are defective?

- $ N = 20, K = 6, n = 5, x = 2 $

$$
P(X = 2) = \frac{\binom{6}{2} \binom{14}{3}}{\binom{20}{5}}
$$

---

#### 💡 Q2: Comparing with Binomial

> If the same question allowed **replacement**, then use:
$$
X \sim \text{Binomial}(5, \frac{6}{20})
$$

But in **Hypergeometric**, we account for decreasing probabilities as items are removed.

---

#### 💡 Q3: Conceptual Twist

> You draw 3 cards from a deck of 52. What’s the probability that **all are red**?

- $ N = 52, K = 26 $ (red cards), $ n = 3, x = 3 $

$$
P(X = 3) = \frac{\binom{26}{3} \binom{26}{0}}{\binom{52}{3}} = \frac{\binom{26}{3}}{\binom{52}{3}}
$$

---

#### 💡 Q4: Expectation-based

> If a jar has 15 white and 10 black balls, and you randomly draw 6 without replacement, what’s the expected number of white balls?

- $ N = 25, K = 15, n = 6 $

$$
\mathbb{E}[X] = 6 \cdot \frac{15}{25} = 3.6
$$

---

### 🔹 **3.5 Negative Binomial Distribution**

#### 🔸 PMF (Probability Mass Function)

Let $ X $ be the number of **trials** needed to get $ r $ successes.

$$
P(X = x) = \binom{x - 1}{r - 1} p^r (1 - p)^{x - r}, \quad x = r, r+1, r+2, \dots
$$

Where:

- $ r $: fixed number of **successes**
- $ x $: total number of **trials**
- $ p $: probability of success
- $ X \sim \text{NegativeBinomial}(r, p) $

> We succeed on the **x-th** trial, and before that, we had $ r-1 $ successes in $ x-1 $ trials.

---

### 🧠 Alternate Interpretation

Sometimes it's framed as:  
Let $ Y $ be the number of **failures** before the $ r $-th success.

Then,

$$
P(Y = y) = \binom{r + y - 1}{y} p^r (1 - p)^y
$$

Where $ Y = X - r $

---

#### 🔸 3.5.2 Expected Value

$$
\mathbb{E}[X] = \frac{r}{p}
$$

---

#### 🔸 3.5.3 Variance

$$
\text{Var}(X) = \frac{r(1 - p)}{p^2}
$$

---

#### 🔸 3.5.4 MGF (Moment Generating Function)

$$
M_X(t) = \left( \frac{p e^t}{1 - (1 - p)e^t} \right)^r, \quad \text{for } t < -\ln(1 - p)
$$

---

#### 🔸 3.5.5 Skewness

$$
\text{Skewness} = \frac{2 - p}{\sqrt{r(1 - p)}}
$$

---

#### 🔸 3.5.6 Kurtosis

$$
\text{Kurtosis} = \frac{6}{r} + \frac{(1 - p)^2}{r p^2}
$$

---

### 🧠 Trick Question Patterns

---

#### 💡 Q1: Trials until Successes

> A basketball player hits a shot with probability $ p = 0.4 $. What is the probability that her **5th success** comes on her **10th shot**?

- $ r = 5, x = 10 $

$$
P(X = 10) = \binom{9}{4} \cdot (0.4)^5 \cdot (0.6)^5
$$

---

#### 💡 Q2: Expectation-based

> If $ X \sim \text{NegBin}(r = 3, p = 0.2) $, find $ \mathbb{E}[X] $ and $ \text{Var}(X) $.

- $ \mathbb{E}[X] = \frac{3}{0.2} = 15 $
- $ \text{Var}(X) = \frac{3(1 - 0.2)}{0.2^2} = \frac{3 \cdot 0.8}{0.04} = 60 $

---

#### 💡 Q3: Conceptual

> What’s the difference between Negative Binomial and Binomial?

| Feature | Binomial | Negative Binomial |
|--------|----------|-------------------|
| Fixed | Number of trials $ n $ | Number of successes $ r $ |
| Variable | Number of successes | Number of trials |
| Application | Pass/fail in fixed tries | Time until fixed # of wins |

---

#### 💡 Q4: Reduce to Geometric

If $ r = 1 $, the Negative Binomial **reduces to the Geometric Distribution**:

$$
P(X = x) = (1 - p)^{x - 1} p
$$

We’ll explore this next 👇

---

### 🔹 **3.6 Geometric Distribution**

#### 🔸 PMF (Probability Mass Function)

Let $ X $ be the trial on which the **first success** occurs.

$$
P(X = x) = (1 - p)^{x - 1} p, \quad x = 1, 2, 3, \dots
$$

Where:
- $ p $: probability of success in a single trial
- $ (1 - p) $: failure
- $ X \sim \text{Geometric}(p) $

---

#### 🔸 3.6.2 MGF (Moment Generating Function)

$$
M_X(t) = \frac{p e^t}{1 - (1 - p) e^t}, \quad \text{for } t < -\ln(1 - p)
$$

---

#### 🔸 3.6.3 Expected Value

$$
\mathbb{E}[X] = \frac{1}{p}
$$

This means **on average**, you need $ \frac{1}{p} $ trials to get the first success.

---

#### 🔸 3.6.4 Variance

$$
\text{Var}(X) = \frac{1 - p}{p^2}
$$

---

#### 🔸 3.6.5 Skewness

$$
\text{Skewness} = \frac{2 - p}{\sqrt{1 - p}}
$$

---

#### 🔸 3.6.6 Kurtosis

$$
\text{Kurtosis} = 6 + \frac{p^2}{1 - p}
$$

---

## 🔄 Relationship to Negative Binomial

The **Geometric Distribution** is a **special case of the Negative Binomial**, when $ r = 1 $.

- Negative Binomial models trials to get **r successes**
- Geometric is **trials to get the 1st success**

---

## 💡 Trick Question Patterns

---

### Q1: First Success on x-th Trial

> A shooter hits a target with $ p = 0.3 $. What’s the probability the **first hit is on the 4th try**?

$$
P(X = 4) = (1 - 0.3)^3 \cdot 0.3 = (0.7)^3 \cdot 0.3 = 0.1029
$$

---

### Q2: At Most / At Least Style

> What’s the probability the first success is **within 3 tries**?

This is a **CDF** question:

$$
P(X \leq 3) = 1 - (1 - p)^3 = 1 - (0.7)^3 = 0.657
$$

---

### Q3: Memoryless Property

The Geometric Distribution is the **only discrete memoryless distribution**.

$$
P(X > m + n \mid X > m) = P(X > n)
$$

> Future doesn’t depend on the past! It resets at every failure.

---

### Q4: Expected Value / Variance Question

If $ X \sim \text{Geometric}(0.25) $:

- $ \mathbb{E}[X] = \frac{1}{0.25} = 4 $
- $ \text{Var}(X) = \frac{1 - 0.25}{0.25^2} = \frac{0.75}{0.0625} = 12 $

---

### 🔹 **3.7 Poisson Distribution**

#### 🔸 PMF (Probability Mass Function)

Let $ X \sim \text{Poisson}(\lambda) $, where $ \lambda $ is the **average rate** of occurrences in an interval.

$$
P(X = x) = \frac{e^{-\lambda} \lambda^x}{x!}, \quad x = 0, 1, 2, \dots
$$

Where:
- $ \lambda > 0 $: average number of occurrences per interval
- $ e \approx 2.718 $: Euler’s number

---

#### 🔸 3.7.2 MGF (Moment Generating Function)

$$
M_X(t) = \exp\left( \lambda (e^t - 1) \right)
$$

---

#### 🔸 3.7.3 Expected Value

$$
\mathbb{E}[X] = \lambda
$$

---

#### 🔸 3.7.4 Variance

$$
\text{Var}(X) = \lambda
$$

> The **mean and variance are equal**, which is a key Poisson property.

---

#### 🔸 3.7.5 Skewness

$$
\text{Skewness} = \frac{1}{\sqrt{\lambda}}
$$

---

#### 🔸 3.7.6 Kurtosis

$$
\text{Kurtosis} = \frac{1}{\lambda}
$$

---

## 🔁 Relationship with Binomial Distribution

The Poisson is often seen as a **limiting case of the Binomial distribution** when:

$$
n \to \infty,\ p \to 0,\ \text{and } np = \lambda
$$

---

## 🧠 Trick Question Patterns

---

### Q1: Direct PMF

> If a call center receives 6 calls per hour on average, what is the probability that 4 calls are received in one hour?

$$
P(X = 4) = \frac{e^{-6} \cdot 6^4}{4!} = \frac{e^{-6} \cdot 1296}{24} \approx 0.1339
$$

---

### Q2: At Least / At Most

> What’s the probability of **at most 2** accidents in a day if $ \lambda = 3 $?

$$
P(X \leq 2) = P(0) + P(1) + P(2) = \sum_{x=0}^{2} \frac{e^{-3} \cdot 3^x}{x!}
$$

You’ll often be asked to calculate or approximate CDF-like expressions manually or using tables.

---

### Q3: Interval Conversion

> If 5 calls arrive per hour, what is the probability of 2 calls in **24 minutes**?

- 24 minutes = $ \frac{2}{5} $ of an hour
- New $ \lambda = 5 \cdot \frac{2}{5} = 2 $

Then apply PMF:

$$
P(X = 2) = \frac{e^{-2} \cdot 2^2}{2!} = \frac{e^{-2} \cdot 4}{2} = 2e^{-2}
$$

---

### Q4: Mean = Variance Trick

> If the variance of a discrete distribution is equal to its mean, what could be the distribution?

✅ **Poisson**!

---

### Q5: Additivity Property

If $ X_1 \sim \text{Poisson}(\lambda_1) $ and $ X_2 \sim \text{Poisson}(\lambda_2) $, then:

$$
X_1 + X_2 \sim \text{Poisson}(\lambda_1 + \lambda_2)
$$

Only valid if $ X_1 $ and $ X_2 $ are **independent**.

---

That completes Part 3 and your entire **Sessional II Syllabus** 🎯