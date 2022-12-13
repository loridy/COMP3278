# Database Design: Functional Dependency #

## Functional Dependency ##
* Definition
  * X $\rightarrow$ Y if X functionally determine Y (each X is associated with **precisely one** Y)
  * eg. {employee_id} $\rightarrow$ {name, phone}

* Armstrong's Axioms
  * **Reflexivity**: if $\beta$ is a subset of $\alpha$, then $\alpha \rightarrow \beta$
    * eg. AB $\rightarrow$ A
  * **Transitivity**: if $\alpha \rightarrow \beta$, and $\beta \rightarrow \gamma$, then $\alpha \rightarrow \gamma$
    * eg. if B $\rightarrow$ C and C $\rightarrow$ D, then B $\rightarrow$ D.
  * **Augmentation**: if $\alpha \rightarrow \beta$, then $\gamma\alpha \rightarrow \gamma\beta$
    * eg. if B $\rightarrow$ C, then AB $\rightarrow$ AC

* Additional rules
  * **Union**: if $\alpha \rightarrow \beta$, and $\alpha \rightarrow \gamma$, then $\alpha \rightarrow \beta\gamma$
    * eg. if B $\rightarrow$ C, and B $\rightarrow$ D, prove that: B $\rightarrow$ CD
    * Prove:
    * B $\rightarrow$ BC (augmentation)
    * BC $\rightarrow$ CD (augmentation)
    * therefore, B $\rightarrow$ CD (transitivity)
  * **Decomposition**: if $\alpha \rightarrow \beta\gamma$, then $\alpha \rightarrow \beta$, and $\alpha \rightarrow \gamma$ (reverse of Union)
    * eg. if B $\rightarrow$ CD, prove that: B $\rightarrow$ C, and B $\rightarrow$ D
    * Prove:
    * CD $\rightarrow$ C (reflexivity)
    * CD $\rightarrow$ D (reflexivity)
    * Therefore, B $\rightarrow$ C and B $\rightarrow$ D (transitivity)
  * **Pseudo-transitivity**: if $\alpha \rightarrow \beta$ and $\gamma\beta \rightarrow \delta$, then $\gamma\alpha \rightarrow \delta$
    * eg. if B $\rightarrow$ C and AC $\rightarrow$ D, prove that: AB $\rightarrow$ D
    * Prove:
    * AB $\rightarrow$ AC (augmentation)
    * Therefore, AB $\rightarrow$ D (transitivity)

## Attribute Set Closure ##
* Definition
  * closure of $\alpha$( $\alpha^{+}$ ) is the **set of attributes** that can be functionally determined by α
  * eg. $F = \lbrace A \rightarrow B, B \rightarrow C\rbrace$
  * $\lbrace A \rbrace ^{+} = \lbrace A, B, C \rbrace$
* Computation
  * result = $\alpha$
  * $while\  (changes\ to\ result)\lbrace for\ each\ \beta \rightarrow \gamma\ \lbrace if\ \beta \subseteq result,\ then\ result=result \cup \gamma \rbrace \rbrace$
* Use of $\alpha^{+}$
  * Test for superkey: $\alpha^{+}$ is a super key of R if $\alpha^{+}$ contains all attributes of R
  * Check if the decomposition of a relation is **dependency preserving** or not
  * Calculate FD closure $F^{+}$, which is an important tool in database normalization 
    * (eg. The Boyce-Codd normal form BCNF.)

## FD Closure $F^{+}$ ##
* Definition
  * The set of all functional dependencies that can be logically implied by F
* Step1: Treat every subset of R as $\alpha$
* Step2: For each $\alpha$, compute $\alpha^{+}$
* Step3: Use $\alpha$ as LHS, and generate a FD for every subset of $\alpha^{+}$ on RHS










