# 📈 A/B Testing: Funnel Optimization Analysis

## 🇺🇸 Project Overview

This project demonstrates a complete **A/B testing workflow** to evaluate the impact of UI/UX changes on the user conversion funnel.
The analysis moves from raw data extraction in **SQL**, through statistical rigorous testing in **Python**, to final validation and visualization in **Tableau**.

**Goal:** To determine if the changes introduced in the Test Group (Group 2) lead to a statistically significant increase in conversion rates compared to the Control Group (Group 1).

**Key Finding:** The test showed a **statistically significant positive impact** on the mid-funnel (checkout progression), validating the hypothesis for implementation.

---

## 🛠️ Technologies Used

| Category | Tools | Usage |
| :--- | :--- | :--- |
| **Data Extraction** | `Google BigQuery` (SQL) | Complex query using CTEs and Unions to aggregate event data. |
| **Statistical Analysis** | `Python` (Pandas, Statsmodels) | Data cleaning, Pivot tables, and **Z-Test for Proportions**. |
| **Visualization** | `Tableau` | Data validation and result presentation. |

---

## 1. Methodology

### A. Data Validation
Before analyzing results, we ensured the A/B test was valid.
* **Traffic Split:** The traffic was split evenly **50/50** between the Control and Test groups.
* **Homogeneity:** Distribution of users by Device, Continent, and Country was identical across groups.

![Validation Dashboard](Tableau%201.png)
*Fig 1. Validation of group distribution (Geography & Devices).*

### B. Statistical Approach
We calculated the **Conversion Rate (CR)** for key funnel metrics:
$$CR = \frac{\text{Unique Events}}{\text{Unique Sessions}}$$

To determine if the difference between groups was real or due to chance, we applied the **Two-Sided Z-Test of Proportions** with a significance level ($\alpha$) of 0.05.

---

## 2. Key Results

The Python analysis yielded the following results regarding the impact of the changes:

| Metric (Event / Session) | Lift (% Change) | P-Value | Statistically Significant? |
| :--- | :---: | :---: | :---: |
| **begin_checkout** | **+8.50%** | < 0.05 | ✅ **Yes** |
| **add_shipping_info** | **+7.13%** | < 0.05 | ✅ **Yes** |
| **add_payment_info** | **+4.93%** | < 0.05 | ✅ **Yes** |
| **new_account** | -3.35% | > 0.05 | ❌ No |

![Results Dashboard](Tableau%202.png)
*Fig 2. A/B Test Results and Z-Statistics.*

---

## 3. Conclusions & Recommendations

1.  **Success:** The test version significantly improved user progression through the checkout flow (Checkout $\to$ Shipping $\to$ Payment).
2.  **Recommendation:** **Deploy the changes** to all users, as they drive higher engagement in the purchase funnel.
3.  **Note:** The drop in `new_account` creation was not statistically significant, but it is worth monitoring in future iterations.

---
---

# 🇺🇦 A/B Тестування: Аналіз Оптимізації Воронки

## 🌟 Огляд Проєкту

Цей проєкт демонструє повний цикл **A/B тестування** для оцінки впливу змін в інтерфейсі на конверсійну воронку користувача.
Аналіз охоплює вибірку даних за допомогою **SQL**, статистичну перевірку гіпотез у **Python** та фінальну візуалізацію в **Tableau**.

**Мета:** Визначити, чи призводять зміни в Тестовій групі (Group 2) до статистично значущого зростання конверсії порівняно з Контрольною групою (Group 1).

**Висновок:** Тест показав **статистично значущий позитивний вплив** на середню частину воронки (перехід до оплати), що підтверджує успішність експерименту.

---

## 🛠️ Використані Технології

| Категорія | Інструменти | Призначення |
| :--- | :--- | :--- |
| **Вибірка даних** | `Google BigQuery` (SQL) | Складний запит (CTE, Union) для агрегації подій. |
| **Статистичний аналіз** | `Python` (Pandas, Statsmodels) | Обробка даних та **Z-тест пропорцій**. |
| **Візуалізація** | `Tableau` | Валідація даних та презентація результатів. |

---

## 1. Методологія

### A. Валідація Даних
Перед аналізом ми переконалися у коректності тесту.
* **Розподіл трафіку:** Користувачі були розділені рівномірно **50/50**.
* **Гомогенність:** Розподіл за пристроями, континентами та країнами був ідентичним в обох групах.

![Validation Dashboard](Tableau%201.png)
*Рис 1. Валідація розподілу груп (Географія та Пристрої).*

### B. Статистичний Підхід
Ми розрахували **Коефіцієнт Конверсії (CR)** для ключових етапів воронки:
$$CR = \frac{\text{Унікальні Події}}{\text{Унікальні Сесії}}$$

Щоб перевірити значущість різниці, ми використали **Двохсторонній Z-тест пропорцій** з рівнем значущості ($\alpha$) 0.05.

---

## 2. Ключові Результати

Аналіз у Python показав наступні зміни показників:

| Метрика (Подія / Сесія) | Приріст (% Change) | P-Value | Статистично Значуще? |
| :--- | :---: | :---: | :---: |
| **begin_checkout** | **+8.50%** | < 0.05 | ✅ **Так** |
| **add_shipping_info** | **+7.13%** | < 0.05 | ✅ **Так** |
| **add_payment_info** | **+4.93%** | < 0.05 | ✅ **Так** |
| **new_account** | -3.35% | > 0.05 | ❌ Ні |

![Results Dashboard](Tableau%202.png)
*Рис 2. Результати A/B тесту та Z-статистика.*

---

## 3. Висновки та Рекомендації

1.  **Успіх:** Тестова версія значно покращила проходження користувачів через етапи оформлення замовлення.
2.  **Рекомендація:** **Впровадити зміни** для всіх користувачів, оскільки вони підвищують залученість у процес покупки.
3.  **Зауваження:** Падіння у створенні акаунтів (`new_account`) не було статистично значущим, але цей показник варто моніторити у майбутньому.
