# gh-teacher — TUIASI pilot

Precompiled [GitHub CLI](https://cli.github.com/) extension for the TUIASI Classroom 50 pilot.

This pilot adds cohort provisioning:

```text
gh teacher assignment provision <org> <classroom> <slug> --all [--apply]
```

## Install

Install GitHub CLI, then install this pinned pilot release:

```powershell
winget install GitHub.cli
gh extension install tuiasi-lab/gh-teacher --pin v0.1.0-tuiasi.1
gh teacher --version
gh teacher assignment provision --help
```

On macOS or Linux, use the same `gh extension install` command.

The extension downloads the native binary for the current platform. It does not require WSL, Go, or Nix.

## Pilot boundary

Only staff who need cohort provisioning should install this extension. Students continue using the upstream `foundation50/gh-student` extension.

Do not run `gh extension upgrade gh-teacher` during the pilot: that switches the installation to the upstream extension, which does not yet contain `assignment provision`. To restore the pilot release, rerun the pinned install command above.

## Source and verification

- Source branch: [`tuiasi-lab/classroom50-pilot@pilot/provision-v0.1.0`](https://github.com/tuiasi-lab/classroom50-pilot/tree/pilot/provision-v0.1.0)
- Release checksums: [`checksums.txt`](https://github.com/tuiasi-lab/gh-teacher/releases/download/v0.1.0-tuiasi.1/checksums.txt)

Before applying to a cohort, use `--all` without `--apply`, then provision one test account end-to-end.
