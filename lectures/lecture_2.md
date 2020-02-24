# Лекция 2

## Праволинейные грамматики

*theorem* Класс праволинейных грамматик порождает класс регулярных языков

*proof* 
>Пусть $G = \left(\Sigma, \Gamma, P, S\right)$.
> Построим недетерминированный конечный автомат по грамматике $G$:
>
> $A = \left(\Sigma, \Gamma, \sigma, S, F\right)$, где
>  $$ \sigma: \left(\Gamma \times \Sigma \right) \rightarrow \Gamma \, \, \vert \, \, A \overset{a}{\rightarrow} B  \iff  \left(A \rightarrow aB \right) \in P $$
> $$ F = \left\{A \in \Gamma \, \vert \, \exists \left( A \rightarrow \lambda \right ) \in P \right\} $$

То есть указали правило преобразования грамматики в автомат, причем оно двухстороннее: если есть прямой переход между вершинами $A$ и $B$ по символу $a$, то в грамматике есть правило $\left( A \rightarrow aB \right )$.

## КСЯ и КСГ

*def* $G = \left(\Sigma, \Gamma, P, S\right)$ — **контекстно-свободная грамматика**
> $$ P = \left\{ (A \rightarrow \alpha) \, \vert \, A \in \Gamma, \, \alpha \in \left(\Sigma \cup \Gamma\right)^*\cdot\Gamma\cdot\left(\Sigma\cup \Gamma\right)^*\right\} $$

*Далее $\alpha$ всегда такое — слово над обоими алфавитами и хотя бы одной буквой из нетерминального алфавита.*

*def* Язык $L$ — контекстно-свободный
> $$ \exist \, G  - КСГ \, \vert \, L = L(G) $$

*def* Корневое дерево является **упорядоченным**
> *Пусть $child(n)$ — множество потомков узла $n$*
> 
> На его узлах задан линейный порядок $\lessdot$ со свойствами:
> 
> * $X$ — потомок $Y$ $\implies$  $Y\lessdot X$
> * $X$ — сосед $Y$, $Y \lessdot X$ $\implies$ $\forall Z \in child(Y): Z \lessdot X$

*def* $T$ — **дерево вывода** слова $w \in \Sigma^*$ в КСГ $G = \left(\Sigma, \Gamma, P, S\right)$
> *Пусть $mark(x) = X$ — функция, показывающая что меткой узла x является $X$*
> 
> $T$ — упорядоченное дерево, для которого выполняются условия:
> 
> * корень помечен $S$, метки внутренних узлов $m \in \Gamma$, листья $l \in \Sigma\cup\{\lambda\}$, листья с меткой $\lambda$ не имеют соседей.
> * $x$ — узел, $\{y_1,…,y_k\} = child(x)$, $y_1 \lessdot y_2 \lessdot … \lessdot y_k$, $mark(y_i) = Y_i$, $mark(x) = X$ $\implies$ $X \underset{G}{\implies} Y_1\cdot Y_2\cdot …\cdot Y_n$
> * $\{z_i \, \vert \, mark(z_i) = A_i, \, z_i \text{— листья } T \}_{i = 1}^{n} \implies w = A_1\cdot A_2\cdot …\cdot A_n$

