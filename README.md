# Прогноз выручки пользователя за 30 дней

Задача: по признакам пользователя (платформа, язык и др.) предсказать `revenue_30d_total`, то есть выручку за первые 30 дней. Объём данных — около 2.9 млн записей.

## Подход

1. **EDA** ([`step1_EDA.ipynb`](step1_EDA.ipynb)): распределение выручки, пропуски, выбросы.
2. **Признаки**: агрегаты выручки (медиана и среднее) по платформе и языку, нормализация.
3. **Линейная регрессия** ([`step2_Modelling_Linear.ipynb`](step2_Modelling_Linear.ipynb)) как baseline: R² ≈ 0.44 на train и test, без переобучения.
4. **LightGBM** ([`step3_Modelling_LGBMRegressor.ipynb`](step3_Modelling_LGBMRegressor.ipynb)): нелинейные зависимости, сравнение с baseline.
5. **Оценка ошибки** по SMAPE и относительной ошибке, прогноз на `test.csv`.

Подробный отчёт с графиками — [`readme.pdf`](readme.pdf).

## Стек

Python · pandas · NumPy · scikit-learn · LightGBM · matplotlib
