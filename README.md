# phonometry-assets

The rendered animation clips of the [phonometry](https://github.com/jmrplens/phonometry) documentation, and the poster frame each one shows before it plays.

Nothing here is edited by hand. Every file is written by `make animations` or `make posters` in the phonometry repository, which renders the clips from the code under `scripts/figures/` and pushes the result here. The code that draws a clip lives there; this repository holds only what it produced.

They live apart from the code because they are binary and large. A clip is re-encoded whenever the code that draws it changes, and each re-encode stores the whole file again, which is what made cloning the main repository download gigabytes it did not need. Splitting them out keeps the code repository small and leaves this one to grow at its own pace.

## Layout

```
images/
  anim_<name>.webm            English, light theme
  anim_<name>_dark.webm       English, dark theme
  anim_<name>_es.webm         Spanish, light theme
  anim_<name>_es_dark.webm    Spanish, dark theme
  anim_<name>_poster.webp     poster frame, one per variant
  anim_<name>.gif             GIF edition of the two English variants, for README previews
```

The documentation site and the READMEs load them from this repository's `main` branch through `raw.githubusercontent.com`. The phonometry repository records which commit of this one its clips were rendered into, in `assets.lock`, and its CI checks that every clip its code expects is present here.

## License

MIT, the same as phonometry. See `LICENSE`.
