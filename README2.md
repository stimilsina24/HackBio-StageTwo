  <h1>Reproducing a Core Single-Cell RNA-Seq Analysis Pipeline Using Scanpy</h1>
</div>

---

## 🎯 Purpose

I replicated the **Scanpy pipeline** to annotate cells from a mystery single-cell dataset, labeled as ‘bone marrow,’ and to speculate whether ‘bone marrow’ is indeed the tissue of origin.

---

## ⚙️ Workflow

The standard Scanpy pipeline executed using a Jupyter notebook involved the following steps:

1.  **Install and import necessary libraries:** (Scanpy, anndata, Decoupler, Pandas)
2.  **Data import and formatting**
3.  **Quality Control (QC):**
    * Assess percent Mitochondrial genes ($\text{%MT}$), percent Ribosomal genes ($\text{%RB}$), and percent Hemoglobin genes ($\text{%HB}$).
    * Check gene counts per cell and total counts.
4.  **Filtering out low-quality cells:**
    * Filtering criteria: stressed/irrelevant cells ($\text{%MT} < 5$, $\text{%RB} < 10$, and $\text{%HB} < 5$).
    * Filtering criteria: empty wells or doublets (gene counts $> 200$ per cell and cell count $> 20$ per gene).
5.  **Finding Highly Variable Features**
6.  **Dimensionality Reduction:** using Principal Component Analysis (PCA)
7.  **UMAP and Leiden Clustering**
8.  **Cell Annotation:** using **Decoupler** and **PanglaoDB**.
    * Use the top-scoring cell type per cluster for annotation.
9.  **Visualization:** (heatmap, dotplot, violin plot)

---

## 🔬 Findings

Several populations of blood cells were identified in the dataset:

* **Neutrophils:** **Innate immune cells** that are usually the first line of defense against infection, functioning through **phagocytosis** or extracellular traps.
* **$\gamma\delta$ T cells:** An alternative type of T lymphocyte that **bridges innate and adaptive immunity** to help fight infections or cancer.
* **Nuocytes (ILC2s):** A type of innate lymphoid cell that plays a role in antibody or B cell-mediated immunity against parasites and allergens, or tissue repair through cytokine production.
* **NK cells:** Innate lymphocytes that destroy virus-infected and cancer cells through the release of **cytotoxic molecules** that act on target cells.
* **Naive B cells:** Inactive B lymphocytes that are precursors to plasma cells or memory B cells, and not yet exposed to activating antigen signals.
* **Platelets:** Fragments of megakaryocyte cells that help with **blood clotting** and prevention of bleeding.
* **Plasma cells:** Activated B lymphocytes that serve as **antibody factories** to help fight off infections from bacteria or viruses.
* **Monocytes:** Circulating immune cells that perform **phagocytosis, antigen presentation**, and other functions. They can differentiate into macrophages or dendritic cells upon entering tissues.

---

## 💡 Conclusion

The tissue of origin is most likely **not bone marrow** (most likely the **lung or blood**), considering the high composition of immune cells in the sample and the **absence of stem or progenitor** mesenchymal or hematopoietic populations. The tissue could be undergoing an **early stage of infection or immune activation** due to the prevalence of mostly innate immune cell types.

It was surprising to see many of the genes **overlapping** between a lot, but not all, cell populations. This could be due to the inability of single-cell sequencing to fully differentiate similar cell populations due to low sequencing depth, or alternatively, the markers used for annotation may not be specific enough, making automated annotation less than optimal and conclusions less solid.

---

## 🧮 Core Analysis Dependencies

| Name | Version | Build/Channel Info |
| :--- | :--- | :--- |
| **scanpy** | 1.11.5 | pyhd8ed1ab\_0 (conda-forge) |
| **anndata** | 0.11.4 | pyhd8ed1ab\_0 (conda-forge) |
| **scvi-tools** | 1.3.3 | pypi\_0 (pypi) |
| **decoupler** | 2.1.2 | pypi\_0 (pypi) |
| **umap-learn** | 0.5.9.post2 | py310hff52083\_0 (conda-forge) |
| **leidenalg** | 0.11.0 | pypi\_0 (pypi) |
| **numpy** | 2.2.6 | py310hefbff90\_0 (conda-forge) |
| **scipy** | 1.15.2 | py310h1d65ade\_0 (conda-forge) |
| **pandas** | 2.3.3 | py310h0158d43\_1 (conda-forge) |
| **seaborn** | 0.13.2 | hd8ed1ab\_3 (conda-forge) |
