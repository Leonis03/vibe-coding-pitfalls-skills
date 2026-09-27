# vibe-coding-pitfalls-skills

Agent skills for Claude Code and Antigravity (`agy`). Most of them encode a failure that
had already cost real time, so the agent does not walk into it again. They are exported from the same source as
[vibe-coding-pitfalls](https://github.com/Leonis03/vibe-coding-pitfalls), where the
pitfall index explains why each one exists; a few skills link to docs there.

| Skill | What it is for |
| :--- | :--- |
| [`android-chroot-debian`](skills/android-chroot-debian/SKILL.md) | Diagnose, configure, and troubleshoot root Debian chroot environments on Android (Termux). |
| [`antigravity-cli`](skills/antigravity-cli/SKILL.md) | Delegate a one-shot prompt, a local image, or a task inside one directory to Google Antigravity CLI (agy, Gemini 3.x) through the least-privilege wrapper agy-run.sh -- sandboxed, read-only by default, write and command access only through grants the user runs. |
| [`bx`](skills/bx/SKILL.md) | Web search, news, images, videos, places and AI-synthesized answers via the Brave Search `bx` CLI. |
| [`compress-wsl-space`](skills/compress-wsl-space/SKILL.md) | Safely estimate and compact local WSL2 ext4.vhdx disk usage on Windows. |
| [`deepln-setup`](skills/deepln-setup/SKILL.md) | Connect to and provision a rented DeepLN cloud GPU node over SSH -- any card, not just the Tesla P4. |
| [`docx-to-md`](skills/docx-to-md/SKILL.md) | Convert Word documents (.docx) to high-quality Markdown with precise mathematical formula error correction (LaTeX \$...\$ and \$\$...\$\$), pure standard Markdown syntax (zero HTML tags), relative image links, clean table generation, code block formatting, and visual bounding-box formula recovery. |
| [`download-bilibili`](skills/download-bilibili/SKILL.md) | Download Bilibili videos or audio with BBDown and process downloaded audio with ffmpeg/ffprobe. |
| [`gpu-cuda-checks`](skills/gpu-cuda-checks/SKILL.md) | Verify that PyTorch CUDA work really runs on the GPU on any rented cloud box, and avoid the silent-CPU-fallback trap. |
| [`honor-linuxlab`](skills/honor-linuxlab/SKILL.md) | Diagnose, recover, and optimize the Honor Tablet Linux Lab (com.hihonor.pcengine) PRoot environment. |
| [`inspect-session`](skills/inspect-session/SKILL.md) | Inspect, audit, and analyze coding agent conversation transcripts (Claude Code JSONL, Antigravity/Gemini). |
| [`linux-cjk-font`](skills/linux-cjk-font/SKILL.md) | Configure and render publication-grade Chinese (CJK) text and Unicode box-drawing tables in images via Python (Matplotlib, Seaborn, Pillow, OpenCV) in WSL and Linux environments. |
| [`pdf-to-md`](skills/pdf-to-md/SKILL.md) | Convert PDF documents (especially academic papers, math modeling reports, and WPS/Word-exported PDFs) to publication-grade Markdown with precise LaTeX mathematical formula error correction (\$...\$ and \$\$...\$\$), pure standard Markdown syntax (zero HTML tags), relative image links, continuous paragraph unwrapping, GFM tables, and visual bounding-box formula recovery. |
| [`shuorenhua`](skills/shuorenhua/SKILL.md) | On request, edit or review Chinese or English prose to strip AI-tell -- template phrasing, filler wrappers, register drift -- so it reads like a person rather than a model performing. |
| [`termux-debian-external-drive`](skills/termux-debian-external-drive/SKILL.md) | Mount, read, write, and safely manage external USB storage and mobile hard drives (NTFS, exFAT, FAT32) inside Termux Debian root chroot containers on Android. |
| [`trim-branch`](skills/trim-branch/SKILL.md) | Diagnose and fix Claude Code conversation JSONL branch/fork issues. |
| [`video-to-md`](skills/video-to-md/SKILL.md) | Two-track extraction from lecture, talk and tutorial video files (.mp4, .mov, .mkv, ...) -- the speaker's verbatim transcript, and the documents shown on screen (slides, Word, code, formulas). |
| [`wsl-windows-command`](skills/wsl-windows-command/SKILL.md) | Run Windows commands, programs, and config edits from WSL2 via interop, and drive other WSL distros from one distro. |

## Install

```bash
npx skills add Leonis03/vibe-coding-pitfalls-skills --list                      # see what is here
npx skills add Leonis03/vibe-coding-pitfalls-skills --skill <name> -g --copy    # one skill, user-level
```

`--copy` copies the files into the agent directories instead of symlinking them. Copying by hand
also works: `skills/<name>/` goes to `~/.agents/skills/<name>/`, `~/.claude/skills/<name>/` or
`~/.gemini/config/skills/<name>/`.

**Placeholders.** The skills are redacted. Values in angle brackets (`<your-home>`,
`<proxy-port>`, `<ssh-port>`, `<instance-domain>`, ...) and `CourseName` stand for
your own values; replace them after installing. `$HOME` is a real shell variable and stays
as it is.

Some skills are machine-specific by nature (`honor-linuxlab`, `deepln-setup`,
`compress-wsl-space`); read the SKILL.md before installing them.

## License

Code (`scripts/`) is [MIT](LICENSE); documentation (every `.md`) is
[CC BY 4.0](LICENSE-DOCS).

Generated by `tools/publish.sh` from 726a605 -- edit the source, not this repo.
