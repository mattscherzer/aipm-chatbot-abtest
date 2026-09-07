# Chatbot A/B Test

A guided, end-to-end A/B testing example built around a chatbot added to a website. You start from raw tracking data, evaluate the experiment with both frequentist and Bayesian methods, and finish by designing the next experiment. A/B testing is a controlled experiment that compares a control version against a variant to decide which performs better on a defined metric such as conversion rate.

## Learning Objectives

By the end of this repository, you should be able to:

- Distinguish an A/B test from an observational study and describe how randomisation removes confounding.
- Clean and summarise raw tracking data into a per-variant conversion table.
- Calculate conversion rates and evaluate them with a frequentist z-test, reporting statistical significance and power.
- Compare the frequentist result against a Bayesian Beta-Binomial evaluation of the same data.
- Recommend a primary metric and plan the sample size, runtime, and minimum detectable effect (MDE) for a follow-up experiment.

## Learning Path

Work through the notebooks in this order:

| File / Folder | Description |
|---|---|
| [**01 - Frequentist Workflow**](01_chatbot_ab_test_frequentist_workflow.ipynb) | Experiment background, data loading and cleaning, exploratory analysis, a per-metric summary table, and the frequentist A/B test evaluation. |
| [**02 - Bayesian Follow-up**](02_chatbot_ab_test_bayesian_followup.ipynb) | Re-evaluates the same test with a Bayesian Beta-Binomial model and compares the two conclusions. |
| [**03 - Experiment Design and Power**](03_chatbot_ab_test_experiment_design_and_power.ipynb) | Turns the findings into the next experiment: candidate metrics, a metric recommendation, sample-size and power planning, and a concrete test brief. |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**Data**](data/) | The chatbot experiment dataset and the cleaned and summarised tables derived from it. |
| [**Assets**](assets/) | Diagrams and screenshots used in the notebooks (schema, chatbot website views). |
| [**pyproject.toml**](pyproject.toml) | Project configuration and dependencies. |
| [**uv.lock**](uv.lock) | Dependency lock file. |

## Setup

> [!NOTE]
> Throughout these steps, text in angle brackets like `<repo-name>` is a **placeholder**. Replace it, including the `< >` brackets, with your own value. For example, `cd <repo-name>` becomes `cd ds-chatbot-abtest`.

### 1. Create the Repository from the Template

Click **Use this template** on GitHub.

When creating the repository:

- Set yourself as the **Owner**
- Choose a repository name
- Disable **Include all branches**
- Click **Create repository**

> [!IMPORTANT]
> If you are working in pairs or groups, only **one person** should complete this step.

---

### 2. Add Collaborators (Pairs/Groups Only)

If working with teammates:

1. Open the repository on GitHub
2. Go to **Settings → Collaborators**
3. Add your teammates as collaborators
4. Share the repository link with your team

Teammates should accept the invitation before continuing.

---

### 3. Clone the Repository

Copy the SSH URL from the **Code** button on GitHub, then run:

```bash
git clone <copied-ssh-url>
```

The copied SSH URL will look like `git@github.com:<your-username>/<repo-name>.git`.

---

### 4. Move into the Project Folder and Install Dependencies

This installs all dependencies and creates a virtual environment in (`.venv/`).

```bash
cd <repo-name>
uv sync
```

---

### 5. Open the Notebooks

> [!NOTE]
> Make sure you open VS Code from the project root so it automatically detects the environment created by `uv sync`.

Launch VS Code in the project root folder:

```bash
code .
```

Then open a notebook and select the Python environment created by `uv sync` as the kernel.

## References & Further Reading

- [**Trustworthy Online Controlled Experiments**](https://www.cambridge.org/core/books/trustworthy-online-controlled-experiments/D97B26382EB0EB2DC2019A7A7B518F59): The standard practical guide to A/B testing, by Kohavi, Tang, and Xu.
- [**scipy.stats**](https://docs.scipy.org/doc/scipy/reference/stats.html): The statistical distributions and tests used in the notebooks.
- [**Conjugate Prior (Wikipedia)**](https://en.wikipedia.org/wiki/Conjugate_prior): Why the Beta distribution pairs naturally with binomial conversion data in the Bayesian notebook.
- [**Refuted Observational Studies**](https://experimentguide.com/refuted_observational_studies/): Real cases where controlled experiments overturned observational findings.
- [**The Highest Paid Person's Opinion**](https://jeffgothelf.com/blog/highest-paid-persons-opinion/): On replacing HiPPO-driven decisions with tested hypotheses.
