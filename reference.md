# Mind Map Skill Reference

## Purpose

Generate a PNG mind map from Markdown text.

## Layout modes

- `free`: Auto-select layout by complexity.
- `center`: Radial layout around root node.
- `horizontal`: Left-to-right hierarchical layout.

## Free mode decision rule

- Select `center` when `depth <= 4` and `total_nodes <= 100`.
- Otherwise select `horizontal`.

## Runner script

Main execution entry:

```bash
python mind_map/scripts/run_mind_map.py --layout <free|center|horizontal> --input "<markdown-or-file>" --output-dir mind_map_output

If your skill directory is named `mind-map-skill`, run:

```bash
python mind-map-skill/scripts/run_mind_map.py --layout <free|center|horizontal> --input "<markdown-or-file>" --output-dir mind_map_output
```
```

Default behavior writes outputs to a date subfolder:

- `mind_map_output/YYYY-MM-DD/`

To disable date grouping, pass `--flat-output`.

## Output

- PNG file path
- Saved input markdown path (same output dated folder)
- Selected layout
- Tree depth
- Total node count

## Errors

- Empty markdown input: returns validation error.
- Unsupported layout value: returns validation error.

## Metadata

- Author: [@sawyer-shi](https://github.com/sawyer-shi)
- Email: sawyer36@foxmail.com
- License: Apache License 2.0
