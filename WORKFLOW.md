# Reading Workflow

The workflow separates private reading from public curation.

## 1. Add the PDF Locally

Save the article in _downloads/. It is ignored by Git and is never pushed to GitHub.

## 2. Create a Private Note

Create _private_notes/<paper-id>.md. Record rough notes, page references, figure interpretation, questions, and tentative ideas there. This file is also ignored by Git.

## 3. Add a Public Paper Entry

Add one concise line to [papers.md](papers.md) with the paper's DOI, region, age, method, and a to-read status. Do not infer a conclusion from the title or abstract.

## 4. Read and Extract Evidence

At minimum, check the abstract, methods, results, figures, discussion, and stated limitations. Record:

- study area and age control;
- proxy, calibration, and model assumptions;
- quantitative result and uncertainty;
- the authors' conclusion;
- alternative explanations and caveats.

## 5. Publish the Curated Record

Update the entry in [papers.md](papers.md) with an evidence-based finding and change the status to read. For a paper that merits detail, add an English note under notes/.

## 6. Commit Only Public Material

    git add papers.md notes catalog
    git commit -m "Add reading note for <short topic>"
    git push

Before committing, confirm that Git is not tracking content under _downloads/ or _private_notes/.
