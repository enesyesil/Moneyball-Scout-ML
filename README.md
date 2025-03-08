# Moneyball: Identifying Undervalued Players

![Moneyball Cover](Moneyball.png)

## Project Overview
The **Moneyball** project applies the Moneyball philosophy to soccer, identifying players whose talents are overlooked or underappreciated in the market using data analysis and machine learning models. By analyzing detailed performance metrics, this project aims to uncover players who are undervalued compared to their actual contributions.

## Team Members
- **Enes Yesil**  
- **Kevin Perera**  
- **Muhammad Ali Kermali**  

## Problem Statement
In soccer, player valuations often fail to reflect true on-field performance. Our goal is to leverage data-driven insights to identify **undervalued players** by comparing their actual price with an expected price derived from machine learning models.

## Data Sources
The project utilizes two datasets:  
1. **Player Information Dataset** – Includes details like player name, age, position, and salary.  
2. **Performance Metrics Dataset** – Includes statistics such as goals, assists, passing accuracy, progressive passes, and defensive actions.  

These datasets were combined into a single dataframe and segmented based on player positions. Key performance metrics were selected to calculate a **Performance Index** for each player.

## Methodology

### 1. **Linear Regression (Attacking Midfielders & Centre Backs)**
- Players with a **positive score** were deemed **undervalued**.
- A second model incorporated **age** to find **young undervalued talents**.

### 2. **Naive Bayes Classification (Centre Forwards)**
- Defined **undervalued players** as those in the **bottom 25% of prices** within similar performance index quartiles.
- Marked players in the **lowest price quartile** within each performance index quartile as undervalued.
- Trained a **Naive Bayes model** using **Performance Index** and **Age** to classify undervalued players.

### 3. **Polynomial Regression (Centre Forwards)**
- Used a similar approach to **linear regression** but incorporated **polynomial features** to better capture **non-linear price relationships**.
- Identified undervalued players using the same **"Underrated Score"** metric.

---

## Key Findings & Analysis
- **Naive Bayes Model for Centre Forwards** achieved **77.72% accuracy**, making it the most effective model in identifying undervalued players.
- **Linear & Polynomial Regression Models** performed well, particularly in identifying players whose market values increased over the season.
- **Model Validation** through cross-validation ensured accuracy and real-world applicability.

---

## Limitations
Despite the success of our models, there are several challenges:

- **Missing or Misleading Data** – Some key player statistics may be incomplete or inaccurately reported.
- **Market Fluctuations** – Player prices depend on factors beyond performance, such as **contract duration, nationality, club relationships, and transfer trends**.
- **Club-Specific Needs** – Valuation varies based on a **club’s playing style and specific tactical requirements**, which are difficult to model.

---

## Conclusion
Our models successfully identified **undervalued players**, providing a **data-driven approach for soccer clubs** to scout affordable yet high-performing talent. The **Naive Bayes model** showed the highest effectiveness, offering a promising avenue for real-world application in **player scouting and recruitment**.

---

## Installation & Usage

### **Prerequisites**
Ensure you have the following dependencies installed:
- **Python 3.x**
- **Pandas**
- **Scikit-learn**
- **NumPy**
- **Matplotlib** (for visualization)

### **Installation**
Clone this repository and install dependencies:

```sh
git clone https://github.com/your-repo/moneyball.git
cd moneyball
pip install -r requirements.txt

