# Лекция 3

## Приведенные грамматики

### Df Грамматика $G$ эквивалентна грамматике $G'$: $G \overset{L}{=} G'$

> $$L(G) = L(G') $$

Дальше все для некоторой грамматики $G = (\Sigma, \Gamma, P, S)$, так же будем обозначать $G.\Gamma$ — множество нетерминалов грамматики $G$ — как свойство в каком-нибудь ЯП

### Df $A \in \Gamma$ — производящий

> $\exists w \in \Sigma^* : A \overset{*}{\implies} w$

### Df $A \in \Gamma$ — достижимый

> $\exists \alpha, \beta \in (\Sigma \cup \Gamma)^* \ : A \overset{*}{\implies} \alpha A \beta$

*Далее $\alpha$ и $\beta$ всегда такие же.*

Нас интересуют такие грамматики, в которых меньше всего мусора, где нет недостижимых и не производящих символов.

Пусть $\Gamma_p$ — множество производящих символов (от *producing*), а $\Gamma_r$ — множество достижимых символов (от *reachable*).

### Df $G$ — приведенная

> $$ \forall A \in G.\Gamma : A \text{ — достижимый и производящий} $$

## Пример множеств достижимых и производящих символов

Пусть $G$ задается так:
$$S \rightarrow bAc | AcB$$

$$A \rightarrow abc$$

$$B \rightarrow Ea$$

$$C \rightarrow BD$$

$$D \rightarrow CCA$$

$$E \rightarrow Fbb$$

$$F \rightarrow a$$

тогда:

$$\Gamma_p = \{F, A, E, S, B\}$$

$$\Gamma_p = \{F, A, E, S, B\}$$

---

### Th $\forall G$ : $G$ — КСГ $\exist G'$ — приведенная грамматика, такая что  $G \overset{L}{=} G'$  (1)

Для доказательства приведем два алгоритма:

### Al Построение $\Gamma_p$

>
>* $\Gamma_p = \{A \in \Gamma \vert (A \rightarrow w) \in P, w \in \Sigma^* \}$
>* пока $\Gamma_p$ не стабильно:
>   * $\Gamma_p = \Gamma_p \cup \{A \in \Gamma \vert (A \rightarrow \gamma) \in P, \gamma \in (\Sigma \cup \Gamma_p)^* \}$

стабильно — больше не меняется.

Простыми словами — добавляем к $\Gamma_p$ символы, из которых выводятся слова, в которых есть символы из $\Gamma_p$.

### Al Построение $\Gamma_r$

>
>* $\Gamma_r = \{S\}$
>* пока $\Gamma_r$ не стабильно:
>   * $\Gamma_r = \Gamma_r \cup \{A \in \Gamma \vert (B \rightarrow \alpha A \beta) \in P, B \in \Gamma_r\}$

Опять простыми словами — нужно брать те символы, которые выводимы из некоторого элемента $\Gamma_r$.

### Al Построение приведенной грамматики $\widehat{G}$
>
>* Найти $\Gamma_p$
>   * $\widehat{G}=$ если $S \notin \Gamma_r$, то $(\Sigma, \emptyset,\emptyset,\emptyset) \overset{L}{=} G$, иначе $(\Sigma, \Gamma, \widehat{P}, S)$,  
>   где $\widehat{P} = \{(A \rightarrow \gamma) \vert (A \rightarrow \gamma) \in P, \gamma \in (\Sigma \cup \Gamma_p)^*\}$
>* Найти $(\Gamma_p)_r$
>   * $\widetilde{G} = (\Sigma,(\Gamma_p)_r, \widetilde{P}, S)$,  
>   где $\widetilde{P} = \{ (A \rightarrow\gamma) \vert (A \rightarrow\gamma) \in \widehat{P}, \gamma \in (\Sigma \cup (\Gamma_p)_r)^* \}$

### Pf Корректность алгоритма

*Доказав корректность алгоритма, мы докажем и теорему (1) по построению, мол "Просто используйте алгоритм".*

**TODO***Тут было много слов и махания руками, но они утеряны, нужно прояснить и написать доказательство.*

Порядок поиска множеств $\Gamma_p$ и $\Gamma_r$ важен: $(\Gamma_r)_p$ будет неверным!

