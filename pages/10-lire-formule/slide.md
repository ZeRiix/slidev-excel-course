---
layout: TheoryContentLayout
kicker: Formules
title: Lire une formule
slide_info: false
---

<div class="formula-reading">
  <div class="formula-reading__formula" aria-label="Formule SOMME.SI découpée">
    <span class="formula-reading__chunk formula-reading__chunk--start">=</span><span class="formula-reading__chunk formula-reading__chunk--function">SOMME.SI</span><span>(</span><span class="formula-reading__chunk formula-reading__chunk--criteria-range">A2:A20</span><span>;</span><span class="formula-reading__chunk formula-reading__chunk--criteria">"Commercial"</span><span>;</span><span class="formula-reading__chunk formula-reading__chunk--sum-range">C2:C20</span><span>)</span>
  </div>

  <svg class="formula-reading__lines" viewBox="0 0 1000 390" preserveAspectRatio="none" aria-hidden="true">
    <line class="formula-reading__line formula-reading__line--start" x1="200" y1="78" x2="222" y2="172" />
    <line class="formula-reading__line formula-reading__line--function" x1="420" y1="94" x2="300" y2="172" />
    <line class="formula-reading__line formula-reading__line--criteria-range" x1="760" y1="78" x2="455" y2="172" />
    <line class="formula-reading__line formula-reading__line--criteria" x1="430" y1="312" x2="580" y2="207" />
    <line class="formula-reading__line formula-reading__line--sum-range" x1="690" y1="312" x2="730" y2="207" />
  </svg>

  <div class="formula-reading__bubble formula-reading__bubble--start">
    <strong>Point de départ</strong>
    <span>`=` indique à Excel qu'on écrit une formule.</span>
  </div>

  <div class="formula-reading__bubble formula-reading__bubble--function">
    <strong>Fonction</strong>
    <span>`SOMME.SI` additionne seulement les lignes qui respectent une condition.</span>
  </div>

  <div class="formula-reading__bubble formula-reading__bubble--criteria-range">
    <strong>Où tester ?</strong>
    <span>`A2:A20` contient les services à vérifier.</span>
  </div>

  <div class="formula-reading__bubble formula-reading__bubble--criteria">
    <strong>Quel critère ?</strong>
    <span>`"Commercial"` est la valeur recherchée.</span>
  </div>

  <div class="formula-reading__bubble formula-reading__bubble--sum-range">
    <strong>Quoi additionner ?</strong>
    <span>`C2:C20` contient les montants à additionner.</span>
  </div>
</div>

<style>
.formula-reading {
  position: relative;
  min-height: 390px;
  margin-top: 24px;
}

.formula-reading__formula {
  position: absolute;
  z-index: 2;
  top: 150px;
  left: 50%;
  width: min(100%, 880px);
  transform: translateX(-50%);
  border: 1px solid rgba(var(--color-primary-rgb), 0.28);
  background: var(--color-inverse);
  padding: 24px 28px;
  color: var(--color-surface);
  font-family: var(--font-mono);
  font-size: 1.28rem;
  font-weight: 750;
  line-height: 1.4;
  text-align: center;
  white-space: nowrap;
}

.formula-reading__chunk {
  border-radius: 4px;
  padding: 2px 5px;
}

.formula-reading__chunk--start {
  background: rgba(244, 114, 182, 0.16);
  color: #f9a8d4;
}

.formula-reading__chunk--function {
  background: rgba(var(--color-primary-rgb), 0.18);
  color: var(--color-primary);
}

.formula-reading__chunk--criteria-range {
  background: rgba(96, 165, 250, 0.18);
  color: #60a5fa;
}

.formula-reading__chunk--criteria {
  background: rgba(245, 158, 11, 0.18);
  color: #f59e0b;
}

.formula-reading__chunk--sum-range {
  background: rgba(34, 197, 94, 0.18);
  color: #22c55e;
}

.formula-reading__bubble {
  position: absolute;
  z-index: 3;
  max-width: 230px;
  border: 1px solid var(--color-border);
  background: var(--color-surface);
  padding: 13px 14px;
  color: var(--color-text);
  font-size: 0.78rem;
  line-height: 1.28;
}

.formula-reading__bubble strong {
  display: block;
  margin-bottom: 5px;
  background: none;
  box-shadow: none;
  color: var(--color-inverse);
  font-size: 0.72rem;
  line-height: 1.1;
  padding: 0;
  text-transform: uppercase;
}

.formula-reading__bubble span {
  display: block;
}

.formula-reading__lines {
  position: absolute;
  z-index: 4;
  inset: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.formula-reading__line {
  stroke-linecap: round;
  stroke-width: 3;
  opacity: 0.68;
}

.formula-reading__line--start {
  stroke: #db2777;
}

.formula-reading__line--function {
  stroke: rgb(var(--color-primary-rgb));
}

.formula-reading__line--criteria-range {
  stroke: #2563eb;
}

.formula-reading__line--criteria {
  stroke: #b45309;
}

.formula-reading__line--sum-range {
  stroke: #16a34a;
}

.formula-reading__bubble--start {
  top: 0;
  left: 0;
  color: #db2777;
}

.formula-reading__bubble--function {
  top: 0;
  left: 270px;
  color: var(--color-primary);
}

.formula-reading__bubble--criteria-range {
  top: 0;
  right: 0;
  color: #2563eb;
}

.formula-reading__bubble--criteria {
  bottom: 0;
  left: 165px;
  color: #b45309;
}

.formula-reading__bubble--sum-range {
  right: 105px;
  bottom: 0;
  color: #16a34a;
}
</style>

<!--
Tip : lorsqu'une formule contient plusieurs fonctions imbriquées, commencez par comprendre les fonctions les plus internes puis remontez vers l'extérieur.
-->
