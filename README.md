---
math: true
---

# Лекции по ЛОИ (лингвистические основы информатики) aka Компиляторы

## Материалы

* [Страница преподавателя на сайте кафедры](http://kadm.kmath.ru/pages.php?id=seamrog)
* [Задачки](https://www.dropbox.com/s/774f50efo1lma6u/loi_tasks.pdf?dl=0)
* [Dragon book](https://github.com/lehaSVV2009/Compiler/blob/master/books/%D0%90%D1%85%D0%BE%2C%20%D0%A1%D0%B5%D1%82%D0%B8%2C%20%D0%A3%D0%BB%D1%8C%D0%BC%D0%B0%D0%BD.%20%D0%9A%D0%BE%D0%BC%D0%BF%D0%B8%D0%BB%D1%8F%D1%82%D0%BE%D1%80%D1%8B.%20%D0%9F%D1%80%D0%B8%D0%BD%D1%86%D0%B8%D0%BF%D1%8B%2C%20%D1%82%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D0%B8%2C%20%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B.2ed.2008.pdf)
* [Ахо, Ульман "Теория синтаксического анализа, перевода и компиляции"](https://github.com/afrolovskiy/compilers_labs/blob/master/literature/%D0%90%D1%85%D0%BE%20%D0%90.%2C%20%D0%A3%D0%BB%D1%8C%D0%BC%D0%B0%D0%BD%20%D0%94%D0%B6.%20%D0%A2%D0%B5%D0%BE%D1%80%D0%B8%D1%8F%20%D1%81%D0%B8%D0%BD%D1%82%D0%B0%D0%BA%D1%81%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B3%D0%BE%20%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%2C%20%D0%BF%D0%B5%D1%80%D0%B5%D0%B2%D0%BE%D0%B4%D0%B0%20%D0%B8%20%D0%BA%D0%BE%D0%BC%D0%BF%D0%B8%D0%BB%D1%8F%D1%86%D0%B8%D0%B8.%20%D0%A2%D0%BE%D0%BC%201.%20%D0%9A%D0%BE%D0%BC%D0%BF%D0%B8%D0%BB%D1%8F%D1%86%D0%B8%D1%8F%20(1978).djvu)
* [Языки, грамматики, распознаватели (Шур, Замятин)](http://kadm.kmath.ru/files/shurzam.pdf)

## Обозначения

Определение выглядит вот так:

### Df **Что-то** определяется вот так:

> Вот так вот так

Теорема выглядит вот так:

### Th **Что-то** как-то (1)

> Вот так вот так

А вот так лемма:

### Lm бла-бла

Их доказательство:

### Pf 1

> Потому-то вот так

Если очевидно, к какой теореме или лемме доказательство, то номер можно опустить (*Вместо номера можно хоть гуид лол*)

Вот так выглядит алгоритм:

### Al Что-то того-то

> Раз раз раз

---

## [Лекция 1](./lectures/lecture_1.md) Структура языка, базовые определения

## [Лекция 2](./lectures/lecture_2.md) Праволинейные грамматики, КСГ, дерево вывода

## [Лекция 3](./lectures/lecture_3.md) Приведенные грамматики, $\lambda$-свободные грамматики

## [Лекция 4](./lectures/lecture_4.md) Нормальная форма Хомского, Pumping lemma

## [Лекция 5](./lectures/lecture_5.md) Свойства КС-грамматик

## [Лекция 6] TODO

## [Лекция 7 и 8](lectures/lecture_7.md) Алгоритм Кока-Янгера-Касами. МПА. Конфигурации ДМПА и НМПА.

# Алгоритмы
*  [Построение  $\Gamma_p$](https://funfunfine.github.io/loi/lectures/lecture_3.html#al-%D0%BF%D0%BE%D1%81%D1%82%D1%80%D0%BE%D0%B5%D0%BD%D0%B8%D0%B5-gamma_p)
*  [Построение $\Gamma_r$](https://funfunfine.github.io/loi/lectures/lecture_3.html#al-%D0%BF%D0%BE%D1%81%D1%82%D1%80%D0%BE%D0%B5%D0%BD%D0%B8%D0%B5-gamma_r)
*  [Построение $\widehat{\Gamma}$](https://funfunfine.github.io/loi/lectures/lecture_3.html#al-%D0%BF%D0%BE%D1%81%D1%82%D1%80%D0%BE%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B8%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%BD%D0%BE%D0%B9-%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B0%D1%82%D0%B8%D0%BA%D0%B8-widehatg)
*  