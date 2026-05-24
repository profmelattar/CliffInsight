# CliffInsight

**An educational web application that visualizes the calculation of effect sizes using Cliff's delta.**

CliffInsight is a lightweight, browser-based tool for computing and *understanding*
[Cliff's delta](https://en.wikipedia.org/wiki/Effect_size#Effect_size_for_ordinal_data),
a robust non-parametric effect size measure. Unlike common effect sizes such as
Cohen's *d*, Cliff's delta does not assume normally distributed data, which makes it
well suited to ordinal data and to the small, skewed samples often found in empirical
research.

The application has two modes, provided as two standalone pages:

- **Calculator** (`CliffCalculator.html`) — paste two groups of raw values and obtain
  Cliff's delta, its variance, and the upper and lower variance bounds, with an
  interpretation of statistical significance.
- **Educator** (`CliffsDelta.html`) — an interactive dominance matrix that shows, cell
  by cell, how every pairwise comparison contributes to the final statistic. Group
  sizes are adjustable, and a randomize button populates the matrix for quick
  experimentation.

---

## Why CliffInsight

Effect sizes tell you the *magnitude* of a difference, not merely whether it is
statistically significant. Cliff's delta is one of the most appropriate choices when
the assumptions behind parametric measures do not hold. CliffInsight is designed for
two audiences:

- **Researchers** who need a quick, dependency-free way to compute Cliff's delta and
  its variance bounds from raw data.
- **Students and instructors** who want to *see* how the dominance matrix produces the
  statistic, rather than treating it as a black box.

---

## Quick start

CliffInsight is pure client-side HTML, CSS, and JavaScript. There is **no build step,
no installation, and no dependencies**.

### Option 1 — open the file directly

1. Download or clone this repository.
2. Double-click `CliffCalculator.html` (or `CliffsDelta.html`) to open it in any
   modern web browser.

That is all that is required to run it.

### Option 2 — serve it locally

If you prefer to serve the files over `http://` (recommended if you plan to host them):

```bash
# from the repository folder
python3 -m http.server 8000
```

Then open `http://localhost:8000/CliffCalculator.html` in your browser.

---

## Running example

This example walks through computing Cliff's delta for two groups that do not overlap.

**Group 1:** `1, 2, 3, 4, 5`
**Group 2:** `6, 7, 8, 9, 10`

### Using the Calculator

1. Open `CliffCalculator.html`.
2. Paste the Group 1 values into the **Group 1** box, one value per line:

   ```
   1
   2
   3
   4
   5
   ```

3. Paste the Group 2 values into the **Group 2** box, one value per line:

   ```
   6
   7
   8
   9
   10
   ```

4. Click **Calculate Cliff's Delta**.

**Expected result:** Cliff's delta is **1.00000**. Every value in Group 2 is greater
than every value in Group 1, so the groups do not overlap at all, and the statistic
reaches its maximum. The interpretation panel reports a statistically significant
difference in favour of Group 2.

For contrast, entering two identical groups (for example `1, 2, 3, 4, 5` in both)
yields a Cliff's delta of **0.00000**, indicating complete overlap.

### Using the Educator

1. Open `CliffsDelta.html`.
2. Set **Group 1 rows** to `5` and **Group 2 columns** to `5`, then click
   **Rebuild Matrix**.
3. Enter the same values as above into the pink (Group 1) and blue (Group 2) cells,
   or click **Randomize Values** to fill the matrix with random integers.
4. The dominance matrix updates live: each cell shows `+1`, `-1`, or `0` for the
   corresponding pairwise comparison, and the row and column averages, the variance
   bounds, and the significance indicators are all derived from it.

Click any matrix cell to see how that specific pair of values is scored.

---

## Features

- Computes Cliff's delta, variance, and upper/lower variance bounds.
- Plain-language interpretation of statistical significance.
- Interactive dominance matrix with adjustable, independent group sizes.
- Randomize button for quick experimentation in the Educator.
- Visual slider placing the result on the &minus;1 to +1 scale.
- Runs entirely in the browser; no server, no installation, no data leaves the page.

---

## How to cite

If CliffInsight is useful in your teaching or research, please cite the accompanying
paper:

> El-Attar, M., Shuhaiber, A., Grati, R., & Kohail, S. (2026). CliffInsight: An
> educational web application that visualizes the calculation of effect-sizes using
> Cliff's delta. In *Proceedings of the 18th International Conference on Computer
> Supported Education* (Vol. 2, pp. 1806&ndash;1815). SciTePress.
> https://doi.org/10.5220/0015020500004021

A BibTeX entry is available in [`CITATION.cff`](CITATION.cff), and both web pages
include a built-in citation panel with APA, IEEE, ACM, and BibTeX formats.

---

## License

<!-- Replace this section with your chosen license. MIT is a common, permissive
     choice for academic tools. If you add a LICENSE file, reference it here. -->

This project is released under the MIT License. See the [`LICENSE`](LICENSE) file for
details.

---

## Contact

Maintained by Mohamed El-Attar.
<!-- Add a contact email, institutional page, or project URL here if you wish. -->

<!-- Replace with your actual repository URL once created:
     https://github.com/<your-username>/CliffInsight -->
