---
math: true
---

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

$$A \rightarrow abc | K$$

$$B \rightarrow Ea$$

$$C \rightarrow BD$$

$$D \rightarrow CCA$$

$$E \rightarrow Fbb$$

$$F \rightarrow a$$

$$ T \rightarrow b $$

$$ K \rightarrow K$$

тогда:

$$\Gamma_p = \left\{S, A, E, B, F\right\}$$

$$\Gamma_r = \left\{S, A, E, B, F, T\right\}$$

Пример такой, что множества почти совпадают, но это не говорит о связи между производящими символами и достижимыми. Например $T$ — производящий, но недостижимый, а $K$ — достижимый и не производящий (хоть правило явно мусорное, которое его задает).

---
Обозначим $G \in \textrm{CFG}$ как $G$ — КСГ, мол $\textrm{CFU}$ — множество всех КСГ.

### Th $\forall G \in \textrm{CFG} \, \, \exists G'$ — приведенная грамматика, такая что  $G \overset{L}{=} G'$  (1)

Для доказательства приведем два алгоритма:

### Al Построение $\Gamma_p$

>
>* $$\Gamma_p = \left\{A \in \Gamma \vert (A \rightarrow w) \in P, w \in \Sigma^* \right\}$$
>* пока $\Gamma_p$ не стабильно:
>   * $$\Gamma_p = \Gamma_p \cup \left\{A \in \Gamma \vert (A \rightarrow \gamma) \in P, \gamma \in (\Sigma \cup \Gamma_p)^* \right\}$$

стабильно — больше не меняется.

Простыми словами — добавляем к $\Gamma_p$ символы, из которых выводятся слова, в которых есть символы из $\Gamma_p$.

### Al Построение $\Gamma_r$

>
>* $$\Gamma_r = \left\{S\right\}$$
>* пока $\Gamma_r$ не стабильно:
>   * $$\Gamma_r = \Gamma_r \cup \left\{A \in \Gamma \vert (B \rightarrow \alpha A \beta) \in P, B \in \Gamma_r\right\}$$

Опять простыми словами — нужно брать те символы, которые выводимы из некоторого элемента $\Gamma_r$.

### Al Построение приведенной грамматики $\widehat{G}$
>
>* Найти $\Gamma_p$
>   * $$\widehat{G}=$ если $S \notin \Gamma_r$$, то $$(\Sigma, \emptyset,\emptyset,\emptyset) \overset{L}{=} G$$, иначе $$(\Sigma, \Gamma, \widehat{P}, S)$$,  
>   где $$\widehat{P} = \left\{(A \rightarrow \gamma) \vert (A \rightarrow \gamma) \in P, \gamma \in (\Sigma \cup \Gamma_p)^*\right\}$$
>* Найти $(\Gamma_p)_r$
>   * $$\widetilde{G} = (\Sigma,(\Gamma_p)_r, \widetilde{P}, S)$$,  
>   где $$\widetilde{P} = \left\{ (A \rightarrow\gamma) \vert (A \rightarrow\gamma) \in \widehat{P}, \gamma \in (\Sigma \cup (\Gamma_p)_r)^* \right\}$$

### Pf Корректность алгоритма

*Доказав корректность алгоритма, мы докажем и теорему (1) по построению, мол "Просто используйте алгоритм".*

**TODO** *Тут было много слов и махания руками, но они утеряны, нужно прояснить и написать доказательство.* **TODO**

Порядок поиска множеств $\Gamma_p$ и $\Gamma_r$ важен: в таком порядке делать $(\Gamma_r)_p$ будет неверно!

### Пример применения алгоритмов поиска $\Gamma_p$ и $\Gamma_r$

$$S\rightarrow ab|bAc$$

$$A \rightarrow CB $$

$$ B \rightarrow aSA $$

$$C \rightarrow bC|d $$

1. > $$\Gamma_p = \left\{S,C\right\}$$
   > $$(\Gamma_p)_r = \left\{S\right\}$$
   > Как видно, такая грамматика не эквивалентна данной, значит в таком порядке применять не нужно.
2. > $$\Gamma_r = \left\{S,A,B,C\right\}$$
   > $$(\Gamma_p)_r = \left\{S,C\right\}$$

---

## $\lambda$-свободные грамматики

### Df Грамматика $G$ — $\lambda$-свободная

Обозначим как $G \in \textrm{CFG}_{\lambda}$
> Либо $\forall p \in G.P \,:\, p \neq (A \rightarrow \lambda)$,  
> либо $(S \rightarrow \lambda) \in G.P$ и $\forall p \in G.P \,:\, \left[\,p = (A \rightarrow \alpha), \, S \notin \alpha\right]$

То есть в грамматике нет символов, из которых напрямую выводится пустое слово, хотя для аксиомы такое разрешается при условии, что нет правил, в правой части которых встречается аксиома.

### Df Множество аннулирующих символов КСГ $G$

> $Ann(G) = \left\{A \in \Gamma\,\vert\, A \overset{*}{\underset{G}{\implies}} \lambda\right\}$

### Пример поиска $Ann(G)$

$$S \rightarrow aBC|A$$

$$A \rightarrow bC|\lambda$$

$$B \rightarrow ACA$$

$$C \rightarrow \lambda$$

$$E \rightarrow CA$$

$$D \rightarrow bE|c$$

Первыми берем очевидные символы из которых напрямую выводится пустой символ — $A$ и $C$. Потом те, из которых выводятся слова, содержащие символы,выбранные раньше, и не содержащие терминалы — $B$, $E$ и $S$.

$D \rightarrow bE \vert c$ не позволяет нам добавить $D$ к $Ann(G)$, так как из $D$ обязательно выведется какой-то непустой символ — $b$ или $c$, хотя из $E$ и выводится пустой символ.

$$Ann(G) = \left\{A,C,B, E, S\right\} $$

---

### Th $\forall G \in \textrm{CFU} \, \, \exists \, G' \in \textrm{CFU}_\lambda$ (2)

Для доказательства введем отношение $\llless$ на $(G.\Gamma \cup G.\Sigma)^*$ для некоторой $G \in \textrm{CFG}$:
$$\beta \llless \gamma  \iff \beta \text{— подпоследовательность } \gamma, \gamma\setminus\beta \in Ann(G) $$

### Al Построение $\lambda$-свободной грамматики $G'$ из $G$

>* Найти $Ann(G)$
>* $$\widehat{G}= (\Sigma, \Gamma, \widehat{P}, S)$$,  
>   где $$\widehat{P} = \left\{(A \rightarrow \beta) \,\vert \, (A \rightarrow \gamma) \in P, \, \beta \llless \gamma, \, \beta \neq \gamma\right\}$$
> * если $\lambda \in L(G)$, то  
>   $$\widehat{G} = (\Sigma, \Gamma \cup \widehat{S}, \widehat{P} \cup \left\{(\widehat{S} \rightarrow \lambda), (\widehat{S} \rightarrow S)\right\}, \widehat{S})$$

Последний шаг обеспечивает сохранение пустого слова в построенном языке тем, что добавляет новую аксиому к нему и правила перехода из нее в старую.

### Pf (2)

Опять говорим, что теорема доказывается применением алгоритма, докажем корректность алгоритма — докажем теорему.

> Проверим, что $L(G) = L(\widehat{G})$:
> возьмем $w \in L(\widehat{G}), \, w \neq \lambda$.
>
> $S \overset{*}{\underset{\widehat{G}}{\implies}} w$
>
> на каждом шаге машем руками и все получается…
>
> **TODO** доказательство упущено, нужно его дописать **TODO**

### Пример построения $\lambda$-свободной грамматики

$G$:

$$ S \rightarrow BC | cBd $$

$$ B \rightarrow BC | ab | \lambda $$

$$ C \rightarrow ac | \lambda $$

$$ Ann(G) = \left\{B,C,S\right\}$$

$\widehat{G}$:

$$ S \rightarrow BC | C| B | cbd | cd $$

$$ B \rightarrow BC | B | C | ab $$

$$ C \rightarrow ac $$
