# AGENTS.md

## About wolfSSL Documentation

This repository is the source for all wolfSSL product manuals. Documents are built to HTML via MkDocs and to PDF via Pandoc + LaTeX. Manuals cover:

- wolfSSL (TLS/crypto library)
- wolfSSH
- wolfTPM
- wolfMQTT
- wolfBoot
- wolfHSM
- wolfEngine
- wolfProvider
- wolfCLU
- wolfSSL JNI/JSSE
- wolfCrypt JNI/JCE
- Guides for FIPS, porting, and tuning

## Quick Start

Docker is preferred — it provides a consistent build environment with all dependencies pre-installed:

```bash
make              # builds all manuals via Docker
make wolfssl      # build one manual
```

Without Docker, install dependencies manually:

```bash
sudo apt install pandoc texlive-full mkdocs doxygen
cd wolfSSL/
make html
make pdf
make serve        # local preview server
```

## Directory Layout

Each product has a top-level directory containing:

```
wolfSSL/           wolfSSL TLS/crypto manual
wolfSSH/           wolfSSH manual
wolfBoot/          wolfBoot manual
wolfTPM/           wolfTPM manual
wolfMQTT/          wolfMQTT manual
wolfHSM/           wolfHSM manual
wolfEngine/        wolfEngine manual
wolfProvider/      wolfProvider manual
wolfCLU/           wolfCLU manual
wolfSSL-JNI/       wolfSSL JNI/JSSE manual
wolfCrypt-JNI/     wolfCrypt JNI/JCE manual
wolfSSL-FIPS-FAQ/  FIPS guide
wolfSSL-Porting/   Porting guide
wolfSSL-Tuning/    Tuning guide
common/            Shared theme and assets
```

Within each product directory:

```
src/               Markdown source files (English)
src-ja/            Markdown source files (Japanese translations)
mkdocs.yml         MkDocs configuration
Makefile           Per-product build targets
```

## Contributing

Edit Markdown files in the relevant `src/` directory. After editing, check both HTML and PDF output to confirm formatting is correct in both renderers — tables, code blocks, and headings can behave differently between the two.

Read `CONTRIBUTING.md` for instructions on adding new manuals, including the required directory structure and how to register a new manual in the top-level `Makefile`.

Note: Japanese translations live in `src-ja/` directories. If you add or restructure English pages, update the Japanese directory structure to match so the build does not break.
