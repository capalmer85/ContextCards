# CMS AN / Paper Writing Context

Concise, LLM-ready context for writing CMS Analysis Notes and papers. Built from the sources listed in sources.md.

## Detector Description Boilerplate (for use in CMS papers)

Source: "Inputs for the description of the detector and physics object reconstruction in CMS physics papers" (PubDetector twiki). This page provides standard, committee-vetted LaTeX text to copy/paste into the detector-description and object-reconstruction sections of a paper. Only the most broadly-applicable paragraphs are reproduced below verbatim; the source page has many more situational variants (Run 1 vs. Run 2 wording, specific subdetector performance numbers, b/c/tau/W/Z/top tagging, forward detectors, etc.) — consult it directly when a specific variant is needed.

**Section title:** Use "The CMS detector" as the title for the detector section (section titles normally don't start with "The", but an exception is made when the next word is an acronym like "CMS").

**Structure:** CMS papers should begin with an introductory section on physics motivation, followed by a section describing the detector and (possibly) trigger, and possibly a separate section on offline event reconstruction.

**Short version (for page-limited letters, e.g. PRL), already including offline physics objects:**
> The CMS apparatus~\cite{CMS:2008xjf,CMS:2023gfb} is a multipurpose, nearly hermetic detector, designed to trigger on~\cite{CMS:2020cmk,CMS:2016ngn,CMS:2024aqx} and identify electrons, muons, photons, and (charged and neutral) hadrons~\cite{CMS:2020uim,CMS:2018rym,CMS:2014pgm}. A global ``particle-flow'' (PF) algorithm~\cite{CMS:2017yfk} aims to reconstruct all individual particles in an event, combining information provided by the all-silicon tracker and by the crystal electromagnetic and brass-scintillator hadron calorimeters, operating inside a 3.8\unit{T} superconducting solenoid, with data from the gas-ionization muon detectors interleaved with the layers of the flux-return yoke outside the solenoid. The reconstructed particles are used to build \PGt leptons, jets, and missing transverse momentum~\cite{CMS:2018jrd,CMS:2016lmd,CMS:2019ctu}.
- The words "(charged and neutral)" can be skipped to gain space. "particle-flow (PF)" can be removed if the PF acronym is never used again. "(PF candidates)" can be added after "reconstructed particles" where suitable.
- If ECAL/HCAL acronyms are used more than once elsewhere, define them: "(...) by the crystal electromagnetic (ECAL) and brass-scintillator hadron (HCAL) calorimeters (...)"

**Longer version (space not a concern), to be paired with separate reconstruction-object sentences:**
> The CMS apparatus~\cite{CMS:2008xjf,CMS:2023gfb} is a multipurpose, nearly hermetic detector, designed to trigger on~\cite{CMS:2020cmk,CMS:2016ngn,CMS:2024aqx} and identify electrons, muons, photons, and (charged and neutral) hadrons~\cite{CMS:2020uim,CMS:2018rym,CMS:2014pgm}. Its central feature is a superconducting solenoid of 6\unit{m} internal diameter, providing a magnetic field of 3.8\unit{T}. Within the solenoid volume are a silicon pixel and strip tracker, a lead tungstate crystal electromagnetic calorimeter (ECAL), and a brass and scintillator hadron calorimeter (HCAL), each composed of a barrel and two endcap sections. Forward calorimeters extend the pseudorapidity coverage provided by the barrel and endcap detectors. Muons are reconstructed using gas-ionization detectors interleaved with the layers of the steel flux-return yoke outside the solenoid. More detailed descriptions of the CMS detector, together with a definition of the coordinate system used and the relevant kinematic variables, can be found in Refs.~\cite{CMS:2008xjf,CMS:2023gfb}.

**Forward calorimetry (if important to the paper), add:**
> "Forward calorimeters, made of steel and quartz-fibres, extend the pseudorapidity coverage provided by the barrel and endcap detectors."

**Tracker alignment (if important), add (Run 1 papers should also cite \cite{CMS:2014fny}):**
> The procedure followed for aligning the detector is described in Ref.~\cite{CMS:2022lime}.

**Trigger system:**
> Events of interest are selected using a two-tiered trigger system. The first level (L1), composed of custom hardware processors, uses information from the calorimeters and muon detectors to select events at a rate of around 100\unit{kHz} within a fixed latency of 4\mus~\cite{CMS:2020cmk}. The second level, known as the high-level trigger (HLT), consists of a farm of processors running a version of the full event reconstruction software optimized for fast processing, and reduces the event rate to a few kHz before data storage~\cite{CMS:2016ngn,CMS:2024aqx}.

**Combine citation (required whenever Combine is used):**
> "The following results have been determined using the CMS statistical analysis tool \textsc{Combine}~\cite{CMS:2024onh}."
> (optionally extend:) ", which is based on the \textsc{RooFit}~\cite{Verkerke:2003ir} and \textsc{RooStats}~\cite{Moneta:2010pm} frameworks."

**Integrated luminosity (Run 2 example — adjust years/values per analysis):**
> The integrated luminosities for the 2016, 2017, and 2018 data-taking years have 0.82–1.2% individual uncertainties~\cite{CMS-LUM-17-003,CMS-PAS-LUM-20-001}, while the overall uncertainty for the 2016–2018 period is 0.73%.
- If 2015 data is included, change to "2015–2018" and keep everything else the same.
- Physics Coordination requires a citation to CMS-LUM-17-003 in all CMS papers.

**Primary vertex:**
> Run 1: "The reconstructed vertex with the largest value of summed charged particle track $\pt^2$ is taken to be the primary $\Pp\Pp$ interaction vertex."
> Run 2: "The primary vertex (PV) is taken to be the vertex corresponding to the hardest scattering in the event, evaluated using tracking information alone, as described in Section 9.4.1 of Ref.~\cite{CMS-TDR-15-02}."

**Particle-flow algorithm, short form:**
> A particle-flow algorithm~\cite{CMS:2017yfk} aims to reconstruct and identify each individual particle in an event, with an optimized combination of information from the various elements of the CMS detector. The energy of photons is obtained from the ECAL measurement. The energy of an electron is determined from a combination of the electron momentum at the primary interaction vertex as determined by the tracker, the energy of the corresponding ECAL cluster, and the energy sum of all bremsstrahlung photons spatially compatible with originating from the electron track. The energy of a muon is obtained from the curvature of the corresponding track. The energy of a charged hadron is determined from a combination of the momentum measured in the tracker and the matching ECAL and HCAL energy deposits, corrected for the response function of the calorimeters to hadronic showers. Finally, the energy of neutral hadrons is obtained from the corresponding corrected ECAL and HCAL energies.

**Jet momentum (follows the anti-$k_t$ mention):**
> Jet momentum is determined as the vectorial sum of all particle momenta in the jet, and is found from simulation to be, on average, within 5 to 10% of the true momentum over the whole \pt spectrum and detector acceptance. Additional proton-proton interactions within the same or nearby bunch crossings can contribute extra tracks and calorimetric energy depositions, increasing the apparent jet momentum. To mitigate this effect, tracks identified to be originating from pileup vertices are discarded and an offset correction is applied to correct for remaining contributions~\cite{CMS:2020ebo}. Jet energy corrections are derived from simulation studies so that the average measured energy of jets becomes identical to that of particle level jets. In situ measurements of the momentum balance in dijet, $\text{photon} + \text{jet}$, $\PZ + \text{jet}$, and multijet events are used to determine any residual differences between the jet energy scale in data and in simulation~\cite{CMS:2016lmd}.

**Global event reconstruction (long form, particle-flow event reconstruction), for papers where more detail is warranted — includes fuller descriptions of photon/electron/muon/charged-hadron/neutral-hadron identification and jet clustering (anti-$k_t$, R=0.4) with residual jet-energy-scale corrections and typical jet energy resolution (15–20% at 30 GeV, 10% at 100 GeV, 5% at 1 TeV); see the source page for the full paragraph and the PUPPI-jets substitution text.**

**Missing transverse momentum (MET):**
> The missing transverse momentum vector \ptvecmiss is computed as the negative vector sum of the transverse momenta of all the PF candidates in an event, and its magnitude is denoted as \ptmiss~\cite{CMS:2019ctu}. The \ptvecmiss is modified to account for corrections to the energy scale of the reconstructed jets in the event.
- When using PUPPI for MET, add: "The pileup per particle identification (PUPPI) algorithm~\cite{Bertolini:2014bba} is applied to reduce the pileup dependence of the \ptmissvec observable. The \ptmissvec is computed from the PF candidates weighted by their probability to originate from the primary interaction vertex~\cite{CMS:2019ctu}."
- When MET filters matter, add: "Anomalous high-\ptmiss events can be due to a variety of reconstruction failures, detector malfunctions or noncollision backgrounds. Such events are rejected by event filters that are designed to identify more than 85–90% of the spurious high-\ptmiss events with a mistagging rate less than 0.1%~\cite{CMS:2019ctu}."

**Standard citations to include when a topic is discussed in detail** (BibTeX keys; see source page for full BibTeX records): overall detector description (CMS:2008xjf + Run 3 update CMS:2023gfb), L1 trigger (CMS:2020cmk), HLT (CMS:2016ngn, CMS:2024aqx), particle-flow (CMS:2017yfk), electron/photon reconstruction (CMS:2020uim Run 2 / CMS:2015xaf, CMS:2015myp Run 1), muon reconstruction (CMS:2018rym), tracking (CMS:2014pgm), tracker alignment (CMS:2021ime, plus CMS:2014fny for Run 1), tau reconstruction (CMS:2018jrd), jets/JES/JER (CMS:2016lmd), MET (CMS:2019ctu), pileup mitigation/PUPPI (CMS:2020ebo, Sirunyan:2020foa, Bertolini:2014bba), Geant4 (Agostinelli:2002hh), Combine (CMS:2024onh), luminosity (CMS-LUM-17-003).

---

## CMS Common Analysis Tools: Figure/Plotting Guidelines (cms-analysis.docs.cern.ch)

This is the current, actively-maintained plotting styling reference (supersedes/complements the older FigGuidelines twiki below), with sample implementations for Python (matplotlib + mplhep) and ROOT (PyROOT + cmsstyle).

**Font:** Helvetica, or its open-source clone TeX Gyre Heros (the CMS font of choice). `mplhep`'s "CMS" style uses TeX Gyre Heros by default. In ROOT, Helvetica is requested where available, falling back to TeX Gyre Heros otherwise (FreeSans was used before ROOT 6.32).

**CMS label position:**
- The "CMS" label is Helvetica boldface, usually within the frame, ideally in the upper-left corner. In exceptionally crowded figures it can go outside the figure (upper-left), but keeping "CMS" in-frame is strongly recommended.
- Labeling rules if reimplementing yourself:
  - "CMS" is bold; the secondary label (e.g. "Preliminary") is italic.
  - The CMS label's font size should be 1.3× the secondary label's size.
  - In-frame: CMS label equidistant from both axes, with a sufficient gap from tick marks; secondary label below or beside it, aligned with it.
  - Out-of-frame: CMS label aligned with the y-axis edge; secondary label (Simulation/Preliminary/etc.) bottom-aligned with the CMS label.
- CMS label requirements by purpose (matches the FigGuidelines table above — Paper/Paper-supplementary/PAS/PAS-supplementary/thesis-endorsement plots/other non-public work → CMS / CMS Supplementary / CMS Preliminary / CMS Work in progress / Private work, each with a "Simulation" variant). Note: "Plots part of thesis endorsement" and "Other non-public work" labels are for internal purposes/student presentations at national conferences only — cannot be included in proceedings (see PhysicsApprovals twiki for full rules).
- Scientific notation: prefer in-frame labeling to avoid conflicts with the exponent multiplier; the multiplier position can otherwise be shifted programmatically.
- Colorbars: any label on top of the plot should align to the edge of the axis, not cross into the colorbar; the colorbar should match the height of the primary axis.

**Color scheme choice** — matters for interpretability, accessibility (colorblindness, greyscale conversion in print), and aesthetics. CVD-friendly (color-vision-deficiency-friendly) palettes were selected via a D&I contest/vote and are now defaults in `cmsstyle`/`mplhep`. **Data should always be shown in black.**
- **Categorical data** (e.g. 1D stack plots): use M. Petroff's scheme (arXiv:2107.02270v2, MIT license). 6-color scheme: `#5790fc`, `#f89c20`, `#e42536`, `#964a8b`, `#9c9ca1`, `#7a21dd`. 10-color scheme (if more colors needed): `#3f90da`, `#ffa90e`, `#bd1f01`, `#94a4a2`, `#832db6`, `#a96b59`, `#e76300`, `#b9ac70`, `#717581`, `#92dadd`.
- **Sequential data** (2D heatmaps, levels): use the "viridis" colormap.
- **"Brazilian flag" limit plots:** 68% band green, 95% band yellow, using the newly recommended colors green `#228b22` and yellow `#ffcc00` (alternative: CMS logo colors `#85D1FBff` / `#FFDF7Fff`, though this alternative is explicitly noted as "not recommended"). **Note:** this differs from the color codes given on the older FigGuidelines twiki page (green `607641`, yellow `F5BB54`) — this docs page is the more current source. Two general legend forms are agreed upon by Physics Coordination and the Statistics Committee (pick one); explain the curves with text similar to: "The inner (green) band and the outer (yellow) band indicate the regions containing 68 and 95%, respectively, of the distribution of limits expected under the background-only hypothesis."
- For sequential data, "perceptually uniform" CVD-friendly palettes are recommended: "cividis" (CVD-corrected viridis), "crest"/"mako" (green-ish), "flare"/"rocket" (red-ish). For diverging data (central value with fluctuations up/down), use "vlag" or "RdBu".
- Useful tools: coolors.co (palette generator with colorblindness simulator), monolens (greyscale-conversion inspector), colorbrewer, metbrewer, seaborn (has good color-scheme discussion).

---

## CMS Figure Guidelines (older twiki version)

Source: "CMS guidelines for figures" twiki. General guidance on CMS figure conventions; further technical/implementation instructions at cms-analysis.docs.cern.ch/guidelines/plotting/.

**Basic guideline:** Clarity and visibility of the relevant objects in the figure is the guiding principle. Figures should be directly usable in presentations (size and color of fonts, markers, lines, and other relevant objects should still be visible from the middle rows of a conference room when projected). No grid should be used; tick marks should be placed on all four axes. The overall style should adhere to conventions so the figure remains interpretable without its caption (e.g., in presentations).

**Labels:**
- The "CMS" label is written in Helvetica boldface, ideally in the upper-left corner inside the frame. In exceptionally crowded figures it may go outside the figure on the upper-left, but keeping "CMS" inside the frame is strongly preferred.
- A figure containing data must show energy and luminosity, positioned out-of-frame on the upper-right, in compact notation, e.g. "36.3 fb$^{-1}$ (13 TeV)" (omit "L", "L$_{int}$", "$\sqrt{s}$"). For two or more data-taking periods: "19.7 fb$^{-1}$ (8 TeV) + 4.5 fb$^{-1}$ (7 TeV)", or "200 fb$^{-1}$ (13 and 13.6 TeV)".
- Additional labels — "Preliminary", "Simulation", "Supplementary" — are written in Helvetica italics, positioned just below the CMS label (if in-frame) or to its right (if out-of-frame).
  - Figures not yet submitted to a journal (in particular PAS, CMS Notes, DPS notes) should be labeled *Preliminary*.
  - Figures containing only simulated results should carry the label *Simulation*.
  - Supplementary figures for papers should usually include the arXiv number or similar publication information.
- Label-by-purpose table:

| Purpose | has/uses data (incl. MC) | simulation only |
|---|---|---|
| Paper | CMS | CMS *Simulation* |
| Paper (supplementary) | CMS *Supplementary* | CMS *Simulation Supplementary* |
| PAS | CMS *Preliminary* | CMS *Simulation Preliminary* |
| PAS (supplementary) | CMS *Preliminary* | CMS *Simulation Preliminary* |
| CMS Note | CMS *Preliminary* | CMS *Simulation Preliminary* |
| Figures for thesis endorsement | CMS *Work in progress* | CMS *Simulation Work in progress* |
| Other non-public work | *Private work (CMS data/simulation)* / *Private work (CMS data)* | *Private work (CMS simulation)* |

**Fonts and font size:** Helvetica, non-boldface (except the CMS label). Fonts of legends, labels, and axis labels should not be smaller than half the size of the paper's standard text.

**Legends and other information:** In stack plots, "Data" should be at the top of the legend list. "Observed" should only appear in limit plots. A legend symbol for a data point should carry the same error bars as shown in the plot itself (vertical only for fixed binning; both horizontal and vertical for varying binning). Additional info (kinematic ranges, references, dates, prefit/postfit, etc.) should usually be similar or smaller size than the legend.

**Data points, error bars, axis labels:** In 1D control distributions ("stack plots") comparing data with simulation/expectation, data are usually drawn as bullets with error bars. In stack plots, error bars indicate the statistical uncertainty of the data. In differential cross section plots, the full length of the error bar should reflect the total uncertainty (including systematic); the statistical uncertainty can be drawn as an inner error bar. (Further details, including for histograms with variable bin size and axis labels, are in the PubGuidelines page above.)

**Color palette:** See cms-analysis.docs.cern.ch/guidelines/plotting/colors/ for recommendations.

**Conventions for 3D plots:** For a 3D plot intended for journal publication (ROOT COLor option, one box per cell colored proportional to cell content), the color palette should by preference consist of varying shades of a single color — this stays legible in greyscale printouts (unlike, e.g., the blue/red extremes of a full color scale, which look similar in greyscale). A version using a fuller color spectrum, suitable for talks/conference presentations, can be included separately in the public analysis twiki. For complex plots where a single color cannot clearly convey the information, this single-color guideline may be relaxed and a full-color plot used in the publication.

**Convention for Brazilian flag plots (exclusion limit bands):**
- The 68% band should be green, the 95% band yellow.
- Recommended hex codes: yellow = `F5BB54`, green = `607641` (chosen so the inner band appears darker than the outer band, and both remain visible in greyscale).
- Explain the curves in the legend with text similar to: "The inner (green) band and the outer (yellow) band indicate the regions containing 68% and 95%, respectively, of the distribution of limits expected under the background-only hypothesis."

---

## CMS Guidelines for Authors (Style & Format)

### Introduction / Guiding Principle
- Clarity is the overriding principle for all CMS documents (papers, Analysis Notes, conference reports).
- Text must be complete, accurate, in good comprehensible English, and edited for clarity.
- Title should be concise with a clear, precise synopsis; abstract should state the actual result (not withhold it, unlike some conference abstracts).
- Different target journals have their own additional conventions; these guidelines describe the common CMS baseline.

### Self-plagiarism
- Do not copy word-for-word text used in an earlier published CMS article, except for standard boilerplate (e.g., detector description text from the CMS detector description twiki page).

---

## Style Guidelines

### Language and Spelling
- Authors may choose British **or** American English conventions, but must be **consistent** throughout the paper.
- Avoid words/usages with different meanings on opposite sides of the Atlantic (e.g., "quite different[ly]").
- British vs. American spelling differs systematically for many words (see Appendix table below).
- "Parametrize"/"parametrization" generally follow the American "-ize" spelling preference.
- British English: comma before "i.e." and "e.g." but not after; be consistent with whichever convention (British/American) is chosen.
- British: "anticlockwise"; American: "counterclockwise".
- MS Word spell-checker can be set to British/American English (Tools menu); dictionary.com, Collins Dictionary, and OED are suggested references.
- On Linux, check LaTeX spelling with `ispell -d american paper.tex` or `ispell -d british paper.tex`.

### Grammar and Punctuation

**Passive vs. active voice, present vs. past tense**
- A mixture of passive and active voice is encouraged in the body of the paper.
- Present tense is encouraged throughout to keep the paper active and engaging.

**Commas**
- Use punctuation to clarify meaning; commas set off clauses.
- Use the serial (Oxford) comma before "and"/"or" in a list of three or more items. Example: "We are indebted to our technicians, Michel Della Negra and Jim Virdee" — a serial comma before "and" avoids ambiguity about how many people are being thanked.
- For complex lists (items containing commas, "and", or phrases), use **semicolons** as item separators.
- American English: comma both before and after "i.e." and "e.g."; British English differs (see above) — be consistent.

**Hyphens**
- Use hyphens to increase clarity; there is no universally accepted rule — rewording a sentence can sometimes resolve ambiguity better than adding/removing a hyphen.
- Reference lists of conventional CMS usage:
  - **No hyphen, two words:** b jet, b quark, b tag, b tagging, beam halo particles, black hole, charged particle tracks, colour singlet state, cross section measurement, heavy ions, heavy ion collisions, Higgs boson, invariant mass distribution, jet energy corrections, jet energy scale, lead tungstate, phase space region, standard model, standard model predictions, tau lepton, top quark decays, single top quark production, Monte Carlo, Z boson, Z boson production, W boson, W boson candidate, $x$ axis, $K$ factor, in the $t$ channel.
  - **No hyphen, single word:** anticlockwise, antiquark, buildup, counterclockwise, cutoff, diboson, dilepton, dijets, dimuon, electroweak, endcap, misidentified, mistagging, monojet, multijet, noncollinear, noncollision, nondiffractive, nonflow, nonisolated, nonlinear, nonnegligible, nonperturbative, nonprompt, nonrelativistic, nonresonant, nonuniform, nonvanishing, nonzero, pickup, pileup, preselection, preshower, pseudorapidity, pseudoscalar, readout, reweighted, semileptonic, standalone, subchannel, subdetector, subleading, subprocess, subsample.
  - **Hyphenated:** anti-$k_t$ algorithm, b-tagged jet, beam-gas events, bin-by-bin correction, calculated to next-to-leading order, centre-of-mass energy, charged-hadron multiplicity, charged-pion mass, data-taking period, double-muon trigger, double-parton scattering, event-by-event fluctuations, final-state radiation, four-momentum, fourth-generation quarks, gas-ionization detector, global-muon trigger, hard-scattered partons, high-$p_T$ jets, initial-state radiation, least-squares fit, matrix-element generator, minimum-bias event, minimum-ionizing particle, multiple-parton interactions, new-physics model, next-to-leading-order calculation, particle-flow algorithm, parton-level data, proton-proton collisions, pseudo-experiments, quark-gluon scattering, root-mean-square, short-range correlations, signal-to-background ratio, two-dimensional histogram, underlying-event data, $t$-channel processes, $x$-$y$ plane.
- **Use a hyphen** for attributive adjectives formed by:
  - Noun + present/past participle: "gas-filled chambers", "English-speaking people", "U-shaped tube".
  - Adjective + present/past participle: "good-sized sample", "straight-sided cavern", "fine-grained...".
  - "Well"/"ill"/"little" + past participle: "well-known theorem", "ill-defined terms", "little-known...".
  - Preposition + noun/adjective: "near-surface reaction", "near-death experience", "next-to-leading...".
  - Temporary compounds formed by adjective + noun indicating number, dimension, or quality.
  - Compounds that form passive verb constructions (need a hyphen to show they act as such).
- **Do NOT hyphenate:**
  - Irregular comparative/superlative + participle/noun: "best known result", "least known theory".
  - Foreign phrases: "a priori solution", "in situ technique".
  - Adverbs ending in "-ly" + adjective/participle: "slowly flowing gas", "highly complex approach".
  - Chemical compounds: "sulfuric acid bath", "carbon dioxide gas", "lead tungstate crystals".
  - Compounds indicating direction/placement: "upper right corner", "north central Switzerland".
  - Temporary noun+noun compounds used as attributive adjectives: "energy flow region".
  - Permanent compounds with their own (unhyphenated) dictionary entry.
  - Comparative modifiers with "more"/"less" (except rare ambiguous cases).
- **Usually hyphenate** phrases acting as attributive modifiers: "signal-to-noise ratio", "order-of-magnitude estimate".
- **Always hyphenate** phrases listed with hyphens in the dictionary: "day-to-day variation...".
- **Nouns:** do not hyphenate a noun + gerund or a fraction acting as a noun ("problem solving..."); do hyphenate "self" compounds and verb+preposition-as-noun forms ("self-destruct", "turn-on...").
- A hyphen connects words of equal weight (joint status).
- British English tends to hyphenate word combinations that American English merges into one word.
- PACS keywords: hyphenate exactly as they appear in the official PACS listings.
- Use an **en dash** (typed as a double hyphen `--` in LaTeX, no surrounding spaces) for ranges.
- If two related hyphenated compounds occur near each other, the first may be shortened (suspension hyphen), sharing the common second word.

**Common grammatical mistakes**
- "A" before a consonant sound, "an" before a vowel sound.
- Whether to use "a"/"an" before an acronym depends on whether the acronym is read as a word or spelled out letter by letter.
- Never start a sentence with an acronym — e.g., write "The ATLAS Collaboration..." rather than starting with "ATLAS...".
- "Allows to do something" / "allows to use" is incorrect; rephrase (e.g., using "allows one to", "makes it possible to", etc.).
- "Due to" should be used only adjectivally, never adverbially. Test: try substituting "caused by" — if the sentence still works, the usage is correct.
- "Evidence" takes no "s" even in a plural sense; similarly for "information", "impact", etc.
- "Which" introduces a nonrestrictive (parenthetical, removable) clause and takes a comma; "that" introduces a restrictive (essential) clause with no comma.
  - Nonrestrictive: "This procedure is effective at identifying the background, which arises from leptonic W..."
  - Restrictive: "This procedure is effective at identifying the background that arises from leptonic W..."
- Avoid ending sentences with a preposition, except where rewording would be awkward. E.g., write "This defines the sample from which the events were selected" rather than ending with "...selected from".
- "Its" (no apostrophe) = possessive of "it" ("Its main feature is..."); "It's" (with apostrophe) = "it is" (but contractions are disallowed in CMS papers — see below).
- "Associated to" is not valid; use "assigned to" or "associated with".

### Numbers
- Spell out integers up to 10 (e.g., "there are four layers of chambers"), **except**:
  - Arithmetical manipulations: "a factor of 7", "4 orders of magnitude", "5 times the height".
  - With units of measure: "5 V", "10 s".
  - With divisions of the paper: "Section 3".
  - When numbers act as nouns: "values of 0 and 1".
- Because the line at 10 is arbitrary, authors may prefer using numerals consistently for all numbers instead.
- If logic requires a number to open a sentence, title, or heading, spell it out (or rephrase).
- When two numbers are adjacent, spell out whichever is more easily expressed in words, leaving the other as a numeral.
- Do not let a number and its units get split across a line break (use the units macros).
- Do not use commas for decimal points: write `3.14`, not `3,14`. To avoid trans-Atlantic ambiguity, group digits with thin spaces (LaTeX `\,`), not commas: e.g. `36 000`, `6 385 321`, `2048`, `3.141 59`.
- Four-digit numbers on either side of a decimal point in a table may be treated differently (grouping conventions apply).
- In scientific notation, use `\times` in LaTeX, not `\cdot`.
- When giving a percentage with an uncertainty in text, put parentheses around the uncertainty value.
- For a plain percentage, do not put a space between the number and the `%` sign.
- For a range of percentages, write "2--3%", not "2%--3%" (percent sign only once, after the second number).
- Expressions with "=", ">" , or "<" should be kept together (in math mode) rather than split across a line.
- Use "=" only with integer numbers, not real numbers.
- In ranges, don't force the same number of digits on both bounds unless it has real meaning.
- For symmetric ranges, prefer $|y| < 1.2$ rather than $-1.2 < y < 1.2$.
- It is **incorrect** to write "ranging from 30--40%" or "between 30--40%"; use words like "to"/"and" with these constructions instead of a dash, e.g. "ranging from 30 to 40%".

**Significant digits for measurements and uncertainties**
- Use at most two significant digits for quoted uncertainties (unless a specific exception applies).
- The precision quoted for an uncertainty must match the precision quoted for its associated central value.
- Examples:
  - `27.4 ± 0.1 (stat) ± 2.1 (syst)` — measurement and statistical uncertainty given to 1 decimal place.
  - `27.40 ± 0.14 (stat) ± 0.85 (syst)` — measurement and statistical uncertainty given to 2 decimal places.
  - `27.4 ± 1.3 (stat) ± 0.2 (syst)` — statistical uncertainty limited to 1 significant digit, driving the precision.
  - `27.4 ± 2.2 (syst)` — when statistical uncertainty is negligible.
- Standard labels are `(stat)` for statistical and `(syst)` for systematic uncertainty.

### Acronyms
- "CMS" and "LHC" no longer need to be defined at first use.
- Do not capitalize the words of a phrase merely because it is about to be turned into an acronym.
- Common CMS acronyms used without definition include "two-dimensional (2D)" and "confidence level (CL)".
- For "number of degrees of freedom", use consistently either "dof" or "d.o.f.".
- Acronyms for software packages should not be used without an accompanying explanation or reference.
- Do not start a sentence with an acronym (or a symbol).
- Do not use acronyms in the title unless widely known. Example: "Measurement of triple gauge-boson couplings in proton-proton collisions at 13 TeV", not an acronym-laden equivalent.
- An acronym (excluding MC program names) should not be defined unless the phrase is used a sufficient number of times later in the text (avoid defining a "TLA" used only once or twice).
- Capitalize words in an acronym's definition only if they would otherwise be capitalized, e.g., "Monte Carlo (MC) simulation of the cathode strip chambers (CSC)".

### Symbols, MC Parameters, Units, and Particle Names
- CMS LaTeX symbol/macro definitions are documented in the referenced Notes for Authors and the `macros.pdf` attachment.
- Subscripts/superscripts that abbreviate English words (e.g., "T" for "transverse") should be set in roman (upright) type, not italic.
- Particle names must always be written using the CMS particle-name macros ("pennames"), not raw symbols — e.g., `\Pell` (lepton), `\PQq`/`\PAQq` (quark/antiquark), `\Pg`/`\PGg` (gluon/photon), `\Pp`/`\Pn` (proton/neutron), `\PW`/`\PZ`/`\PV` (bosons), `\PGp`/`\PK`/`\PD`/`\PB` (hadrons), `\PGn` (neutrino), `\PH` (Higgs), `\PSg` (SUSY particles), etc. Custom particle names can be defined with the `\HepParticle`, `\HepAntiParticle`, `\HepSusyParticle`, and `\HepSusyAntiParticle` macros.
- Use the CMS `\kt` macro for the anti-$k_t$ jet algorithm ("anti-\kt").
- Standard CMS mass notation: lower-case italic "m" with a subscript for the particle (e.g., $m_t$ for top quark mass).
- If a symbol immediately follows the noun it refers to, a comma is not required before it.
- Do not start a sentence with a symbol (or acronym).
- If a symbol is used in both the abstract and the body, define it in both places.
- Do not use σ to mean "standard deviation" without explicitly defining it; if σ is also used for "cross section" in the same paper, distinguish the two uses (e.g., with subscripts) rather than overloading the symbol.
- More generally, avoid reusing the same typographical symbol to denote different quantities within a paper.
- The CMS x, y, z axes and angles ϑ and φ no longer need to be defined (see the CMS detector description twiki page).
- Angles ϑ and φ are implicitly assumed to be in radians.
- Axis labels "x", "y", "z" should be in math mode; write "$x$ axis" (math-mode x), not plain-text "x axis".
- The rapidity parameter y does not need a defining equation — it's a well-established quantity.
- Use the calligraphic "B" ($\mathcal{B}$) in LaTeX for a branching fraction.
- Missing transverse momentum should be explicitly defined at first use.
- PubComm recommends the symbol `\ptmiss` ($=p_T^{miss}$) for the magnitude of missing transverse momentum.
- Use LaTeX `\approx` as a substitute for the word "approximately" in running text.
- Use `\sim` (~) to mean "goes as", e.g., when giving the functional form of a relationship.
- Do not write inline fractions with `\frac`; use the "/" symbol instead.
- Use the CMS macros `\GeV`, `\GeVc`, `\GeVcc` (defined in the CMS style file) for energy, momentum, and mass units, respectively.
- Rapidity: $y = \frac{1}{2}\ln\left[\frac{E+cp_z}{E-cp_z}\right]$; note "c" here is a physical constant, not a unit.
- A derived unit formed by dividing two others may be written either as, e.g., m/s$^2$ or with a negative exponent.
- Add the word "events" or "candidates" as a unit where appropriate, e.g., "The background is 4.1 ± 1.3 events".
- Acronyms (e.g., SUSY) and non-mathematical superscripts/subscripts (e.g., vis, miss, jet) should be printed in roman type.
- Names of symmetry groups (SU(3), U(1), SO(5), etc.) should be set in roman type.
- Temperatures in Celsius should carry the degree symbol (°C); this is not used for Kelvin.
- Use either "center-of-mass energy" or "$\sqrt{s}$" consistently — not a mix of both.

### Word Usage and Jargon
- **Actual**: a semi-false cognate of French "actuel" — be careful of ambiguous usage.
- **Agreement**: use graded adjectives to describe the level of agreement between distributions/results rather than a flat "good"/"bad"; replace phrases like "very poor agreement" with more dispassionate wording. If the exact level of agreement matters, quantify it.
- **Antiquarks**: do not write "antitop quark" — use "top antiquark" instead (and similarly, "top quark and antiquark", not "top and antitop quarks").
- **Beamspot**: jargon — do not use unless explicitly defined first.
- **Charged tracks**: tracks are not charged, particles are — use "charged particle tracks" instead of "charged tracks".
- **Collaboration**: capitalize in phrases like "the CMS Collaboration" or "the ATLAS and CMS Collaborations".
- **Colloquial expressions**: avoid usage that is common in spoken English but improper in formal writing.
- **Convolved, not convoluted**: the correct verb for "convolution" is "convolved" — "convoluted" means something else (complicated).
- **Data**: "data" is plural — "the data are" is correct; "the data is" is incorrect.
- **Data set / Dataset**: either spelling is acceptable, but be consistent within a single paper.
- **Discriminant vs. discriminator**: both mean "a distinguishing characteristic"; "discriminant" is more commonly used in statistical contexts.
- **Fake**: physics slang — use "hadron misidentified as a lepton" (or similar) instead.
- **Higgs boson**: use the full term "Higgs boson" throughout the text.
- **Kinematics**: avoid using as a plain noun unless referring to the field of kinematics itself; rephrase otherwise.
- **Monte Carlo**: refers to a simulation technique — be careful with loose usage like "Monte Carlo program".
- **Physics jargon**: avoid slang such as "cuts", "cut tuning"; use "require" instead of "cut on", etc.
- **Pileup**: jargon — define it the first time it is used.
- **QCD events, QCD jets**: most LHC events arise from gluon fusion and could loosely be called "QCD events" regardless of process — use with care.
- **QCD**: like other acronyms (except exceptions such as "CMS"/"LHC"), define "QCD" at first occurrence.
- **Run 1 / Run 2**: do not use in the title or abstract of a CMS physics paper.
- **Sensible/sensitive**: French "sensible" = English "sensitive" — write "sensitive volume", not "sensible volume".
- **Statistics**: do not use as a substitute for "amount of data" — write "the larger sample of..." instead of "more statistics".
- **Supersymmetric particle names**: use "top squark" for the SUSY partner of the top quark, and analogous names for other SUSY squarks.
- **Two-Higgs-doublet model**: use this hyphenated, lower-case form (not "Two Higgs Doublet Model").
- **Systematics**: as a noun this word properly refers to a field of biology — use "systematic uncertainty" or "systematic bias" instead.
- **Tau lepton**: three recommended forms depending on context:
  - When `\Pe` and `\Pgm` (electron/muon macros) are used in a sentence, use `\Pgt` for the tau as well.
  - When "electron" and/or "muon" are spelled out, spell out "tau lepton" too (don't mix symbols and words).
  - When the tau lepton is mentioned alone, "tau lepton" (or just "tau" if the meaning is clear) may be used.
- **Top quark tagging / Higgs boson tagging**: PubComm discourages shortened jargon like "top tagging" or "Higgs tagging".
- **Uncertainty in vs. uncertainty on**: both forms have been used in HEP papers; pick one and be consistent.
- **Uncertainty vs. error**: an "error" is a mistake — do not use "error" when you mean "uncertainty".
- **Refer to your result as a concrete observable**: avoid vague constructions like "Measurements of $t\bar{t}$ production are obtained..." or "Limits on the parameter..."; state the result in terms of the actual physical observable measured.

### Contractions
- Do not use contractions: e.g., "let's", "don't", "can't", "won't", "it's", "shan't".

### Nested Parentheses
- APS journals (Phys. Rev. Lett., Phys. Rev. D) do not allow nested parentheses.
- When nesting would otherwise occur, replace the outer parentheses with square brackets, per APS style.

### Miscellaneous
- Do not capitalize "standard model" — it is not a proper noun.
- Words derived from proper nouns should be capitalized, e.g., "Gaussian", "Lagrangian" (with some exceptions).
- Common particle names should be spelled out in sentences, e.g., "muon", "electron" (rather than bare symbols).
- Use the full quark name in most cases, e.g., "charm quark" instead of just "charm".
- Do not write "cross section times branching fraction" — write "the product of the cross section and the branching fraction".
- Do not write "a 95% CL" — there is only one CL of 95%, so use "the 95% CL".
- In text, write "Figure 3" when starting a sentence, "Fig. 3" elsewhere (analogous abbreviation conventions apply to other cross-references, e.g., Table/Eq.).
- When referencing MC generators such as MadGraph+Pythia, use a descriptive phrase rather than simply listing tool names.
- In tables and figures, use sentence-style (single) capitalization, e.g., "Prompt leptons", not "Prompt Leptons".

---

## Format Guidelines

### Title
- Should be clear and concise; prefer words over symbols unless doing so would compromise clarity.
- Acronyms should not appear in titles unless widely known (see Acronyms section).

### Abstract
- Unlike many conference abstracts, the CMS paper abstract should state the actual final result, not withhold it.
- Abstract length limits by target journal:
  | Journal | Limit |
  |---|---|
  | PRD | About 5% of article length and less than 500 words |
  | PRL | 600 characters (~100 words at 6 characters/word) |
  | EPJC | 200 words |
  | arXiv | 1920 characters (~320 words at 6 characters/word) |
  | PLB | "concise and factual" (no strict limit stated) |
  | JHEP | "must fit in the first page" |

### PDF Author
- The `PDFAuthor` line should list the names of all authors, noting the contact author.

### PDF Title
- The `PDFTitle` line should be an exact copy of the real title with LaTeX symbols/markup removed or simplified.

### Section Headings
- Limit the number of section heading levels to 4 generally; short notes need fewer levels.

### Figures and Tables
- Follow the standard CMS plot format approved by the PubComm Steering Board (see the FigGuidelines twiki and `cms-analysis.docs.cern.ch/guidelines/plotting`).
- Produce figures using the TDR ROOT/style macros or their Python equivalents.
- Place figures and tables as close as possible to their first reference in the text.
- All figures and tables must have captions; figure captions go below the figure, table captions above the table.
- Label both plot axes, including units.
- For 1D histograms with fixed bin width, state the bin width (e.g., in the y-axis label).
- Use horizontal error bars on data points only when the bin width varies across the plot.
- For variable-bin-width plots, the y-axis may be rescaled to show a normalized ("per unit") quantity.
- In a legend, the symbol representing a data point should carry the same error bars as shown in the plot.
- Units in axis labels or table column/row headers can be given in either of two accepted formats (e.g., parentheses or after a slash).
- ROOT-specific tips exist for formatting a minus sign as a superscript in legends/axis labels, and for approximating $\mathcal{B}$ (branching fraction) using ROOT markup.
- For histograms with varying bin size, data points should be correctly positioned horizontally (see the StatComWideBins twiki page).
- For histograms with small numbers of events per bin, follow the Statistics Committee's recommended convention of asymmetric error bars with correct coverage (see the PoissonErrorBars twiki page).
- Use of colour in figures is encouraged, but figures must remain intelligible in black and white, with limited exceptions (e.g., very dense scatter plots or screen grabs).
- Subfigure identifiers such as "(a)", "(b)" are allowed only if embedded within the figure itself.
- Figures should be produced in `.pdf` format (some journals only accept this).
- Do not use the old-style, full-page figure format; size figures appropriately.
- All target journals except JHEP and JINST use a two-column-wide format — account for this when sizing figures/tables.
- Two-panel figures sharing identical horizontal axes can be stacked to save space.
- Tables can be a bigger space problem than figures — try to size and format them efficiently.
- Minimize the number of vertical and horizontal divider lines used in tables.

### Footnotes
- Footnotes are allowed in CMS papers only in very exceptional cases.
- Only in rare cases is the high visibility of a footnote justified.
- "Details" alone are never sufficient justification for the high visibility of a footnote.

### HEPData
- HEPData submission information is now required for most papers (see the CMS Scientific Publications instructions).

### Acknowledgements
- Every CMS paper submitted for publication should include an appropriate Acknowledgements section (see "Acknowledgements to include in CMS Scientific Publications").
- The most recent version of the acknowledgements text is automatically used at the time of submission.

### References
- A public CMS note or paper cannot cite an internal CMS document or a conference talk (see the "which documents can be cited" guide).
- References should be numbered consecutively in the order they are cited in the text.
- What to reference:
  - All papers useful in preparing/making the measurement.
  - Extensively, previous measurements (particularly from other LHC and Tevatron experiments).
  - Relevant theoretical papers, especially those predicting a value for your measurement.
  - A minimal general bibliography for the nonexpert reader.
- BibTeX guidance:
  - Verify all information in each reference; don't assume correctness just because it was copied from elsewhere.
  - Every journal citation should include its DOI.
  - Include the arXiv number as a courtesy to readers without journal access.
  - URLs for CMS notes/ANs should point to the CDS server, not the CMS server.
  - CMS Notes not available on CDS are private and cannot be cited in a CMS publication.
  - When citing a collaboration by name (not a first author), format the BibTeX collaboration field correctly.
  - Author lists must be entered correctly in the BibTeX file.
  - Use the URL field rather than embedding an href.
  - Guidance exists for referencing arXiv preprints vs. published versions (see WhatCanBeQuoted).
  - For standard MC generators/programs, use the correct references listed on the CMS CitationsForGenerators twiki page.
  - When using PDFs, cite all relevant publications (see the PDFatCMS and CitationsForGenerators twiki pages).
  - For statistical methods, use the CMS Statistics Committee's recommended references (StatisticsReferences twiki page).
  - Avoid using a bare URL as the sole reference unless there is no alternative.
  - Strongly avoid "Private communication" as a reference.
  - Do not put braces `{}` around an entire title (it clashes with journal style files).
  - Include any journal series letter in the journal name field, not the volume number.
  - Delete the issue number and month from the BibTeX record.
  - Some journals (e.g., JINST) reference single-digit volume numbers without a leading zero.
  - `COMMENTS` fields can be placed outside the `{...}` structure (unless using JabRef, which will complain).
- Standard BibTeX templates/examples are maintained (see `gen.bib` and the referenced templates) for common CMS citation cases, including: published CMS papers, submitted/accepted papers (`@unpublished`), combined CMS + other-collaboration papers, theory papers (published and unpublished), conference proceedings, Particle Data Group reviews (multiple yearly editions), Geant4, FastSim, the CMS Trigger paper (cite in every paper using collider data), Combine (interim reference), MadGraph, FastJet, the PDF4LHC prescription (requires two specific references, plus NNPDF set references), LHAPDF (different references for v5-and-earlier vs. v6), the joint ATLAS/CMS LHC CL-procedure document, CERN yellow book reports, CMS PAS documents (cite only for technical information, must link to CDS), Detector Performance Notes/Summaries, papers with an erratum, and Ph.D. theses. Consult the source guidelines page directly for exact BibTeX syntax for these.
- Double-check in journal proofs that the CDS link is included where required.

### Supplemental Material
- CMS discourages presenting results as an Appendix within the main paper in general; consider first whether the additional material is really necessary.
- Distinction: an **appendix** is part of the paper itself; **supplemental material** is separate from it.
- If an Appendix is not appropriate and supplemental material is needed:
  - In the "CMS format", supplemental material is included at the end of the paper as a LaTeX appendix.
  - In the "Publication format", supplemental material is a separate PDF file from the main paper.
- APS journals provide a platform for Supplemental Material (SM) submissions (per the APS submission site).
- See the Notes for Authors document, Section 4.9, for full details on the required LaTeX file and procedure.
- In the "Publication format", the two submitted PDF files are named following a pattern like `EXO-11-091.pdf` (main) and a corresponding supplement file.
- Reference the supplemental material in the main text using standard phrasing, e.g.: "See Supplemental Material at [URL will be inserted by publisher] for [brief description of material]".
- Implement this via a `\suppMaterial` macro, conditionally defined (via the `cms@external` boolean) to point either to the publisher-inserted URL or to the internal appendix.
- Other journals may use different procedures for supplemental material — consult the relevant contact.
- Separate instructions exist for creating supplemental material for the CMS public results webpage.

### LaTeX and Templates
- LaTeX is the standard for all CMS physics papers; standard documents and templates exist to help authors (see the Notes for Authors reference).

### Updating a Paper in GitLab and Producing a PDF for CADI
- Changes to a paper draft should always be uploaded to GitLab, with a new PDF version produced and stored accordingly.

### Appendix: British vs. American English Spellings
| British | American |
|---|---|
| aluminium | aluminum |
| analogue (but "analog" in opposition to "digital"), catalogue, prologue | same as British, or analog, catalog, prolog |
| analyse (or analyze) | analyze |
| cancelled, cancellation | canceled, but cancellation with two "l"s as in British |
| centre, litre, metre (but "meter" for a measuring device) | center, liter, meter |
| colour, flavour, favour, behaviour | color, flavor, favor, behavior |
| fulfil | fulfill |
| grey | gray |
| inflexion | inflection |
| labelled, modelled | labeled, modeled |
| programme (but "computer program") | program |
| sizeable | sizable |
| speciality | specialty |
| sulphur | sulfur |

## Paper Submission Preparation Checklist

Source: "Instructions on preparing your paper for submission" (PaperSubmissionPrep twiki). All steps should be completed before a paper is declared "ReadyForSub". Contact George Alverson for issues with the python scripts referenced (validated for lxplus only).

**Common issues found at "ReadyForSub" time (most frequently missed):**
- Use pennames for every occurrence of a b quark/jet: `\PQb quark`, `\PQb tagging`, `\PQb jets`, `$N_\PQb$`, etc.
- Double-check all "Z", "W", "H" boson mentions use pennames: "ttH production" → `$\ttbar\PH$ production`.
- Eliminate all vertical lines and intermediate horizontal lines from tables.
- Use `\abs{...}`, not `|...|`, for absolute value signs, e.g. `\abs{\eta}`, `\abs{m_{\mathrm{j1}} - m_{\mathrm{j2}}}`.
- Use anti-\kt in references too, not just the text, when citing the anti-$k_t$ jet finder (the algorithm's authors don't care whether the "t" subscript is roman or italic — CMS standard is roman — and are themselves inconsistent).
- All words in reference titles should be lower case except proper nouns/acronyms.
- For expressions like `$\geq$3`, `$\approx$3`, `$\sim$3` (no variable/number on the left), write them as shown to suppress the space — do not write `$\geq 3$` (can also use `${\geq}3$`).
- All figures must use vector graphics (.pdf), not .png — watch for a .png merely wrapped in a .pdf (not a true vector figure).

**General preparation steps:**
- Unlike a PAS, a PAPER's title/abstract should use the same CMS/local macros as the main text (e.g. `13\TeV`, `35.9\fbinv`) for uniform style.
- Combine all LaTeX files into the main file — no `\input{Introduction.tex}` etc.
- Place all macro definitions in the main file, not included via `\input{pdefs.tex}` or similar; move anything in `definitions.tex` into the main file.
- Define macros (via `\newcommand`, not `\def`/`\providecommand`) for user-defined expressions used more than once, e.g. `$N_{\text{jets}}$`, `$\pt^{\PQt}$`.
- Wrap math expressions in the title (and recommended for section/subsection titles) in `\texorpdfstring`, e.g.: `\title{Measurement of differential \texorpdfstring{\ttbar}{ttbar} production cross sections in \texorpdfstring{$\Pp\Pp$}{pp} collisions at \texorpdfstring{$\sqrt{s} = 13\TeV$}{sqrt(s) = 13 TeV}}` — otherwise the paper may fail to compile in journal-specific mode.
- Remove all commented-out text (`%`), including the standard CMS template comments.
- Do not include individual author bylines (`\address`, `\author`).
- **Tables:** minimize vertical/horizontal lines — in general no vertical lines and no horizontal lines except immediately after the header row (optionally one at the very top and bottom). Use `[\cmsTabSkip]` (not `\hline`) to add vertical space distinguishing sections of a table. Use `\arraystretch` to increase row spacing if needed. For PRL/PRD/PRC, replace the `tabular` environment with `scotch`. For oversized tables (only if they spill into the margin), add `\providecommand{\cmsTable}[1]{\resizebox{\textwidth}{!}{#1}}` to the header and wrap `\cmsTable` around the `tabular` environment — don't use `\small`/`\tiny`/`\scriptsize`. Use the `\NA` macro for "not applicable" entries and `\CL` for "confidence level".
- Acknowledgements are no longer required in CWR/FR or post-FR versions — the most recent version is inserted automatically at submission time.
- Verify every reference in the `.bib` file follows CMS conventions, including title case rules.
- Verify `@unpublished` (not `@article`) is used for submitted/accepted-but-unpublished papers; `@techreport` for a cited PAS; `@phdthesis` for a Ph.D. thesis.
- Compile in "preview" mode and correct reference errors.
- Ensure figure label/legend fonts are legible at the actual one- or two-column journal print size.
- Remove non-ASCII characters from `.bib`/`.tex` files, and remove all unused `\newcommand` macros.
- Place all figures in the trunk directory and rename to the standard format before final submission (can wait until the paper is declared ready for final reading, so renaming isn't repeated as figure count changes).
- Compile with the journal-specific switch and check the output (all target journals except JHEP use two-column format). Reference-related compile errors in journal-specific mode are a known, ignorable "feature" as long as normal ("preprint") mode compiles cleanly. Commands (example using EXO-17-015):
  - PLB: `utils/tdr --style paper --plb -b EXO-17-015`
  - JHEP: `utils/tdr --style paper --jhep -b EXO-17-015`
  - EPJC: `utils/tdr --style paper --epjc -b EXO-17-015`
  - PRL: `utils/tdr --style paper --aps="prl,reprint,longbibliography" -b EXO-17-015`
  - PRD: `utils/tdr --style paper --aps="prd,reprint,longbibliography" -b EXO-17-015`
  - PRC: `utils/tdr --style paper --aps="prc,reprint,longbibliography" -b EXO-17-015`
- Convert all `\(...\)` to `$...$`, and `\[...\]` to `\begin{equation}...\end{equation}`.
- Adjust figure/table placement and equation formatting by inspecting both the arXiv and journal-specific formatted versions (trial-and-error with `[htbp]`, `[htb]`, occasionally `\clearpage`) — don't over-invest, since the Publications Office may adjust placement again at submission.
- Two-column-spanning figures/tables (PLB, EPJC, PRL, PRD, PRC) need an asterisk: `\begin{figure*}`, `\end{figure*}`, `\begin{table*}`, `\end{table*}`.
- Use plain `\includegraphics`, never `\includegraphics*` (the starred form clips at the bounding box and can hide material used elsewhere) or variants using `height=`.
- For a two-panel figure, an alternative to side-by-side across two columns is stacking one-on-top-of-the-other in a single column: use `[width=0.49\textwidth]` instead of `\linewidth`, change "(left)"/"(right)" captions to `(\cmsLeft)`/`(\cmsRight)`, and use the single-column `\figure` environment (no asterisk). Required header definitions:
  ```
  \ifthenelse{\boolean{cms@external}}{\providecommand{\cmsLeft}{upper\xspace}}{\providecommand{\cmsLeft}{left\xspace}}
  \ifthenelse{\boolean{cms@external}}{\providecommand{\cmsRight}{lower\xspace}}{\providecommand{\cmsRight}{right\xspace}}
  ```
  (This makes "upper"/"lower" appear in the double-column journal format and "left"/"right" in the single-column arXiv version.)
- For APS journals only (not PLB/EPJC), an equation too long for one column can be spread across both columns by wrapping it in `\begin{widetext}...\end{widetext}` (alternative to manually splitting it across lines).
- If text sticks into the margin, wrap the offending paragraph in `{\tolerance=800 …\par}` and increase tolerance until it fits.
- Run `ispell`, confirm the paper compiles without errors, and commit all changes to git before declaring the paper ready.

## LaTeX Formatting Conventions for CMS Papers

Source: "Examples of CMS choices for formatting in a LaTeX file" (PaperSubmissionFormat twiki, updated 2024-11-04). As of 2024-03-18, the latest `tdr/utils` automatically provides equation line numbers, so the `linenomath` environment is no longer necessary.

**General:**
- Do not use `\sloppy` or `\fussy`.
- Use `\centering` in tables/figures, not `\begin{center}...\end{center}` (yields preferred centering).
- Use the `aligned` environment for multi-line equation alignment, not `eqnarray`.
- Use `\begin{equation}...\end{equation}`, not `$$...$$`.
- Use native LaTeX math spacing — don't invent your own scheme. Use `\,` for a small space between variables/factors if needed, not `~`. E.g. "3 $< \eta <$ 5" → `$3 < \eta < 5$`; `$\pt\,{\approx}\,45$` → `$\pt\approx45$`.
- Put all equations in math mode: "\sqrtsNN = 5.02\TeV" → `$\sqrtsNN = 5.02\TeV$`; "\pt $>$ 30\GeV" → `$\pt>30\GeV$`.
- Remove blank lines before `\begin{equation}` and after `\end{equation}` for correct spacing.
- No space between the end of an equation and a following punctuation mark (comma, full stop, colon).
- En/em dash usage: en dash for a range of numbers or between two names — "2.0-4.5\%" → "2.0--4.5\%"; "Cambridge-Aachen" → "Cambridge--Aachen" (also "Drell--Yan", "Bose--Einstein"); otherwise generally use a hyphen (e.g. "proton-proton"). Em dash example: "the lightest neutralino---stable and weakly interacting---is assumed to be the LSP" (no space before or after).
- Use `\to`, not `\rightarrow`, in equations.
- Do not use `\times` or `\cdot` unless it denotes an operation between two vectors — e.g. "the product $A\times\epsilon$" → "the product $A\epsilon$" (optionally `A\,\epsilon`). Exceptions where `\times` **should** be used: scientific notation (`$4.1\times 10^{-4}$`); expressions like "matrices of $5{\times}5$ crystals" (use curly braces `{\times}`); to begin a continuation line of a split equation.
- Use LaTeX2e syntax, not obsolete TeX syntax: `\mathrm{...}` not `{\rm ...}`; `\textsc{...}` not `{\sc ...}`; `\text{...}` not `{\text ...}`; `\textbf{...}`/`\mathbf{...}` not `{\bf ...}`; `\textit{...}` not `{\it ...}`.
- Subscripts/superscripts in variable names should be roman: `\mathrm` for non-Greek symbols (e.g. `s_{\mathrm{NN}}`), `\text` for text fragments (e.g. `N_{\text{jet}}`, `N_{\text{stat}}`).

**Standard macros (use these, don't redefine):** `\pt`, `\ptvecmiss`, `\ptmiss`, `\HT`, `\mT`, `\mTii`, `\mht`, `\alpS` (strong coupling), `\kt` (anti-\kt → "anti-\kt"), `\ttbar` ($\text{t}\bar{\text{t}}$), `\stat`/`\thy`/`\syst`/`\lum` for uncertainty labels (e.g. `$4.2\pm 0.3\stat\pm 0.9\syst$`, or with all four: `$48.09\pm 0.96\stat\pm 0.37\thy\pm 2.39\syst\pm 1.39\lum\pb$`), `\abs{...}` (not `|...|`), `\ie`/`\eg` (not "i.e."/"e.g."), `\CL`, `\CLs`, `\sqrtsNN`, `\mT`, `\mTii`, `\mht`. Define macros for expressions used more than once, e.g. `\newcommand{\ptmax}{\ensuremath{pt^{\text{max}}}\xspace}`.

**Pennames (particle-name macros) — use in text, tables, subscripts/superscripts, and math, not just equations:** `\PW` (W boson), `\PWpr` (W′), `\PZ` (Z boson — not the obsolete `\Z`), `\PZpr` (Z′), `\PH` (Higgs — e.g. "ggH and VH production" → `$\Pg\Pg\PH$ and $\PV\PH$ production`), `\Pe` (electron), `\Pp` (proton), `\PQq` (quark), `\PQb` (b quark — "b tagging" → `\PQb tagging`, "$N_b$" → `$N_\PQb$`), `\Pg` (gluon), `\PSQ` (squark), `\PSGcz` (lightest neutralino), `\PGmpm`/`\PGmmp` ($\mu^\pm$/$\mu^\mp$, analogous `\Pepm`/`\Pemp` for electrons), `\PGLb` (Λ_b), `\PGcc`/`\PGcb` (χ_c/χ_b), `\PAQd` (down antiquark). Example: "$\text{pp} \to \text{Bbq}$" → `$\Pp\Pp\to\PB\PQb\PQq$`. With heppennames2, all pennames have a trailing `\xspace` — never manually brace them or add trailing space, but when two or more pennames appear together they must all be in math mode to avoid excess spacing: `\Pp\Pp` → `$\Pp\Pp$`, `\ttbar\PW` → `$\ttbar\PW$`. A penname can be used in or out of math mode, but never inside `\text{}`/`\mathrm{}` (e.g. `$\Gamma_\text{\PZ}$` → `$\Gamma_{\PZ}$`).

**Other symbols:**
- Use `\overline`, not `\bar` (scales correctly), e.g. `$\overline{S}$`; use `\widetilde` for a tilde over a variable.
- Use `13\TeV`, `91\GeV` (no space before the unit macro) — gives correct small spacing and prevents line breaks between number and unit. Same pattern for `\fbinv`, `\unit`, e.g. `35.9\fbinv`, `3.8\unit{T}`, `1\unit{kHz}`, `2\unit{pb}`.
- Don't put numbers, %, etc. into math mode unnecessarily: `$1.28$--$0.07$\unit{pb}` → `1.28--0.07\unit{pb}`; `$12\%$` → `12\%`; `$\pt$` → `\pt`; `$125\GeV$` → `125\GeV`.
- For "GeV"/"TeV" in brackets (table headers, text), use `({\GeVns})` or `(\GeVns{})` (curly braces) rather than `(\GeV)`, so no space is inserted; `{\TeVns}` analogously for TeV. For GeV²: `(${\GeVns}^2$)`.
- Put entire comparison expressions in math mode for correct spacing, e.g. `$N_{\text{jets}} \geq 3$`; don't write `20$\,<\pt<\,$100\GeV`, write `$20<\pt<100\GeV$`. Exception: for `$\geq$3`, `$\approx$3`, `$\sim$3`, `$>$2` etc. with no variable/number on the left (as in a table or text), write as shown to suppress the operator-number space (`${\geq}3$` also acceptable).
- Use the `smash` macro to keep a radical sign from descending below the line, e.g. `\sqrt{\smash[b]{(\Delta\eta)^2+(\Delta\phi)^2}}`, `\mT = \sqrt{\smash[b]{2\pt^\mu\ptmiss[1-\cos(\Delta\phi_{\mu,\ptvecmiss})]}}` — only when actually needed (not for a radical that stays fully inline, e.g. `$\sqrt{s}=13\TeV$`).
- Remove any `ang=0` instruction from `\includegraphics` commands.
- Use `\GEANTfour` when referring to Geant4 (e.g. "the \GEANTfour~\cite{Agostinelli:2002hh} suite of programs"). Use the defined generator-name macros: `\PYTHIA`, `\HERWIG`, `\MGvATNLO` (Madgraph5_aMC@NLO), `\POWHEG`, `\FEWZ`, `\MCFM`, `\FASTJET`, `\HYDJET`, etc.
- For a derivative symbol, use `\rd` (e.g. `$\frac{ \rd\sigma }{ \rd\pt }$`) or the `\dd` macro (`\dd{\sigma}{\pt}`); for inline equations use `\ddinline{\sigma}{\pt}`.
- The branching-fraction symbol should be `\mathcal{B}`.
- Built-up equations (integral signs with limits, vertically stacked fraction) belong in an equation environment, not inline — an inline fraction alternative is "A/B" rather than `\frac{A}{B}`.

**Figures and tables:**
- Don't override default figure placement with commands like `\advance\leftskip-0.5cm` — do any pruning/manipulation in the PDF, not the LaTeX.
- Use `\topcaption{...}`, not `\caption{...}`, for tables (improves caption/table spacing by 10pt). Table captions go above the table; figure captions go below the figure.
- The `\subfigure` environment and "(a)", "(b)", "(c)" labels are not allowed unless embedded in the PDF itself — otherwise use "left", "center"/"middle", "right", "upper right", etc. The `minipage` environment is also not allowed.
- Acknowledgements are no longer required in CWR/FR or post-FR paper versions — inserted automatically at submission.
- Don't use boldface for itemized-list or table headers (italics, e.g. `\textit{Pileup modeling}`, is acceptable).
- For appendices: title them descriptively, not "Appendix" (e.g. "Selection efficiency of representative signal models"). The appendix comes after acknowledgements and references, and must be referenced somewhere in the main text (e.g. "Additional efficiency plots are presented in Appendix A"). Format:
  ```
  \clearpage
  \appendix
  \section{Title of appendix}
  ... contents of appendix.
  ```

Authors should carefully implement these formatting guidelines and then request review by a Journal Submission Expert (JSE) before declaring the paper "ReadyForSub".

## BibTeX / Reference Tooling: jsetools

[jsetools](https://gitlab.cern.ch/joknolle/jsetools) (maintained by Joscha Knolle) is a repository of BibTeX entries for CMS publications, formatted according to the CMS style guidelines described above, plus supporting scripts (`parse_bibtex.py`, `add_tdr.sh`, `read_refs_from_web.py`, `rename_figures.sh`, etc.) for maintaining and exporting a paper's reference list (`cmsrefs.bib`/`cmsrefs.tex`). Useful as a starting point/complement to the References section guidance above rather than something to reproduce verbatim — consult the repo directly for current BibTeX entries and tooling usage.

## Supplementary Material for CMS Public Results Pages

Guidance for adding approved supplementary content to CMS paper and Physics Analysis Summary (PAS) web pages.

- **Figures and Tables:** commit additional figures/tables to the Git repository in a file named `[PaperID]_aux.tex`. The file must compile successfully to PDF and include appropriate captions. Avoid using the LaTeX `subfigure` environment.
- **Data Files:** ROOT and tar files go in a `RootFilesAndTarFiles` subdirectory with specific naming conventions (e.g., `CMS-SMP-24-003_Figure-aux_YYY.root`). Filenames must precisely match the corresponding figures.
- **Custom HTML:** `Before.html` and `After.html` files can be added for supplementary information, but require ARC and committee approval first.
- **Process:** all supplementary materials require approval from the Analysis Review Committee and relevant convenors/Publication Committee before submission. Authors should then contact Roberto Salerno (roberto.salerno@cern.ch) with their paper ID to complete the addition to the public results page.
