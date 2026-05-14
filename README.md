# RayshineRen Skill

A standalone Codex skill that captures RayshineRen's technical identity, research lineage, publication context, and engineering working style.

It does **not** require access to any private repository. If users provide extra files, papers, logs, or repositories, the skill can use them as optional evidence; otherwise it works from the bundled profile and playbooks.

## Install

```bash
python ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo RayshineRen/rayshineren-skill \
  --path rayshineren
```

Restart Codex after installation, then invoke:

```text
Use $rayshineren to reason in RayshineRen's technical style.
```
