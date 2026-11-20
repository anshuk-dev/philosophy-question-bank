# Contemporary Analytic Philosophy: Formal Logic, Modal Logic, and Fallacies
## Propositional Logic, Predicate Logic, Modal Systems, and Formal & Informal Fallacies

---

### Question 1: Propositional Logic: Formal Deductive Proofs and Rules of Replacement
**Format**: Formal Proof / Logic Derivation Analysis  
**Topic**: Natural Deduction in Propositional Calculus — Copi Rules of Inference & Replacement

Consider the following formal deductive argument in standard propositional logic:
1. $P \to (Q \lor R)$
2. $P \land \neg Q$
3. $(P \land R) \to S$
$$\therefore S$$

A logician constructs the following deduction to derive the conclusion $S$:
- **Step 4**: $P$ (from line 2, by *Simplification*)
- **Step 5**: $\neg Q$ (from line 2, by *Simplification*)
- **Step 6**: $Q \lor R$ (from lines 1 and 4, by *Modus Ponens*)
- **Step 7**: $R$ (from lines 6 and 5, by *Disjunctive Syllogism*)
- **Step 8**: $P \land R$ (from lines 4 and 7, by *Conjunction*)
- **Step 9**: $S$ (from lines 3 and 8, by *Modus Ponens*)

Now consider an alternative one-step transformation that directly yields $(P \land R) \to S$ into an equivalent conditional form using the **Rule of Exportation**. What is that logically equivalent form, and what would happen if Step 7 had applied *Disjunctive Syllogism* to $Q \land R$ instead of $Q \lor R$?

A. By Exportation, $(P \land R) \to S$ is logically equivalent to $P \to (R \to S)$; Disjunctive Syllogism is valid only for disjunctions ($Q \lor R$), and applying it to a conjunction ($Q \land R$) would commit a formal category error, though in this proof Step 6 is indeed a disjunction and the derivation is entirely valid.  
B. By Exportation, $(P \land R) \to S$ is logically equivalent to $(P \to R) \land (P \to S)$; the derivation is invalid because Disjunctive Syllogism requires both disjuncts to be negated.  
C. By Exportation, $(P \land R) \to S$ is equivalent to $\neg (P \land R) \lor S$ by Material Implication; Step 7 is invalid because Modus Tollens should have been used instead of Disjunctive Syllogism.  
D. By Exportation, $(P \land R) \to S$ is equivalent to $S \to (P \land R)$ by Transposition; the proof is a formal fallacy of Affirming the Consequent.

**Correct Answer**: **A**

#### Philosophical Grounding & Demonstration:
1. **The Rule of Exportation**:
   In formal propositional logic, the Rule of Replacement known as **Exportation** is formally stated as:
   $$((p \land q) \to r) \equiv (p \to (q \to r))$$
   Applied directly to Premise 3, $((P \land R) \to S)$ transforms into:
   $$P \to (R \to S)$$
   This captures the logical principle that if the joint presence of $P$ and $R$ entails $S$, then given $P$, $R$ on its own entails $S$.
2. **Evaluation of the Deduction Steps**:
   - Step 4 ($P$) and Step 5 ($\neg Q$) follow strictly from $P \land \neg Q$ by Simplification ($p \land q \vdash p$ and $p \land q \vdash q$).
   - Step 6 ($Q \lor R$) follows from line 1 ($P \to (Q \lor R)$) and line 4 ($P$) by Modus Ponens ($p \to q, p \vdash q$).
   - Step 7 ($R$) follows from line 6 ($Q \lor R$) and line 5 ($\neg Q$) by Disjunctive Syllogism ($p \lor q, \neg p \vdash q$). This rule requires an exclusive or inclusive disjunction where one branch is negated.
   - Step 8 ($P \land R$) joins line 4 ($P$) and line 7 ($R$) by Conjunction ($p, q \vdash p \land q$).
   - Step 9 ($S$) follows from line 3 ($(P \land R) \to S$) and line 8 ($P \land R$) by Modus Ponens.
   The proof is formally flawless, sound, and valid.
3. The equivalence cited in option B ($(P \to R) \land (P \to S)$) is NOT Exportation; that is the equivalence for $P \to (R \land S)$. The equivalence in C ($\neg (P \land R) \lor S$) is the Rule of **Material Implication**, not Exportation. The equivalence in D ($S \to (P \land R)$) is the converse, which is a fallacy.

#### Distractor Analysis:
- **B is incorrect**: It misstates the Rule of Exportation (confusing it with distribution of implication over conjunction) and falsely claims the proof is invalid.
- **C is incorrect**: While $\neg (P \land R) \lor S$ is indeed equivalent by Material Implication, it is not the Rule of Exportation.
- **D is incorrect**: Transposition asserts $(p \to q) \equiv (\neg q \to \neg p)$, not the reversal of antecedent and consequent, which is the fallacy of conversion of a conditional.

**Primary Source**: Irving M. Copi, Carl Cohen, and Kenneth McMahon, *Introduction to Logic* (Routledge); Patrick Suppes, *Introduction to Logic* (Van Nostrand, 1957).

---

### Question 2: Predicate Logic: Quantifier Rules and Validity Restrictions
**Format**: Conceptual / Formal Multiple-Choice  
**Topic**: First-Order Predicate Logic — Universal Instantiation (UI), Universal Generalization (UG), Existential Instantiation (EI), and Existential Generalization (EG)

In standard natural deduction systems for First-Order Predicate Logic (such as Copi's or Suppes' system), the four quantifier rules allow transitions between quantified statements and their singular instantiations. Which of the following describes a fatal violation of the strict restrictions governing **Existential Instantiation (EI)** or **Universal Generalization (UG)** that would allow a fallacious derivation of an invalid conclusion?

A. Deriving $Fa$ from $\forall x Fx$ using Universal Instantiation, where $a$ is an individual constant already present in the premises.  
B. Instantiating an existential quantifier $\exists x Fx$ to an individual constant or variable $a$ using Existential Instantiation, where $a$ has already appeared in an earlier line of the proof or occurs free in the conclusion or premises.  
C. Generalizing from an arbitrary variable $x$ to $\forall x Fx$ using Universal Generalization, where $x$ was introduced via Universal Instantiation from a universal premise.  
D. Applying Existential Generalization from $Fa$ to $\exists x Fx$, where $a$ is a specific named individual.

**Correct Answer**: **B**

#### Philosophical Grounding & Demonstration:
In First-Order Predicate Logic, moving between quantified formulas and propositional instances requires strict safeguards to preserve truth:
1. **Existential Instantiation (EI)**:
   From $\exists x Fx$, one may infer $Fa$ (or $Fy$), under the absolute condition that the instantiating symbol must be a **completely new variable/constant** that has *never appeared previously* anywhere in the proof, does not occur in the premises, and does not occur in the conclusion.
   **Why this restriction is mandatory**:
   Suppose the restriction were ignored. Consider the premises:
   - Line 1: $\exists x Cx$ ("Someone is a criminal")
   - Line 2: $\exists x Px$ ("Someone is a police officer")
   If one could instantiate Line 1 to the constant $a$ ($Ca$), and then illegitimately instantiate Line 2 to the *same* constant $a$ ($Pa$), one could conjoin them to get $Ca \land Pa$ and infer:
   - Line 5: $\exists x (Cx \land Px)$ ("Someone is both a criminal and a police officer").
   This would allow one to infer an absurd, invalid conclusion from two independent, true existential premises! The restriction ensures that the name introduced by EI represents an unknown, arbitrary representative entity about which nothing else is known.

2. **Universal Generalization (UG)**:
   From $Fy$, one may infer $\forall x Fx$ only if $y$ represents a genuinely arbitrary individual—meaning $y$ was not introduced by EI, is not free in any active assumptions/premises, and has no special properties attributed to it.

#### Distractor Analysis:
- **A is incorrect**: Universal Instantiation (UI) has no such restriction; if a property holds for all $x$ without exception ($\forall x Fx$), it holds universally for *any* individual constant $a$, whether $a$ already appears in the proof or not.
- **C is incorrect**: Applying UG to an arbitrary variable introduced via UI is the standard, valid method for proving universal conditionals.
- **D is incorrect**: Existential Generalization (EG) is unconditionally valid: if a specific individual $a$ has property $F$ ($Fa$), it logically follows that there exists at least one thing that has property $F$ ($\exists x Fx$).

**Primary Source**: Patrick Suppes, *Introduction to Logic* (D. Van Nostrand, 1957, Chapter 4); Irving M. Copi, *Symbolic Logic* (Macmillan, 5th ed., 1979).

---

### Question 3: Predicate Logic: Polyadic Relations and Quantifier Order
**Format**: Conceptual Multiple-Choice (Advanced)  
**Topic**: Relational Predicates and Scope of Quantifiers

Let the domain of discourse be the set of all human beings. Let $Lxy$ denote the two-place relational predicate "$x$ loves $y$."
Consider the two distinct first-order sentences:
$$\text{Sentence 1: } \forall x \exists y Lxy$$
$$\text{Sentence 2: } \exists y \forall x Lxy$$
Which of the following statements correctly evaluates their semantic translations, their logical entailment relation, and the specific formal fallacy committed if one attempts to deduce Sentence 2 from Sentence 1?

A. Sentence 1 asserts "There is a single universal beloved whom everyone loves"; Sentence 2 asserts "Everyone has someone or other whom they love"; Sentence 1 entails Sentence 2, and the reverse is valid by Existential Generalization.  
B. Sentence 1 asserts "Everyone loves someone (or other)"; Sentence 2 asserts "There exists someone whom everyone loves"; Sentence 2 entails Sentence 1, but Sentence 1 does NOT entail Sentence 2; inferring Sentence 2 from Sentence 1 commits the **Quantifier Shift Fallacy**.  
C. Both sentences are logically equivalent due to the Commutative Law of Quantifiers ($\forall x \exists y \equiv \exists y \forall x$).  
D. Sentence 1 asserts "Someone loves everyone"; Sentence 2 asserts "Everyone is loved by someone"; Sentence 1 entails Sentence 2 by De Morgan’s laws for quantifiers.

**Correct Answer**: **B**

#### Philosophical Grounding & Demonstration:
In polyadic predicate logic, the linear order of different quantifiers governs their scope and fundamentally alters their truth-conditions:
1. **Sentence 1 ($\forall x \exists y Lxy$)**:
   - The universal quantifier has wide scope. For every person $x$, there exists some person $y$ (where $y$ can depend on $x$) such that $x$ loves $y$.
   - Natural language translation: "Everyone loves someone or other" (each person has their own beloved: Alice loves Bob, Charlie loves Dana, etc.).
2. **Sentence 2 ($\exists y \forall x Lxy$)**:
   - The existential quantifier has wide scope. There is at least one specific, unique person $y$ who is simultaneously loved by every single person $x$ in the domain.
   - Natural language translation: "There is someone whom everyone loves" (a universal beloved, like an idol).

3. **Entailment Relation and the Quantifier Shift Fallacy**:
   - **Direction $\text{Sentence 2} \implies \text{Sentence 1}$ is VALID**: If there is indeed a single person whom everyone loves, then trivially, every person loves someone.
   - **Direction $\text{Sentence 1} \implies \text{Sentence 2}$ is INVALID**: From the fact that every person has a mother ($\forall x \exists y Mxy$), it does not follow that there is a single woman who is the mother of all humanity ($\exists y \forall x Mxy$).
   - Deducing an existential quantifier with wide scope from a universal quantifier with wide scope over an existential quantifier is a catastrophic formal error known as the **Quantifier Shift Fallacy**. This fallacy famously infects faulty cosmological arguments (e.g., "Every event has a cause; therefore, there is one universal Cause of all events").

#### Distractor Analysis:
- **A is incorrect**: It reverses the translations of the two sentences and erroneously claims that the inference from 1 to 2 is valid.
- **C is incorrect**: Quantifiers of *different* kinds do NOT commute ($\forall x \exists y \not\equiv \exists y \forall x$). Only homogeneous quantifiers commute ($\forall x \forall y \equiv \forall y \forall x$ and $\exists x \exists y \equiv \exists y \exists x$).
- **D is incorrect**: It misidentifies which variable occupies the agent and patient arguments of the relation and misapplies De Morgan's laws.

**Primary Source**: W.V.O. Quine, *Methods of Logic* (Harvard University Press, 1950/1982); E.J. Lemmon, *Beginning Logic* (Nelson, 1965).

---

### Question 4: Russell's Theory of Descriptions in Formal Predicate Logic
**Format**: Formal Symbolization Analysis  
**Topic**: The Iota Operator $(\iota x)$ and First-Order Translation with Identity

Using the language of first-order logic with identity, let:
- $Fx$: "$x$ is a French monarch" (or "present King of France")
- $Bx$: "$x$ is bald"
How is Russell's formal translation of the proposition "The present King of France is bald" represented without using the primitive descriptive iota operator $(\iota x)Fx$, and what exact condition makes the proposition false in the actual world?

A. $\forall x (Fx \to Bx)$; false because the antecedent is empty.  
B. $\exists x [Fx \land \forall y (Fy \to y = x) \land Bx]$; false because the existential conjunct ($\exists x Fx$) is not satisfied in the actual world.  
C. $\exists x (Fx \land Bx) \land \forall x (Fx \to Bx)$; false because the uniqueness clause is omitted.  
D. $(\iota x)Fx = Bx$; false because identity cannot link an object with a predicate.

**Correct Answer**: **B**

#### Philosophical Grounding & Demonstration:
In *Principia Mathematica* (*14), Bertrand Russell and A.N. Whitehead introduce the contextual definition of definite descriptions. The natural language expression "The $F$ is $G$" is symbolized using the iota operator as:
$$G((\iota x)Fx)$$
Russell eliminates the incomplete symbol $(\iota x)Fx$ by translating the entire sentence into the standard language of first-order predicate logic with identity as a three-part conjunction:
1. **At least one**: $\exists x Fx$ (There is at least one entity that is $F$).
2. **At most one**: $\forall y (Fy \to y = x)$ (There is at most one entity that is $F$; any entity that is $F$ is identical to $x$).
3. **Predication**: $Bx$ (That individual has property $B$).

Joining these into a single first-order formula:
$$\exists x [Fx \land \forall y (Fy \to y = x) \land Bx]$$
Alternatively formulated as:
$$\exists x [ \forall y (Fy \leftrightarrow y = x) \land Bx ]$$
In the actual world, France is a republic and has no monarch. Therefore, the subformula $\exists x Fx$ is false. Because the entire formula is a conjunction governed by an existential quantifier, the falsity of this conjunct renders the entire proposition **strictly false**.

#### Distractor Analysis:
- **A is incorrect**: A universal conditional $\forall x (Fx \to Bx)$ is vacuously *true* when the antecedent $Fx$ is universally false, which contradicts Russell’s fundamental insistence that "The present King of France is bald" is false.
- **C is incorrect**: $\exists x (Fx \land Bx) \land \forall x (Fx \to Bx)$ does not strictly state the uniqueness condition ($\forall y (Fy \to y = x)$); it merely says that some $F$ is $B$ and all $F$s are $B$, allowing there to be multiple Kings of France.
- **D is incorrect**: The expression $(\iota x)Fx = Bx$ is syntactically ill-formed in predicate logic, as it attempts to equate an individual term with a monadic predicate formula.

**Primary Source**: Bertrand Russell and Alfred North Whitehead, *Principia Mathematica* (Cambridge University Press, Vol. 1, 1910, *14).

---

### Question 5: Modal Logic: Relational Semantics and System K
**Format**: Conceptual Multiple-Choice (Advanced)  
**Topic**: Kripke Relational Semantics — Frames, Models, and the Distribution Axiom (K)

In modern modal logic, a **Kripke Frame** is an ordered pair $\mathcal{F} = \langle W, R \rangle$, where $W$ is a non-empty set of possible worlds and $R \subseteq W \times W$ is a binary **accessibility relation** on $W$. A **Kripke Model** is a triple $\mathcal{M} = \langle W, R, V \rangle$, where $V$ is a valuation function assigning truth-values to propositional variables at each world.
The minimal normal modal logic system is **System K** (named after Saul Kripke). Which of the following defines the characteristic axiom schema of System K, and what is its semantic validity status across Kripke frames?

A. Axiom Schema: $\Box p \to p$; it is valid only on frames where the accessibility relation $R$ is reflexive.  
B. Axiom Schema: $\Box (p \to q) \to (\Box p \to \Box q)$; it is valid on **all** Kripke frames whatsoever, without placing any restriction on the accessibility relation $R$.  
C. Axiom Schema: $\Box p \to \Diamond p$; it is valid only on frames where $R$ is serial.  
D. Axiom Schema: $\Diamond p \to \Box \Diamond p$; it is valid only on frames where $R$ is an equivalence relation.

**Correct Answer**: **B**

#### Philosophical Grounding & Demonstration:
1. **The Minimal System K**:
   System K is the base system of all normal modal logics. It consists of:
   - All tautologies of classical propositional calculus.
   - The **Distribution Axiom Schema (K)**:
     $$\Box (p \to q) \to (\Box p \to \Box q)$$
     (In epistemic logic, this asserts that if an agent knows that $p \to q$, then if they know $p$, they know $q$—the closure of knowledge under deduction).
   - Rules of Inference: Modus Ponens ($p, p \to q \vdash q$) and the **Rule of Necessitation** ($\vdash p \implies \ \vdash \Box p$).

2. **Semantic Universality of Axiom K**:
   Let $\mathcal{M} = \langle W, R, V \rangle$ be *any* arbitrary Kripke model, with no restrictions placed on $R$ (it can be empty, irreflexive, asymmetric, etc.).
   Suppose at an arbitrary world $w \in W$, $w \Vdash \Box (p \to q)$ and $w \Vdash \Box p$.
   - $w \Vdash \Box (p \to q)$ means: for every world $u \in W$ such that $wRu$, $u \Vdash p \to q$.
   - $w \Vdash \Box p$ means: for every world $u \in W$ such that $wRu$, $u \Vdash p$.
   - By classical modus ponens at world $u$, since $u \Vdash p \to q$ and $u \Vdash p$, it must be that $u \Vdash q$.
   - Since this holds for *every* world $u$ accessible from $w$ ($wRu$), by definition of the necessity operator, $w \Vdash \Box q$.
   Hence, the conditional $\Box (p \to q) \to (\Box p \to \Box q)$ is true at every world in every model. Axiom K is therefore **universally valid** on the entire class of all Kripke frames.

#### Distractor Analysis:
- **A is incorrect**: $\Box p \to p$ is **Axiom T** (the reflexivity axiom), which characterizes System T, not the minimal System K.
- **C is incorrect**: $\Box p \to \Diamond p$ is **Axiom D** (the seriality axiom: $\forall w \exists u (wRu)$), which characterizes Deontic Logic (System D).
- **D is incorrect**: $\Diamond p \to \Box \Diamond p$ is **Axiom 5** (the Euclidean axiom), which characterizes System S5.

**Primary Source**: Saul Kripke, "Semantical Analysis of Modal Logic I: Normal Propositional Calculi", *Zeitschrift für mathematische Logik und Grundlagen der Mathematik*, 9 (1963), pp. 67–96; Brian F. Chellas, *Modal Logic: An Introduction* (Cambridge University Press, 1980).

---

### Question 6: Modal Logic: Frame Correspondence and Modal Systems (T, S4, S5)
**Format**: Comparative / Doctrinal Matching (Advanced)  
**Topic**: Modal Axioms and their Corresponding Frame Conditions

In modal correspondence theory, specific modal axiom schemas correspond to specific mathematical properties of the accessibility relation $R$ in the frame $\mathcal{F} = \langle W, R \rangle$. Match the **Modal Axiom Schemas** in **List-I** with their **Defining Frame Properties and Modal Systems** in **List-II**:

| List-I (Modal Axiom Schema) | List-II (Frame Property & Characteristic System) |
| :--- | :--- |
| **p. $\Box p \to p$ (Axiom T)** | **1. Transitivity ($\forall u, v, w ((uRv \land vRw) \to uRw)$); System S4** |
| **q. $\Box p \to \Box \Box p$ (Axiom 4)** | **2. Reflexivity ($\forall w (wRw)$); System T** |
| **r. $p \to \Box \Diamond p$ (Axiom B)** | **3. Euclidean ($\forall u, v, w ((uRv \land uRw) \to vRw)$) / Equivalence; System S5** |
| **s. $\Diamond p \to \Box \Diamond p$ (Axiom 5)** | **4. Symmetry ($\forall u, v (uRv \to vRu)$); System B (Brouwersche)** |

Choose the correct matching code:

A. p-2, q-1, r-4, s-3  
B. p-1, q-2, r-3, s-4  
C. p-2, q-4, r-1, s-3  
D. p-3, q-1, r-4, s-2  

**Correct Answer**: **A**

#### Philosophical Grounding & Demonstration:
- **p matches 2 (Axiom T: $\Box p \to p$)**:
  Known as the **Axiom of Necessity** (or Truth Axiom). In epistemic logic, it expresses the veridicality of knowledge: if an agent knows that $p$, then $p$ is true ($K_i p \to p$).
  **Frame Condition**: **Reflexivity** ($\forall w \in W, wRw$). If every world can see itself, then if $p$ is true in all accessible worlds, $p$ must be true in the current world.
- **q matches 1 (Axiom 4: $\Box p \to \Box \Box p$)**:
  Known as the **Axiom of Iteration**. In epistemic logic, it represents **Positive Introspection** (the "KK thesis": if you know that $p$, you know that you know that $p$).
  **Frame Condition**: **Transitivity** ($\forall u, v, w \in W$, if $uRv$ and $vRw$, then $uRw$). Adding Axiom 4 to System T yields **System S4**.
- **r matches 4 (Axiom B: $p \to \Box \Diamond p$)**:
  Named after L.E.J. Brouwer. It asserts that if $p$ is actual, then it is necessary that $p$ is possible.
  **Frame Condition**: **Symmetry** ($\forall u, v \in W$, if $uRv$, then $vRu$). Adding Axiom B to System T yields **System B**.
- **s matches 3 (Axiom 5: $\Diamond p \to \Box \Diamond p$)**:
  In epistemic logic, it represents **Negative Introspection** (if you do not know that $p$, you know that you do not know that $p$: $\neg K p \to K \neg K p$).
  **Frame Condition**: **Euclidean** ($\forall u, v, w$, if $uRv$ and $uRw$, then $vRw$). When combined with reflexivity, an accessibility relation that is transitive and Euclidean is an **equivalence relation** (reflexive, symmetric, transitive). Adding Axiom 5 (or Axioms 4 and B) to System T yields the celebrated **System S5**, where all possible worlds are accessible to one another, collapsing strings of modal operators (e.g., $\Box \Diamond \Box p \equiv \Diamond \Box p \equiv \Box p$).

Thus, the exact correspondence is **p-2, q-1, r-4, s-3**.

#### Distractor Analysis:
- Options B, C, and D misalign the axioms with their geometric accessibility relations:
  - In B, Axiom T is conflated with transitivity, and Axiom 4 with reflexivity.
  - In C, Axiom 4 is matched to symmetry, which belongs to Axiom B.
  - In D, Axiom T is matched to Euclidean relations.

**Primary Source**: Brian F. Chellas, *Modal Logic: An Introduction* (Cambridge University Press, 1980, ch. 3 & 4); G.E. Hughes and M.J. Cresswell, *A New Introduction to Modal Logic* (Routledge, 1996).

---

### Question 7: Modal Predicate Logic: The Barcan Formula and Possibilism vs. Actualism
**Format**: Conceptual Multiple-Choice (Advanced)  
**Topic**: Ruth Barcan Marcus — The Barcan Formula (BF) and Converse Barcan Formula (CBF)

In Quantified Modal Logic, the relation between quantifiers and modal operators was famously formalized by Ruth Barcan Marcus (1946). Consider the **Barcan Formula (BF)** and its converse, the **Converse Barcan Formula (CBF)**:
$$\text{BF: } \forall x \Box Fx \to \Box \forall x Fx$$
$$\text{CBF: } \Box \forall x Fx \to \forall x \Box Fx$$
What are the precise ontological commitments of the Barcan Formula regarding the domains of possible worlds, and why do **Actualists** reject BF in varying-domain semantics?

A. BF implies that all possible worlds have decreasing domains; Actualists accept BF because it proves that God exists necessarily.  
B. BF semantically corresponds to the condition that the domain of individuals cannot expand from the actual world to accessible worlds (the anti-shrinkage condition: if $wRu$, then $D(u) \subseteq D(w)$); Actualists reject BF because it entails that whatever exists in any possible world already exists in the actual world, implying **Possibilism** (the doctrine that merely possible entities, such as a possible brother of mine, actually exist).  
C. BF asserts that existence is a first-order predicate; Actualists reject it because Kant proved that existence is not a real predicate.  
D. BF is a theorem of propositional logic and has no bearing on domains of discourse or ontology.

**Correct Answer**: **B**

#### Philosophical Grounding & Demonstration:
1. **Semantics of the Barcan Formula**:
   Consider what BF asserts:
   $$\forall x \Box Fx \to \Box \forall x Fx$$
   "If everything in the domain is necessarily $F$, then it is necessary that everything is $F$."
   In varying-domain Kripke semantics, each possible world $w$ has its own domain of existing entities, $D(w)$.
   - Suppose world $w$ has domain $D(w) = \{a, b\}$. Suppose both $a$ and $b$ are $F$ in all worlds accessible from $w$. Then the antecedent $\forall x \Box Fx$ is true at $w$.
   - Now consider an accessible world $u$ ($wRu$) where an *additional* entity $c$ exists that does not exist in $w$ (i.e., $D(w) \subset D(u)$). Suppose $c$ is *not* $F$ in world $u$.
   - Then at world $u$, it is *not* the case that everything is $F$ (since $c$ is not $F$).
   - Consequently, $\Box \forall x Fx$ is **false** at world $w$!
   This shows that BF fails in any frame where the domain of an accessible world can *expand* beyond the base world. For BF to be valid, every accessible world's domain must be a subset of the actual world's domain: if $wRu$, then $D(u) \subseteq D(w)$.

2. **The Actualist vs. Possibilist Conflict**:
   If both BF and CBF hold (as in constant domain semantics), then for all worlds $w, u$, $D(w) = D(u)$: the set of existing entities is fixed and identical across all possible worlds.
   - **Possibilism**: Embraces BF, accepting that the domain of the actual world includes all entities that could ever exist in any possible world (possibilia).
   - **Actualism**: Rejects BF. Actualists (like Alvin Plantinga, Saul Kripke, and Robert Stalnaker) insist that to be is to be actual. I might have had a brother, but there is no actual entity that *is* my possible brother. Since there could have existed things that do not actually exist, domains vary and expand across worlds; therefore, BF is invalid.

#### Distractor Analysis:
- **A is incorrect**: BF corresponds to non-expanding domains (nested domains where $D(u) \subseteq D(w)$), not merely decreasing domains, and actualists *reject* BF rather than accepting it.
- **C is incorrect**: BF is formulated in standard modal predicate logic without requiring an existence predicate, and the Kantian slogan does not address the model-theoretic conditions of varying domains.
- **D is incorrect**: BF contains quantifiers and is a central thesis of Quantified Predicate Modal Logic, not propositional logic.

**Primary Source**: Ruth C. Barcan (Marcus), "A Functional Calculus of First Order Based on Strict Implication", *Journal of Symbolic Logic*, 11 (1946), pp. 1–16; Saul Kripke, "Semantical Considerations on Modal Logic", *Acta Philosophica Fennica*, 16 (1963), pp. 83–94.

---

### Question 8: Formal Fallacies in Syllogistic and Propositional Logic
**Format**: Conceptual Multiple-Choice (Advanced)  
**Topic**: Classical Formal Fallacies — Undistributed Middle, Illicit Major/Minor, Affirming the Consequent

Consider the following two categorical syllogisms:
$$\text{Syllogism 1:}$$
$$\text{All philosophers are seekers of wisdom.}$$
$$\text{All scientists are seekers of wisdom.}$$
$$\therefore \text{All scientists are philosophers.}$$

$$\text{Syllogism 2:}$$
$$\text{All mammals are warm-blooded creatures.}$$
$$\text{No reptiles are mammals.}$$
$$\therefore \text{No reptiles are warm-blooded creatures.}$$

Which formal fallacies are committed by Syllogism 1 and Syllogism 2, respectively?

A. Syllogism 1 commits the **Fallacy of the Undistributed Middle**; Syllogism 2 commits the **Fallacy of Illicit Major**.  
B. Syllogism 1 commits the **Fallacy of Illicit Minor**; Syllogism 2 commits the **Fallacy of Exclusive Premises**.  
C. Syllogism 1 commits the **Fallacy of Affirming the Consequent**; Syllogism 2 commits the **Fallacy of the Undistributed Middle**.  
D. Syllogism 1 commits the **Fallacy of Four Terms**; Syllogism 2 commits the **Fallacy of Drawing an Affirmative Conclusion from a Negative Premise**.

**Correct Answer**: **A**

#### Philosophical Grounding & Demonstration:
1. **Analysis of Syllogism 1**:
   - Mood and Figure: Premise 1 is an **A** proposition: "All $P$ are $M$" (Subject distributed, Predicate undistributed). Premise 2 is an **A** proposition: "All $S$ are $M$" (Subject distributed, Predicate undistributed).
   - The middle term $M$ is "seekers of wisdom." In both premises, $M$ appears in the predicate position of universal affirmative (A) propositions. In an A proposition, the predicate term is **undistributed**.
   - Therefore, the middle term is not distributed at least once in either premise.
   - This violates Rule 2 of categorical syllogisms, committing the formal **Fallacy of the Undistributed Middle** (*non distributio medii*). Both classes ($S$ and $P$) could fall into disjoint sub-regions of the middle term $M$ without overlapping each other.

2. **Analysis of Syllogism 2**:
   - Premise 1: "All mammals ($M$) are warm-blooded creatures ($P$)." (A proposition: $M$ distributed, $P$ undistributed).
   - Premise 2: "No reptiles ($S$) are mammals ($M$)." (E proposition: both $S$ and $M$ distributed).
   - Conclusion: "No reptiles ($S$) are warm-blooded creatures ($P$)." (E proposition: both $S$ and $P$ distributed).
   - The major term is $P$ ("warm-blooded creatures").
   - Notice that $P$ is **undistributed** in the major premise (as the predicate of an A proposition), but it becomes **distributed** in the conclusion (as the predicate of an E proposition).
   - This violates Rule 3 of categorical syllogisms: no term can be distributed in the conclusion that was not distributed in the premises.
   - Distributing the major term illicitly commits the **Fallacy of Illicit Major** (*illicitus processus termini majoris*). (Indeed, reptiles are not mammals, but warm-blooded creatures include birds, so reptiles not being mammals does not exclude them from being warm-blooded by logic alone).

#### Distractor Analysis:
- **B is incorrect**: Syllogism 1 does not involve an illicit minor (the minor term $S$ is distributed in the premise); Syllogism 2 does not have exclusive premises (only one premise is negative).
- **C is incorrect**: Affirming the Consequent is a fallacy of propositional logic (conditional statements), whereas Syllogisms 1 and 2 are categorical syllogisms; moreover, Syllogism 2 does not commit undistributed middle (the middle term "mammals" is distributed in both premises).
- **D is incorrect**: Syllogism 1 has exactly three terms, not four; Syllogism 2 draws a negative conclusion, not an affirmative one.

**Primary Source**: Irving M. Copi, Carl Cohen, *Introduction to Logic* (ch. 6: Categorical Syllogisms); Aristotle, *Prior Analytics*.

---

### Question 9: Informal Fallacies: Fallacy of Composition vs. Fallacy of Division
**Format**: Conceptual Multiple-Choice (Advanced)  
**Topic**: Informal Fallacies — Collective vs. Distributive Predication

Consider the following two arguments:
- **Argument 1**: "Every constituent atom in this brain is completely devoid of conscious experience; therefore, the brain as a whole cannot possess conscious experience."
- **Argument 2**: "The Indian Parliament is a deliberative democratic assembly of the nation; therefore, each individual member of Parliament is a deliberative democratic assembly of the nation."

What is the precise logical mechanism of these fallacies, and how does the distinction between **distributive** and **collective** properties explain why they are fallacious?

A. Argument 1 commits the **Fallacy of Composition**, and Argument 2 commits the **Fallacy of Division**; they are fallacious because they confuse a **distributive property** (a property belonging to individual members of a collection or parts of a whole) with a **collective property** (a property possessed by the whole or class as an emergent structural unity).  
B. Argument 1 is the **Fallacy of Accident**, and Argument 2 is the **Converse Accident**; they confuse an accidental property with an essential property.  
C. Argument 1 commits the **Fallacy of Equivocation**, and Argument 2 commits the **Fallacy of Amphiboly**; they arise from syntactic ambiguity in the definition of "assembly."  
D. Both arguments are logically valid demonstrations of mereological essentialism.

**Correct Answer**: **A**

#### Philosophical Grounding & Demonstration:
1. **Fallacy of Composition**:
   This fallacy occurs when one infers that a whole must have a certain property simply because every part of that whole possesses that property:
   - Parts $\to$ Whole.
   - In Argument 1, the property "is devoid of conscious experience" is predicated *distributively* of every individual atom. From this, the arguer fallaciously infers that the organized whole (the functioning brain) must *collectively* have the property of being devoid of consciousness. This ignores the possibility of emergent structural, organizational, or systemic properties.

2. **Fallacy of Division**:
   This is the exact reverse fallacy: inferring that an individual part must possess a property simply because the whole possesses that property:
   - Whole $\to$ Parts.
   - In Argument 2, "is a deliberative democratic assembly" is a *collective property* of the entire Parliament as an institutional body. Predicating it of a single individual member is a blatant Fallacy of Division.

3. **Distributive vs. Collective Predication**:
   - A property is predicated **distributively** when it applies to each and every member individually (e.g., "Elephants are mammals" means *every individual elephant* is a mammal).
   - A property is predicated **collectively** when it applies to the group as a whole, but not to its individual members (e.g., "Elephants are an endangered species" does *not* mean that Jumbo the elephant is an endangered species).
   Confusing the distributive predication of parts with the collective predication of wholes generates the Fallacies of Composition and Division.

#### Distractor Analysis:
- **B is incorrect**: The Fallacy of Accident (*dicto simpliciter*) consists in applying a general rule to a specific case whose accidental circumstances make the rule inapplicable; Converse Accident is hasty generalization. Neither addresses part-whole mereology.
- **C is incorrect**: Equivocation is semantic ambiguity of a word; Amphiboly is grammatical/syntactic structural ambiguity. Neither is the part-whole confusion operative here.
- **D is incorrect**: Mereological essentialism is the metaphysical thesis that an object cannot survive the loss of any of its parts (Chisholm); it does not validate inferences between distributive and collective properties.

**Primary Source**: Irving M. Copi, Carl Cohen, *Introduction to Logic* (ch. 4: Informal Fallacies); C.L. Hamblin, *Fallacies* (Methuen, 1970).

---

### Question 10: Informal Fallacies of Relevance and Presumption
**Format**: Multi-Statement Evaluation (MSQ / GATE style)  
**Topic**: Petitio Principii, Ignoratio Elenchi, Complex Question, and Ad Hominem

Evaluate the truth-value of the following statements concerning informal fallacies of relevance and presumption:

I. **Petitio Principii** (Begging the Question) is formally valid because whenever $p \vdash p$, the conclusion follows necessarily from the premises; its defect is epistemic rather than formal, because it fails to provide independent evidence for the conclusion.  
II. The **Fallacy of Complex Question** (plurium interrogationum) operates by presupposing the truth of an unproven assertion buried within the question itself (e.g., "Have you stopped cheating on exams?").  
III. **Argumentum ad Hominem (Tu Quoque)** refutes the logical truth of a proposition by pointing out that the proponent’s personal conduct is hypocritical and inconsistent with their stated proposition.  
IV. **Ignoratio Elenchi** (Irrelevant Conclusion / Red Herring) occurs when an argument purporting to establish a particular conclusion is directed instead to proving a completely different conclusion.

Which of the combinations is strictly correct?

A. I, II, and IV only  
B. II, III, and IV only  
C. I and III only  
D. I, II, III, and IV

**Correct Answer**: **A**

#### Philosophical Grounding & Demonstration:
- **Statement I is TRUE**: In formal deductive logic, an argument of the form $p \vdash p$ is impeccably **valid** (if the premise is true, the conclusion cannot be false). Yet *Petitio Principii* is a profound **informal fallacy** because the purpose of argumentation is epistemological: to establish the truth of a contested proposition on the basis of already accepted premises. If the conclusion is already presupposed among the premises, the argument fails to produce epistemic justification. Thus, begging the question is a pragmatic/epistemic defect, not a formal invalidity.
- **Statement II is TRUE**: A *Complex Question* achieves rhetorical persuasion by embedding a presupposition into an interrogative utterance such that any direct affirmative or negative answer ("yes" or "no") forces the respondent to concede the buried unproven claim.
- **Statement III is FALSE**: *Tu Quoque* ("you too") is an **informal fallacy of relevance**. The fact that a doctor who smokes warns you that "Smoking causes lung cancer" shows that the doctor is a hypocrite; it does *not* refute the objective truth of the proposition that smoking causes lung cancer! A person's hypocrisy or personal inconsistency has zero bearing on the logical validity or truth of their empirical claim. To claim that it *refutes* the truth of the proposition is precisely what makes *Tu Quoque* a fallacy.
- **Statement IV is TRUE**: *Ignoratio Elenchi* (literally "ignorance of the refutation"), first identified by Aristotle in *Sophistical Refutations*, occurs when premises establish a conclusion other than the one that was supposed to be established.

Therefore, Statements I, II, and IV are correct, while Statement III is false.

#### Distractor Analysis:
- Options B and D are incorrect because they include Statement III, which fallaciously treats *Tu Quoque* as a legitimate refutation.
- Option C is incorrect because Statement II and IV are textbook correct definitions.

**Primary Source**: Aristotle, *De Sophisticis Elenchis* (Sophistical Refutations); Douglas Walton, *Informal Logic: A Pragmatic Approach* (Cambridge University Press, 2nd ed., 2008).

---

### Question 11: The Epistemic and Cosmological Quantifier Fallacy
**Format**: Conceptual Multiple-Choice (Advanced)  
**Topic**: Fallacy of Modal / Quantifier Reversal in the History of Philosophy

In the history of philosophy, many famous arguments have been criticized for committing a subtle logical fallacy involving the illicit reversal of operators or quantifiers. Consider the following inference:
$$\text{"Every event has a cause; therefore, there is a single First Cause that caused every event."}$$
Which of the following correctly analyzes the exact logical structure of this fallacy and identifies its parallel in modal logic?

A. It commits the **Fallacy of Undistributed Middle** in categorical logic; its modal parallel is Axiom T ($\Box p \to p$).  
B. It commits the **Quantifier Shift Fallacy**, moving illegitimately from $\forall x \exists y (Ex \to Cyx)$ to $\exists y \forall x (Ex \to Cyx)$; its exact parallel in modal logic is the **Modal Fallacy** of confusing the necessity of the consequence ($\Box (p \to q)$) with the necessity of the consequent ($p \to \Box q$).  
C. It commits the **Fallacy of Affirming the Consequent**; its modal parallel is the Rule of Necessitation.  
D. It commits the **Fallacy of Equivocation** on the word "cause"; its modal parallel is the Barcan Formula.

**Correct Answer**: **B**

#### Philosophical Grounding & Demonstration:
1. **The Quantifier Shift Fallacy in the Cosmological Argument**:
   - The premise asserts: "For every event $x$, there exists some cause $y$ such that $y$ causes $x$" ($\forall x \exists y C(y, x)$). Here, the cause $y$ may be completely different for each event $x$ (Event 1 was caused by Cause 1, Event 2 by Cause 2, ad infinitum).
   - The conclusion asserts: "There exists some entity $y$ such that for every event $x$, $y$ caused $x$" ($\exists y \forall x C(y, x)$).
   - This inference shifts the existential quantifier from inside the scope of the universal quantifier to wide scope outside it ($\forall \exists \vdash \exists \forall$). This is formally invalid: from "Every person has a biological mother", one cannot infer "There is one woman who is the biological mother of every person."

2. **The Parallel Modal Fallacy (Necessity of the Consequence vs. Consequent)**:
   This quantifier shift is structurally parallel to the notorious **Modal Fallacy** made throughout scholastic and modern metaphysics:
   - A valid logical entailment asserts that the conditional is necessarily true:
     $$\Box (p \to q)$$
     (The *necessitas consequentiae*—the necessity of the consequence).
   - The fallacious inference illicitly shifts the modal necessity operator inside, attaching it directly to the consequent:
     $$p \to \Box q$$
     (The *necessitas consequentis*—the necessity of the consequent).
   - For example: "Necessarily, if Socrates is sitting, he is sitting" ($\Box (S \to S)$) is a trivial tautology. The modal fallacy infers: "If Socrates is sitting, then he is *necessarily* sitting" ($S \to \Box S$), falsely turning a contingent empirical fact into a metaphysically necessary fatalistic truth.

#### Distractor Analysis:
- **A is incorrect**: The argument is in relational predicate logic, not syllogistic categorical logic, and Axiom T ($\Box p \to p$) is a valid modal axiom, not a fallacy.
- **C is incorrect**: Affirming the Consequent is an error in conditional propositional logic ($p \to q, q \vdash p$), which does not capture the $\forall \exists \to \exists \forall$ scope shift.
- **D is incorrect**: The fallacy is structural and scope-based, not a lexical equivocation on the word "cause."

**Primary Source**: Anthony Kenny, *The Five Ways: St. Thomas Aquinas' Proofs of God's Existence* (Routledge, 1969); Brian F. Chellas, *Modal Logic* (1980).

---

### Question 12: Doctrinal Matching: Logical Systems and Their Characteristic Theorems
**Format**: Comparative / Doctrinal Matching (Advanced)  
**Topic**: Propositional, Predicate, and Modal Logic Properties

Match the **Formal Logic Concepts / Theorems** in **List-I** with their **Defining Formula or Principle** in **List-II**:

| List-I (Formal Concept / Law) | List-II (Defining Formula or Formalization) |
| :--- | :--- |
| **p. Law of Material Equivalence** | **1. $(p \leftrightarrow q) \equiv ((p \to q) \land (q \to p)) \equiv ((p \land q) \lor (\neg p \land \neg q))$** |
| **q. Converse Barcan Formula (CBF)** | **2. $\Box \forall x Fx \to \forall x \Box Fx$** |
| **r. De Morgan's Quantifier Duality** | **3. $\neg \forall x Fx \equiv \exists x \neg Fx \quad \text{and} \quad \neg \exists x Fx \equiv \forall x \neg Fx$** |
| **s. Deontic Duality** | **4. $O p \equiv \neg P \neg p$ (Obligatory is equivalent to Not Permissible Not)** |

Choose the correct matching code:

A. p-1, q-2, r-3, s-4  
B. p-2, q-1, r-4, s-3  
C. p-1, q-3, r-2, s-4  
D. p-4, q-2, r-1, s-3  

**Correct Answer**: **A**

#### Philosophical Grounding & Demonstration:
- **p matches 1 (Material Equivalence)**: In propositional logic, two statements are materially equivalent when they have the same truth-value. The biconditional $p \leftrightarrow q$ is logically equivalent to the conjunction of two conditionals $(p \to q) \land (q \to p)$, and by Material Implication and Distribution, to $(p \land q) \lor (\neg p \land \neg q)$.
- **q matches 2 (Converse Barcan Formula)**: In modal predicate logic, the Converse Barcan Formula (CBF) is $\Box \forall x Fx \to \forall x \Box Fx$. It semantically corresponds to the condition that domains cannot shrink across accessible worlds (if $wRu$, then $D(w) \subseteq D(u)$).
- **r matches 3 (De Morgan's Laws for Quantifiers)**: In first-order predicate logic, universal and existential quantifiers are duals under negation: "Not all are $F$" is equivalent to "There exists something that is not $F$", and "There does not exist an $F$" is equivalent to "All things are non-$F$."
- **s matches 4 (Deontic Duality)**: In Deontic Logic (von Wright, 1951), the obligation operator $O$ and permission operator $P$ are interdefinable duals: an act $p$ is obligatory if and only if it is not permitted to refrain from $p$ ($O p \equiv \neg P \neg p$), mirroring the relationship between $\Box$ and $\Diamond$.

Thus, the exact correspondence is **p-1, q-2, r-3, s-4**.

#### Distractor Analysis:
- Options B, C, and D misalign the formal equivalences with their standard definitions:
  - In B, Material Equivalence is paired with CBF.
  - In C, CBF is matched with Quantifier Duality.
  - In D, Deontic Duality is matched with Material Equivalence.

**Primary Sources**:
- G.H. von Wright, "Deontic Logic", *Mind*, 60 (1951), pp. 1–15.
- Ruth Barcan Marcus, *Modalities: Philosophical Essays* (Oxford University Press, 1993).
- Patrick Suppes, *Introduction to Logic* (1957).
