# The Five Extra Minutes

This zip holds only this video and its skills. It is 2D art with a depth camera that looks 3D.

| Folder / file | What it is |
|---|---|
| `video/` | The finished video and subtitles |
| `episode/` | Story, voice settings per line, sound cues |
| `art/` | Characters, sets, camera and fonts |
| `studio/`, `studio.py` | Voice, sound, render and check |
| `skills/` | All skills. Same copy in the hidden folder `.claude/skills/` (Claude Code reads that one) |
| `docs/` | Reference analysis from your repository, which the skills use |

## Skills
- `make-five-minutes-video`: written for this video's style. Start with this one.
- `make-fable`, `fable-script`, `fable-voice`, `fable-animation`, `fable-sound`, `reference-study`: the unchanged
  skills from your repository. They were written for its first example, so some details differ.

## Run it
Needs a computer with Python 3.12, Node.js, FFmpeg and internet.

    python3.12 setup.py                  # Windows: py -3.12 setup.py
    .venv/bin/python studio.py build     # Windows: .venv\Scripts\python.exe studio.py build

Setup downloads the voice files (about 340 MB). The new video appears in `output/`.

## New video
Open this folder in Claude Code and type:

> Use the make-five-minutes-video skill. Make a new story video about "YOUR TOPIC".

Each new story needs its own script, drawings and sound cues.
Third-party tools, voice files and fonts have their own licences. Check them before commercial use.
