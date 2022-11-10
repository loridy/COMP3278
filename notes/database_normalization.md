# Database Normalization #

## Decomposition ##
* **Lossless-join decomposition**: Avoid the decomposition result in information loss.
  * A decomposition of R into R1 and R2 is lossless-join if and only if at least one of the following dependencies is in F+
  * schema of R1 $\cap$ schema of R2 $\rightarrow$ schema of R1, OR
  * schema of R1 $\cap$ schema of R2 $\rightarrow$ schema of R2
* **Dependency preserving decomposition**
  * **Avoid the need to join** the decomposed relations to check the functional dependencies
  * A decomposition is dependency preserving if and only if
  * $(F1 \cup F2 \cup F3 \cup\ ...\ \cup\ Fn)^{+} = F^{+}$

## Normal Form ##
* **Boyce-Codd Normal Form (BCNF)**: has no redundancy
  * For all FDs in $F^{+}$ of form $\alpha \rightarrow \beta$, where $\alpha \subseteq R\ and\ \beta \subseteq R$, at least one of the following holds:
  * $\alpha \rightarrow \beta$ is trivial ( $\beta \subseteq \alpha$), OR
  * $\alpha$ is key(superkey) for R ( $\alpha^{+}$ covers all attributes in R)
* Verify:
  * For each non-trivial dependency $\alpha \rightarrow \beta$ in $F^{+}$, check if $\alpha^{+}$ covers whole relation
* Simplified verification:
  * check only dependencies in given F
    * eg. Given R = {A, B, C}; F = $\lbrace A \rightarrow B, B \rightarrow C \rbrace $ 
    * Check if $\lbrace A \rbrace ^{+}\ and\ \lbrace B \rbrace ^{+}$ cover {A, B, C}
  * Need to use $F^{+}$ instead of F if decomposed into R1 and R2

## Normalization ##
* Goal
  * Lossless-join
  * No redundency
  * Dependency preserving
  * 
