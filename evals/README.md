# Evals

`claude plugin eval` suite: one directory per case (`prompt.md`, or `case.yaml` for `humanize-finds-tells`,
whose planted em dash is a YAML escape), graders in `graders/`. Personas are inline because runs have no `~/`.

    claude plugin eval .                                  # full suite, 3 runs, with and without the plugin
    claude plugin eval . --runs 1 --ablation none         # cheap iteration, one arm, one run
    claude plugin eval . --case 'dm-*' --runs 1 --ablation none

Cost: every run and every `llm` grader is a real model call on your account. The full suite is about
21 cases x 3 runs x 2 arms plus three judge calls per `llm` grader per run. Results land in `results/` (gitignored).
