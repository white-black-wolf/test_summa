<a id="up"></a>

<p align="center">
 <img src="https://i.ibb.co/99qgRP3/summma.jpg" alt="Project logo"width="726">
</p>
<p align="center">
 <img src="https://img.shields.io/badge/python-3.11-blue" alt="Версия python">
 <img src="https://img.shields.io/badge/version-0.1(beta)-purple" alt="Версия игры">
 <img src="https://img.shields.io/badge/license-MIT-brightgreen" alt="Лицензия">
</p>

## 📑Оглавление
- [Описание задачи](#task)
- [O проеке](#about_project)
- [Рабочий процесс](#process)
- [Документация](#documentation)
- [Разработчики](#developers)
- [Лицензия](#license)

<a id="task"></a>
## 📖Описание задачи
На вход программе подаётся текст. Результатом работы программы должен стать тип поста в котором мог быть этот текст!


<a id="about_project"></a>
## 📁О проекте
Мы разработали **Классификатор постов в социальной сети ВКонтакте**.
Это система, предназначенная для автоматической классификации контента, размещаемого пользователями. Его основная задача заключается в анализе и сортировке постов по темам.

Классификатор использует алгоритмы машинного обучения и обработки естественного языка, чтобы определить содержание постов и их назначение. Например, он может отличать посты, относящиеся к новостям, развлекательному контенту, образовательным материалам и т.д. Это позволяет пользователям быстрее находить интересующий их контент и улучшает качество взаимодействия в социальной сети.

Кроме того, такая система может быть полезна для рекламодателей, которые хотят таргетировать свою аудиторию более точно, выбирая посты, соответствующие определённой категории или интересам пользователей. В результате, классификатор постов в ВКонтакте способствует более организованному и эффективному контенту на платформе.


<a id="process"></a>
## ✍️Рабочий процесс
- Сбор необходимых данных.
-  Предварительная обработка данных.
-  Выбор и обучение модели.
-  Оценка решения.
-   Презентация решения.


<a id="documentation"></a>
## 🗃️Документация

Данный проект создан с целью определения типов постов в социальных сетях!

Для анализа текста с помощью модели машинного обучения над каждым текстом мы провели несколько манипуляций:
- [Очистка данных](https://en.wikipedia.org/wiki/Data_cleansing) - удаление ненужных символов, таких как пунктуация, цифры и стоп-слова (часто встречающиеся слова, которые не несут значимой информации). Этот шаг помогает уменьшить шум в данных и улучшить качество анализа. 
- [Нормализация текста](https://en.wikipedia.org/wiki/Text_normalization) — это метод преобразования текста в единую каноническую форму. 2 Она помогает уменьшить количество уникальных слов в тексте, что упрощает дальнейший анализ
- [Токенизация](https://wiki.loginom.ru/articles/tokenization.html) — это процесс разделения текста на составляющие (токены).
- [Векторизация текста](https://wiki.loginom.ru/articles/text-data-vectorization.html) — это процесс преобразования текста в числовой формат, который могут понимать и обрабатывать алгоритмы машинного обучения

Для очистки, нормализации и токенизации мы использовали библиотеку spacy и обученный конвейер для русского языка [ru_core_news_lg](https://spacy.io/models/ru).

Итак, с очисткой, нормализацией и токенизацией данных всё понятно, топерь осталось выбрать модель машинного обучения и метод векторизации! Как мы их выбрали? Всё просто! Мы выбрали лучшее сочетание по соотношению точности и времени!
Вот результат наших тестов:

<h3>Точность</h3> 

модель/метод | TF-IDF | Bag-of-Words | Word Embeddings
:------------:|:------:|:------------:|:----------------:
[Нейронная сеть](https://ru.wikipedia.org/wiki/Нейронная_сеть) | 50 | 51 | 59
[SVM](https://ru.wikipedia.org/wiki/Метод_опорных_векторов) | 64 | 65 | 63
[MultinomialNB](https://sklearn.vercel.app/docs/classes/MultinomialNB) | 58 | 67 | 71

<h3>Скорость</h3> 

модель/метод | TF-IDF | Bag-of-Words | Word Embeddings
:------------|:------:|:------------:|----------------:
[Нейронная сеть](https://ru.wikipedia.org/wiki/Нейронная_сеть) | | |
[SVM](https://ru.wikipedia.org/wiki/Метод_опорных_векторов) | | |
[MultinomialNB](https://sklearn.vercel.app/docs/classes/MultinomialNB) | | |

По результатам наших тестов мы выбрали модель машинного обучения MultinomialNB из библиотеки [sklearn.naive_bayes](https://scikit-learn.org/stable/modules/naive_bayes.html) и метод векторизация [Bag-of-Words](https://ru.wikipedia.org/wiki/Мешок_слов) из библиотеки [sklearn.feature_extraction.text](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html).

Multinomial Naive Bayes (MultinomialNB) — это мощный алгоритм, известный своей простотой и эффективностью в задачах классификации текстов. Он представляет собой вероятностный алгоритм, основанный на [теореме Байеса](https://ru.wikipedia.org/wiki/Теорема_Байеса), с допущением о независимости между характеристиками.

[Bag-of-Words](https://ru.wikipedia.org/wiki/Мешок_слов) - упрощенное представление текста, которое используется в обработке естественных языков и информационном поиске.


<a id="developers"></a>
## 👨🏻‍💻Разработчики

- [wbw](https://github.com/white-black-wolf)
- [Vanish](https://github.com/vanish12345)   

<a id="license"></a>
## 🏛️Лицензия
Проект sirius_AI распространяеться под лицензией MIT.

 [Лицензия](https://github.com/white-black-wolf/sirius_AI/blob/main/LICENSE)
 
<br></br>

 [Вверх](#up)
