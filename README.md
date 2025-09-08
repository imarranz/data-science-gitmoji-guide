
# 📊 Data Science Gitmoji Guide

![](https://repository-images.githubusercontent.com/1040634553/460955b6-9d76-40c0-8f0c-3ee3e1385077)

![Guide](https://img.shields.io/badge/type-Guide-blueviolet?style=flat-square&logo=book)
![Data Science](https://img.shields.io/badge/domain-Data%20Science-orange?style=flat-square&logo=anaconda)
![Git](https://img.shields.io/badge/version_control-Git-red?style=flat-square&logo=git)
![Gitmoji](https://img.shields.io/badge/conventions-Gitmoji-yellow?style=flat-square&logo=git)
![Markdown](https://img.shields.io/badge/format-Markdown-lightgrey?style=flat-square&logo=markdown)
![Author](https://img.shields.io/badge/author-ibon-blue?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/status-En%20desarrollo-orange?style=flat-square)
![PRs](https://img.shields.io/badge/PRs-Welcome-brightgreen?style=flat-square)
![Stars](https://img.shields.io/github/stars/imarranz/ds-gitmoji-guide?style=flat-square)
![Forks](https://img.shields.io/github/forks/imarranz/ds-gitmoji-guide?style=flat-square)


This repository defines a **Gitmoji-based convention** for Data Science projects.

It extends the original [gitmoji.dev](https://gitmoji.dev/) idea by incorporating [GitHub-supported emoji codes](https://github.com/ikatyang/emoji-cheat-sheet) to maximize compatibility and readability in commit messages. These enhancements include custom emojis and well-defined scopes specifically tailored for **data pipelines, exploratory data analysis (EDA), notebooks, modeling, visualization, MLOps, and reproducibility**. The goal is to provide a richer, more expressive commit convention that captures both the technical and scientific context of each change, making collaboration easier and commit histories more insightful for teams working in Data Science projects.

---

## 📑 Table of Contents

- [Commit Message Format](#-commit-message-format)
- [Scopes](#-scopes)
- [Emoji Intention Reference](#-emoji-intention-reference)
  - [Data & Preparation](#-data--preparation)
  - [Exploration & Analysis](#-exploration--analysis)
  - [Modeling & Evaluation](#-modeling--evaluation)
  - [Notebooks & Reproducibility](#-notebooks--reproducibility)
  - [Pipelines, MLOps & Infra](#-pipelines-mlops--infra)
  - [Quality, Security & Maintenance](#-quality-security--maintenance)
  - [Documentation & Communication](#-documentation--communication)
- [Examples](#-examples)
- [Searching Commits](#-searching-commits)
- [Guidelines](#-guidelines)
- [Inspiration](#-inspiration)

---

## 📝 Commit Message Format

A clear and consistent commit message structure helps teams understand the purpose of each change at a glance. In Data Science projects, where experiments, models, and data transformations evolve quickly, good commit hygiene is essential for reproducibility, collaboration, and compliance with good practices (e.g., ALCOA+ or GCP standards).

This convention uses emojis as intentions, an optional scope to narrow the context, and a concise short message, optionally followed by a longer description for details.

Each commit message follows this structure:

```

<intention>\<intention?> \[scope]: \[short message]

\[long message]

```

- **`<intention>`**: one emoji (required).
- **`<intention?>`**: optional second emoji (for extra nuance).
- **`[scope]`**: the context of the change (see list below).
- **`[short message]`**: a concise description (max 72 chars).
- **`[long message]`**: optional detailed description (what/why/how).

### Example

```

🧹 [clean]: Remove outliers from ALT variable

Applied IQR method to detect and remove outliers in the ALT column.
This improves normality assumptions for downstream models.

```

---

## 🎯 Scopes

Scopes define the **context** of a commit. They act like labels that specify the part of the workflow or codebase affected by the change.

In Data Science projects, having clear and standardized scopes is particularly useful because changes can happen at very different levels: **data cleaning**, **feature engineering**, **modeling**, **notebooks**, **pipelines**, or **infrastructure**. By tagging commits with scopes, you can later filter your history with `git log` to answer questions like: _“When did we last update the preprocessing pipeline?”_ or _“Which commits introduced new experiments?”_.

Scopes should be **short**, **descriptive**, and **stable** across the lifetime of the project, so they remain useful for searching and automation.

Recommended scopes (short and grep-able):

```

data, ingest, clean, impute, schema, labels, fe, eda, viz, stats,
exp, hparam, model, train, metrics, xai, nb, nb2py, report, env,
config, pipeline, ci, serve, monitor, rollback, security, refactor,
deps, style, tests, infra, dvc, sql, py, r, docs, release

```

---

## 💡 Emoji Intention Reference

Emojis are the **visual anchors** of this convention. Each one represents an intention behind the change: was it about cleaning data, adding a new model, fixing a bug, or updating documentation?

In this extended Gitmoji set, every concept has its **own unique emoji** (no overlaps), tailored to Data Science workflows. Categories are grouped by domain (data preparation, analysis, modeling, notebooks, pipelines, etc.) so it’s easy to pick the right emoji and keep the project history clean and meaningful.

### 🔹 Data & Preparation

The foundation of any Data Science project lies in **data preparation**. This includes ingestion, cleaning, handling missing values, defining schemas, and ensuring reproducibility. Clear commits in this category help track how raw data was transformed into reliable inputs for models, making the workflow transparent and auditable.

| Emoji | Meaning | Example |
|-------|---------|---------|
| 📥 | Data ingestion / connectors | 📥 [ingest]: Add LC-MS data loader |
| 🧹 | Data cleaning | 🧹 [clean]: Normalize columns and remove outliers |
| 🧩 | Missing value imputation | 🧩 [impute]: Add KNN imputer for BMI |
| 🔀 | Sampling / splitting | 🔀 [data]: Stratified train/test split |
| 🧱 | Data schema validation | 🧱 [schema]: Add Great Expectations checks |
| 🏷️ | Labeling / targets | 🏷️ [labels]: Update MASLD diagnosis labels |
| 🌱 | Random seeds / reproducibility | 🌱 [repro]: Fix random_state in pipeline |
| 🧰 | Feature engineering | 🧰 [fe]: Add PCA-based features |
| 🗃️ | Data versioning (DVC) | 🗃️ [dvc]: Track dataset v1.3 |
| 🕶️ | Anonymization / privacy | 🕶️ [privacy]: Mask patient IDs |

---

### 🔹 Exploration & Analysis

Before building models, data must be **explored and analyzed**. This stage covers exploratory data analysis (EDA), visualizations, statistical tests, and experiment tracking. Capturing these changes with dedicated emojis ensures that the process of understanding the data remains well documented and easy to revisit.

| Emoji | Meaning | Example |
|-------|---------|---------|
| 🧐 | Data exploration / EDA | 🧐 [eda]: Generate profile report |
| 📊 | Visualizations | 📊 [viz]: Add ROC and PR curves |
| 📏 | Statistical tests | 📏 [stats]: Run Pearson correlation |
| 🧪 | Experiments | 🧪 [exp]: Run new MASLD experiment |
| ⚗️ | Hyperparameters | ⚗️ [hparam]: Bayesian optimization sweep |

---

### 🔹 Modeling & Evaluation

Modeling is the core of many Data Science projects. This section includes introducing new models, retraining with updated data, refactoring model code, benchmarking performance, and evaluating with metrics or explainability tools. Well-tagged commits make it easy to trace model evolution and compare approaches over time.

| Emoji | Meaning | Example |
|-------|---------|---------|
| ✨ | New model | ✨ [model]: Add logistic regression baseline |
| 🔁 | Retrain | 🔁 [train]: Retrain SVM with new cohort |
| 🛠️ | Model refactor | 🛠️ [model]: Clean redundant code in fit() |
| 📈 | Metrics | 📈 [metrics]: Add AUC/PR reporting |
| 🧠 | Explainability (XAI) | 🧠 [xai]: Add SHAP values |
| ⏱️ | Benchmarking / performance | ⏱️ [perf]: Compare inference times |

---

### 🔹 Notebooks & Reproducibility

Notebooks are often the entry point for Data Science work, but reproducibility requires discipline. This category covers commits related to notebooks, converting them into scripts, freezing environments, and generating reports. These practices ensure that experiments can be rerun consistently and shared with collaborators.

| Emoji | Meaning | Example |
|-------|---------|---------|
| 📓 | Notebooks | 📓 [nb]: Add EDA notebook |
| 🔗 | Notebook → script | 🔗 [nb2py]: Convert preprocessing to Python script |
| 📰 | Reports | 📰 [report]: Generate results |
| 📦 | Freeze environment | 📦 [env]: Add environment.yml |

---

### 🔹 Pipelines, MLOps & Infra

As projects mature, workflows need to be **automated and deployed**. This section includes configuration files, pipelines/DAGs, CI/CD, serving endpoints, monitoring, and rollbacks. Using dedicated emojis highlights the operational side of Data Science, bridging the gap between experimentation and production.

| Emoji | Meaning | Example |
|-------|---------|---------|
| ⚙️ | Config files | ⚙️ [config]: Add pipeline.yaml |
| 🏗️ | Pipelines / DAGs | 🏗️ [pipeline]: Add Airflow DAG |
| 🤖 | CI/CD | 🤖 [ci]: Add GitHub Actions workflow |
| 🌐 | Serving / deployment | 🌐 [serve]: Add FastAPI /predict endpoint |
| 📡 | Monitoring | 📡 [monitor]: Add drift detection |
| ⬅️ | Rollback | ⬅️ [rollback]: Revert model v2 to v1 |

---

### 🔹 Quality, Security & Maintenance

Good science and engineering rely on **clear communication**. This section covers documentation, contributors, release tagging, and updates to text or messages. By tagging these commits explicitly, teams make it easier for others to onboard, reproduce results, and understand the project history.

| Emoji | Meaning | Example |
|-------|---------|---------|
| ✅ | Tests | ✅ [tests]: Add unit test for preprocessing |
| 🐞 | Bugfix | 🐞 [fix]: Correct NaN handling in imputer |
| 🚑 | Hotfix | 🚑 [hotfix]: Fix prod error in endpoint |
| 🔐 | Security / secrets | 🔐 [security]: Rotate API keys |
| ♻️ | Refactor | ♻️ [refactor]: Simplify data pipeline |
| 📌 | Dependency management | 📌 [deps]: Pin pandas==2.2.2 |
| 🎨 | Lint / style | 🎨 [style]: Format code with black |

---

### 🔹 Documentation & Communication

Document decisions, update text/strings, manage contributors, and tag releases.

| Emoji | Meaning | Example |
|-------|---------|---------|
| 📝 | Documentation | 📝 [docs]: Update README |
| 💬 | Text / strings | 💬 [copy]: Fix UI messages |
| 🙋 | Contributors | 🙋 [community]: Add co-author |
| 🏷️ | Release | 🏷️ [release]: Tag v1.0.0 |

---

## 📌 Examples

Examples illustrate how the convention looks in practice. They combine emojis, scopes, and messages into concrete commits that are short yet descriptive. This section is meant to inspire your team and provide quick references when you’re unsure about how to phrase a commit.

```

🧹 [clean]: Remove outliers from ALT variable

Applied IQR method to detect and remove outliers in the ALT column.
This improves normality assumptions for downstream models.

```

```

✨ [model]: Add support vector machine for MASLD classification

* Kernel: RBF
* Class_weight: balanced
* Trained with cohort v2

```

```

📓 [nb]: Add PCA exploration notebook

Includes variance explained plot, loadings heatmap,
and interactive scatter for PC1 vs PC2.

````

---

## 🔍 Searching Commits

One of the main strengths of this convention is that it makes your commit history **queryable**. By grepping for emojis or scopes, you can instantly filter commits related to a particular task, such as all model changes, all experiments, or all cleaning steps. This helps with traceability, auditing, and knowledge transfer in collaborative Data Science projects.

By **emoji**:

```bash
git log --grep="🧹" --oneline
````

By **scope**:

```bash
git log --grep="\[model\]" --oneline
```

By **both**:

```bash
git log --grep="^📈 \[metrics\]" --oneline
```

---

## ✅ Guidelines

Guidelines summarize the best practices for writing commits under this convention. They serve as a checklist to ensure consistency and readability across the team. Following them keeps your history **clean**, **searchable**, and **reproducible**, which is especially critical in regulated or research environments.

1. Use **1–2 emojis** max per commit.
2. Always include a **scope** where relevant.
3. **Short message** in imperative mood.
4. **Long message** if the change needs context.
5. Keep commits **atomic**.

---

## 📚 Inspiration

This convention builds on the [gitmoji.dev](https://gitmoji.dev/)  initiative and adapts it for Data Science workflows. It reflects lessons learned from working with **notebooks**, **reproducible pipelines**, **MLOps**, and **collaborative data analysis**. The result is a practical toolkit to make commit histories more meaningful and aligned with scientific and engineering practices.

* [gitmoji.dev](https://gitmoji.dev)
* Data Science workflow needs (EDA, cleaning, modeling, MLOps)
* [GitHub Emoji Cheat Sheet](https://github.com/ikatyang/emoji-cheat-sheet) — Full list of emoji codes supported by GitHub.

---

## 💡 Contributions welcome!

This is not a closed project — if you have **any suggestions**, **new emojis**, or frequently used **actions** that could be included, feel free to open an _issue_ or submit a _pull request_.

