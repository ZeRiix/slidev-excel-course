<script setup lang="ts">
import { useFrontmatter } from "../composables/useFrontmatter";
import { useSlideAsset } from "../composables/useSlideAsset";

export interface ExcelCoverCell {
	value: string;
	strong?: boolean;
}

export interface ExcelCoverFrontmatter {
	kicker?: string;
	title?: string;
	logo?: string;
	subtitle?: string;
	eyebrow?: string;
	trainer?: string;
	institution?: string;
	footerNote?: string;
}

const metrics = [
	{
		label: "Commercial",
		value: "8 070 €",
	},
	{
		label: "Moyenne",
		value: "4 035 €",
	},
	{
		label: "Lignes",
		value: "2",
	},
];

const cells: ExcelCoverCell[] = [
	{
		value: "Service",
		strong: true,
	},
	{
		value: "Mois",
		strong: true,
	},
	{
		value: "Montant",
		strong: true,
	},
	{
		value: "Statut",
		strong: true,
	},
	{ value: "Commercial" },
	{ value: "Janvier" },
	{ value: "3 200 €" },
	{ value: "Payé" },
	{ value: "Support" },
	{ value: "Février" },
	{ value: "1 450 €" },
	{ value: "À relancer" },
	{ value: "Commercial" },
	{ value: "Mars" },
	{ value: "4 870 €" },
	{ value: "Payé" },
];

const frontmatter = useFrontmatter<ExcelCoverFrontmatter>();
const logoSrc = useSlideAsset(() => frontmatter.value.logo);
const cursorSrc = useSlideAsset(() => "./cursor.png");
</script>

<template>
	<section class="course-slide excel-cover">
		<header class="excel-cover__top">
			<span class="course-kicker">{{ frontmatter.kicker }}</span>

			<span class="excel-cover__level">{{ frontmatter.institution }}</span>
		</header>

		<main class="excel-cover__body">
			<div
				class="excel-cover__sheet"
				aria-hidden="true"
			>
				<div class="excel-cover__logo-box">
					<img
						v-if="logoSrc"
						:src="logoSrc"
					/>

					<span v-else>XLS</span>
				</div>

				<div class="excel-cover__formula">
					<span class="excel-cover__formula-prefix">fx</span>

					<strong>
						<span>=SOMME.SI(</span>

						<span class="excel-cover__formula-range excel-cover__formula-range--criteria">A2:A4</span>

						<span>;"Commercial";</span>

						<span class="excel-cover__formula-range excel-cover__formula-range--sum">C2:C4</span>

						<span>)</span>

						<span class="excel-cover__formula-caret" />
					</strong>
				</div>

				<div class="excel-cover__grid">
					<div class="excel-cover__corner" />

					<span
						v-for="column in ['A', 'B', 'C', 'D']"
						:key="column"
						class="excel-cover__column"
					>
						{{ column }}
					</span>

					<template
						v-for="row in 4"
						:key="row"
					>
						<span class="excel-cover__row">{{ row }}</span>

						<span
							v-for="(cell, cellIndex) in cells.slice((row - 1) * 4, row * 4)"
							:key="`${row}-${cellIndex}-${cell.value}`"
							:class="[
								'excel-cover__cell',
								cell.strong ? 'excel-cover__cell--strong' : '',
							]"
						>
							{{ cell.value }}
						</span>
					</template>

					<div class="excel-cover__range excel-cover__range--criteria" />

					<div class="excel-cover__range excel-cover__range--sum">
						<img
							v-if="cursorSrc"
							:src="cursorSrc"
							class="excel-cover__cursor"
						/>
					</div>
				</div>
			</div>

			<div class="excel-cover__content">
				<div class="excel-cover__title">
					<span class="excel-cover__eyebrow">{{ frontmatter.eyebrow }}</span>

					<h1>{{ frontmatter.title }}</h1>

					<p>{{ frontmatter.subtitle }}</p>
				</div>

				<div class="excel-cover__metrics">
					<div
						v-for="metric in metrics"
						:key="metric.label"
						class="excel-cover__metric"
					>
						<span>{{ metric.label }}</span>

						<strong>{{ metric.value }}</strong>
					</div>
				</div>
			</div>
		</main>

		<footer class="excel-cover__footer">
			<span>{{ frontmatter.trainer }}</span>

			<span>{{ frontmatter.footerNote }}</span>
		</footer>
	</section>
</template>

<style scoped>
.excel-cover {
	position: relative;
	isolation: isolate;
	justify-content: space-between;
	overflow: hidden;
	background: var(--color-inverse);
	color: var(--color-surface);
}

.excel-cover::before {
	content: "";
	position: absolute;
	z-index: -1;
	inset: 0;
	background:
		linear-gradient(90deg, rgba(var(--color-primary-rgb), 0.13) 0 1px, transparent 1px 100%),
		linear-gradient(0deg, rgba(var(--color-primary-rgb), 0.09) 0 1px, transparent 1px 100%);
	background-size: 52px 52px;
}

.excel-cover__top,
.excel-cover__footer {
	display: flex;
	align-items: center;
	justify-content: space-between;
	gap: 24px;
}

.excel-cover__level,
.excel-cover__footer {
	color: var(--color-border);
	font-size: 0.9rem;
}

.excel-cover__body {
	display: grid;
	grid-template-columns: minmax(450px, 0.92fr) minmax(0, 1fr);
	gap: 46px;
	align-items: center;
}

.excel-cover__content {
	display: grid;
	gap: 26px;
	align-content: center;
}

.excel-cover__title {
	max-width: 790px;
}

.excel-cover__eyebrow {
	display: inline-block;
	margin-bottom: 18px;
	color: var(--color-primary);
	font-family: var(--font-mono);
	font-size: 0.82rem;
	font-weight: 800;
	text-transform: uppercase;
}

.excel-cover h1 {
	margin: 0;
	max-width: 620px;
	font-size: 5rem;
	font-weight: 850;
	line-height: 0.96;
	letter-spacing: 0;
}

.excel-cover p {
	margin: 22px 0 0;
	max-width: 610px;
	color: var(--color-border);
	font-size: 1.22rem;
	line-height: 1.32;
}

.excel-cover__sheet {
	display: grid;
	grid-template-columns: 46px minmax(0, 1fr);
	gap: 8px;
	border: 1px solid rgba(var(--color-primary-rgb), 0.62);
	background: rgba(var(--color-surface-rgb), 0.1);
	padding: 14px;
	box-shadow:
		inset 0 0 0 1px rgba(var(--color-surface-rgb), 0.11),
		0 24px 70px rgba(0, 0, 0, 0.34);
}

.excel-cover__logo-box {
	display: grid;
	min-height: 44px;
	place-items: center;
	padding: 6px;
	color: var(--color-surface);
	font-family: var(--font-mono);
	font-size: 0.7rem;
	font-weight: 900;
}

.excel-cover__logo-box img {
	display: block;
	width: 34px;
	height: 34px;
	object-fit: contain;
}

.excel-cover__formula {
	display: flex;
	min-width: 0;
	align-items: center;
	gap: 10px;
	border: 1px solid rgba(var(--color-surface-rgb), 0.32);
	background: rgba(var(--color-surface-rgb), 0.1);
	padding: 11px 16px;
	font-family: var(--font-mono);
	font-size: 0.72rem;
}

.excel-cover__formula-prefix {
	color: var(--color-primary);
	font-weight: 900;
}

.excel-cover__formula strong {
	display: inline-flex;
	overflow: hidden;
	min-width: 0;
	align-items: center;
	color: var(--color-border);
	font-weight: 700;
	text-overflow: ellipsis;
	white-space: nowrap;
}

.excel-cover__formula-range {
	border-radius: 3px;
	padding: 1px 3px;
	font-weight: 850;
}

.excel-cover__formula-range--criteria {
	background: rgba(96, 165, 250, 0.18);
	color: #93c5fd;
}

.excel-cover__formula-range--sum {
	background: rgba(var(--color-primary-rgb), 0.2);
	color: var(--color-primary);
}

.excel-cover__formula-caret {
	display: inline-block;
	width: 2px;
	height: 1.4em;
	margin-left: 2px;
	background: var(--color-primary);
}

.excel-cover__grid {
	--excel-cover-row-header-size: 34px;
	--excel-cover-row-size: 48px;

	position: relative;
	display: grid;
	grid-column: 1 / -1;
	grid-template-columns: var(--excel-cover-row-header-size) repeat(4, minmax(0, 1fr));
	grid-template-rows: var(--excel-cover-row-header-size) repeat(4, var(--excel-cover-row-size));
	border-top: 1px solid rgba(var(--color-surface-rgb), 0.48);
	border-left: 1px solid rgba(var(--color-surface-rgb), 0.48);
	background: rgba(9, 9, 7, 0.25);
}

.excel-cover__range {
	z-index: 2;
	position: absolute;
	pointer-events: none;
}

.excel-cover__range--criteria {
	top: calc(var(--excel-cover-row-header-size) + var(--excel-cover-row-size));
	left: var(--excel-cover-row-header-size);
	width: calc((100% - var(--excel-cover-row-header-size)) / 4);
	height: calc(var(--excel-cover-row-size) * 3);
	border: 2px solid #60a5fa;
	background: rgba(96, 165, 250, 0.13);
}

.excel-cover__range--sum {
	top: calc(var(--excel-cover-row-header-size) + var(--excel-cover-row-size));
	left: calc(var(--excel-cover-row-header-size) + ((100% - var(--excel-cover-row-header-size)) / 4 * 2));
	width: calc((100% - var(--excel-cover-row-header-size)) / 4);
	height: calc(var(--excel-cover-row-size) * 3);
	border: 2px solid var(--color-primary);
	background: rgba(var(--color-primary-rgb), 0.14);
}

.excel-cover__cursor {
	position: absolute;
	right: -31px;
	bottom: -36px;
	z-index: 2;
	width: 34px;
	height: 34px;
	object-fit: contain;
	filter: drop-shadow(0 4px 5px rgba(0, 0, 0, 0.45));
	transform: rotate(-4deg);
}

.excel-cover__range--sum::after {
	content: "";
	position: absolute;
	right: -5px;
	bottom: -5px;
	width: 9px;
	height: 9px;
	border: 1px solid var(--color-inverse);
	background: var(--color-primary);
}

.excel-cover__corner,
.excel-cover__column,
.excel-cover__row {
	z-index: 1;
	min-height: 34px;
	border-right: 1px solid rgba(var(--color-surface-rgb), 0.48);
	border-bottom: 1px solid rgba(var(--color-surface-rgb), 0.48);
	background: rgba(var(--color-primary-rgb), 0.14);
	color: var(--color-border);
	font-family: var(--font-mono);
	font-size: 0.68rem;
	font-weight: 800;
	line-height: 34px;
	text-align: center;
}

.excel-cover__cell {
	z-index: 1;
	min-height: 48px;
	border-right: 1px solid rgba(var(--color-surface-rgb), 0.48);
	border-bottom: 1px solid rgba(var(--color-surface-rgb), 0.48);
	padding: 9px 10px;
	color: var(--color-border);
	font-family: var(--font-mono);
	font-size: 0.67rem;
	line-height: 1.15;
}

.excel-cover__cell--strong {
	color: var(--color-surface);
	font-weight: 800;
}

.excel-cover__metrics {
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	gap: 10px;
	max-width: 520px;
}

.excel-cover__metric {
	border: 1px solid rgba(var(--color-primary-rgb), 0.34);
	background: rgba(var(--color-surface-rgb), 0.08);
	padding: 10px 12px;
}

.excel-cover__metric span {
	display: block;
	color: var(--color-border);
	font-size: 0.62rem;
	font-weight: 750;
	text-transform: uppercase;
}

.excel-cover__metric strong {
	display: block;
	margin-top: 5px;
	color: var(--color-primary);
	font-family: var(--font-mono);
	font-size: 0.86rem;
}

.excel-cover__footer {
	border-top: 1px solid rgba(var(--color-surface-rgb), 0.18);
	padding-top: 22px;
}
</style>
