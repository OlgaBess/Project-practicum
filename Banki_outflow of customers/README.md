# Анализ оттока клиентов банка.

Банку необходимо сегментирование пользователей, чтобы определить, как клиенты пользуются его услугами. 
Для отдела маркетинга нужны компактные однородные сегменты и примеры мероприятий, которые можно провести, чтобы вернуть клиентов в банк или удержать сомневающихся от оттока.


**Цель:**

Проанализировать клиентов регионального банка и выделить портрет клиентов, которые склонны уходить из банка, дать рекомендации для отдела маркетинга. 


**Описание данных в датасете:**

- userid — идентификатор пользователя,
- score — баллы кредитного скоринга,
- city — город,
- gender — пол,
- age — возраст,
- equity — приблизительная оценка собственности клиента,
- balance — баланс на счёте,
- products — количество продуктов, которыми пользуется клиент,
- credit_card — есть ли кредитная карта,
- last_activity — был ли клиент активен последнее время,
- salary — заработная плата клиента
- churn — уходит или нет.

Используемые библиотеки в работе:
import pandas as pd  
import numpy as np  

# библиотеки для построения графиков
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px

# библиотеки для построения моделей и расчета метрик
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split
from sklearn.utils.class_weight import compute_class_weight
from sklearn.linear_model import LogisticRegression
from sklearn.ensemble import RandomForestClassifier, GradientBoostingClassifier
from sklearn.tree import DecisionTreeClassifier, plot_tree
from sklearn.metrics import roc_auc_score, f1_score, recall_score, precision_score

# библиотеки для проведения статистических тестов
from statsmodels.stats.proportion import proportions_ztest
from scipy.stats import mannwhitneyu, ttest_ind
