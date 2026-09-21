# Breast Cancer Classification

Учебный проект бинарной классификации опухолей по числовым признакам.
Положительный класс (`1`) — злокачественная опухоль. Главная метрика —
recall, поскольку FN означает пропущенный злокачественный случай.

## Данные и метод

Использован датасет `load_breast_cancer` из scikit-learn: 569 объектов
и 30 признаков. Данные разделены на train и test с сохранением
пропорций классов. Модели сравнивались с помощью стратифицированной
5-кратной кросс-валидации.

Сравнены DummyClassifier, Logistic Regression, Decision Tree,
Random Forest и Gradient Boosting. Для итоговой модели выбран
Gradient Boosting; параметры подобраны по CV.

## Результаты

- CV recall: 0.959
- CV F1: 0.970
- Test recall: 0.929
- Test F1: 0.963
- Test ROC-AUC: 0.995
- Ошибки на тесте: 3 FN и 0 FP

При снижении порога можно уменьшить число FN, но возрастает число FP.
В итоговой модели оставлен порог 0.5.

## Воспроизведение

Откройте `breast_cancer_classification.ipynb` в Google Colab и
выполните все ячейки сверху вниз. Датасет загружается через
scikit-learn; отдельный файл данных не требуется. Ноутбук также
создаёт файл `breast_cancer_model.joblib`.

## Ограничения

Тестовая выборка использовалась во время учебного исследования,
поэтому её результат не является полностью независимой оценкой
окончательного выбора модели. Проект не предназначен для медицинского
применения.

Ссылки
- [Соревнование на Kaggle](https://www.kaggle.com/competitions/spaceship-titanic)
- [Ноутбук в Google Colab](https://colab.research.google.com/drive/1ijxrGnHhADEDd5_WanqJCrSE7_AJEb0S?usp=sharing)
- [Мой профиль Kaggle](https://www.kaggle.com/potsml)

Контакты
- Telegram: @antaleksandr
- Email: AntAleksandrGit@gmail.com
