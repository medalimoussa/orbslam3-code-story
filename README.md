# The Story of ORB-SLAM3

**A complete code walkthrough, from `main` to `MapPoint`**

By Mohamed Alimoussa · January 2026 · 26 pages

### 📖 [Read the book (PDF)](orbslam3_code_story.pdf)

---

This book follows one image through [ORB-SLAM3](https://github.com/UZ-SLAMLab/ORB_SLAM3): from the moment you run
the program on the command line, through feature extraction, pose estimation, map building and loop closure, to the
3D map it produces. Instead of listing classes alphabetically, it tells the story in the order the code actually
runs, so you learn not only *what* each component does but *why* it exists and *how* it connects to the rest.

Each class gets a role in the cast: `System` is the director, `Tracking` the lead actor, `LocalMapping` the builder,
`LoopClosing` the proofreader, and `Frame`, `KeyFrame` and `MapPoint` are the photos and landmarks they work with.

## Contents

| Part | Topic |
|---|---|
| Prologue | The cast of characters |
| Act I | The beginning: `mono_euroc.cc`, command line to main loop |
| Act II | The brain: `System`, threads and the public interface |
| Act III | The hero: `Tracking`, initialization, pose estimation, local map, keyframe decision |
| Act IV | The photo: `Frame`, its constructors, the spatial grid |
| Act V | The builder: `LocalMapping`, new map points, local bundle adjustment, culling |
| Act VI | The proofreader: `LoopClosing`, Sim(3), loop correction, global bundle adjustment |
| Epilogue | The complete picture: data flow, thread model, core data structures |
| Appendices | File organization · quick reference and cheat sheet |

**Who it's for:** readers who know some C++ and the basic ideas of visual SLAM and want a guided tour of the
ORB-SLAM3 source instead of reading it cold.

## Build from source

The book is plain LaTeX. With a TeX Live installation, run the command twice so the table of contents resolves:

```bash
pdflatex orbslam3_code_story.tex
pdflatex orbslam3_code_story.tex
```

Chapters are in [`chapters/`](chapters/).

## Credits

This is an independent walkthrough and is not affiliated with the ORB-SLAM3 authors. ORB-SLAM3 is by Carlos Campos,
Richard Elvira, Juan J. Gómez Rodríguez, José M. M. Montiel and Juan D. Tardós, and is released under the
[GPLv3](https://github.com/UZ-SLAMLab/ORB_SLAM3/blob/master/LICENSE). The code excerpts in the book are quoted from
or adapted from it for explanation; a few passages also describe the author's own XFeat-based feature-extraction
variant. If you use ORB-SLAM3 in academic work, please cite the original paper:

> C. Campos, R. Elvira, J. J. Gómez Rodríguez, J. M. M. Montiel and J. D. Tardós,
> "ORB-SLAM3: An Accurate Open-Source Library for Visual, Visual-Inertial and Multi-Map SLAM,"
> *IEEE Transactions on Robotics*, vol. 37, no. 6, pp. 1874–1890, 2021.
