# MoviePilot — Unraid Community Applications template

Unofficial, community maintained Unraid CA template for
[MoviePilot](https://github.com/jxxghp/MoviePilot).

| | |
|---|---|
| Template | `MoviePilot_v3.xml` |
| Docker image | `jxxghp/moviepilot-v3` |
| Web UI | port `3000` |
| Support thread | https://forums.unraid.net/topic/184591-support-moviepilot-v3/ |
| Upstream project | https://github.com/jxxghp/MoviePilot |
| Documentation | https://wiki.movie-pilot.org |

## Quick notes

* V3 ships as its own image (`jxxghp/moviepilot-v3`). V2 stays on
  `jxxghp/moviepilot-v2`; this template does not upgrade a V2 install in place.
  Run V3 alongside V2 with a separate appdata folder first, then retire V2.
* Map `/media` and `/downloads` under the same Unraid share (for example both
  under `/mnt/user/`). Different shares mean different filesystems, and
  MoviePilot will fall back to copying instead of hardlinking.
* Settings are stored in `/config/app.env` and can also be edited from the web UI.
* `Docker Socket` is optional and left unmapped by default. Only plugins that
  restart containers need it.

## Template maintenance

The template is hand written. It is deliberately **not** produced by the
"convert existing container" tool, and it does not carry build-time environment
variables from the image (`LANG`, `HOME`, `PYTHON_*`, `GPG_KEY`, `DISPLAY`,
`TERM`, `CONFIG_DIR`), a `DateInstalled` field, or a
`Community_Applications_Conversion` marker. Only settings a user is expected to
change are exposed.

Template issues → the Unraid support thread above.
MoviePilot bugs → https://github.com/jxxghp/MoviePilot/issues
