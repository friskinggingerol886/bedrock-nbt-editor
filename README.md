# Bedrock NBT Editor

[![GitHub Pages](https://img.shields.io/badge/demo-live-brightgreen?style=flat-square)](https://w1zardz.github.io/bedrock-nbt-editor/)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](LICENSE)

**Online NBT editor for Minecraft Bedrock Edition level.dat files.** Built for the PocketMine-MP community.

## The Problem

When you duplicate a Bedrock world by copying its folder, the internal `LevelName` tag inside `level.dat` doesn't change — it still references the original world name. This causes confusing bugs in PocketMine-MP and MCPE/MCBE. This tool lets you fix that (and edit any other NBT tag) directly in your browser.

## Features

- Full Bedrock NBT support — all 13 tag types including TAG_Long (BigInt)
- Parses Bedrock `level.dat` format (8-byte LE header + LE NBT payload)
- Tree view editor with collapsible compound/list nodes
- Inline value editing — click any value to change it
- Add and remove tags
- Download modified file with correct header
- Drag & drop or file picker upload
- Mobile-first, touch-friendly UI (44px+ tap targets)
- Dark theme, no frameworks, zero dependencies
- Works 100% client-side — your files never leave your browser

## How to Use

1. Open [the editor](https://w1zardz.github.io/bedrock-nbt-editor/)
2. Drag & drop your `level.dat` file (or click to browse)
3. Expand the tree to find the tag you want to edit (e.g. `LevelName`)
4. Click the value to edit it inline
5. Click **Save & Download** to get the modified file

## Technical Details

- Bedrock `level.dat` has an 8-byte header: 4 bytes LE version integer + 4 bytes LE payload length
- All NBT data is little-endian (unlike Java Edition which is big-endian)
- TAG_Long values are handled with JavaScript BigInt for full 64-bit precision
- The editor recalculates the payload length on save

## Supported Tag Types

| ID | Tag Type | Description |
|----|----------|-------------|
| 0 | TAG_End | Marks end of compound |
| 1 | TAG_Byte | Signed 8-bit integer |
| 2 | TAG_Short | Signed 16-bit LE integer |
| 3 | TAG_Int | Signed 32-bit LE integer |
| 4 | TAG_Long | Signed 64-bit LE integer (BigInt) |
| 5 | TAG_Float | 32-bit LE IEEE 754 float |
| 6 | TAG_Double | 64-bit LE IEEE 754 double |
| 7 | TAG_Byte_Array | Length-prefixed byte array |
| 8 | TAG_String | Length-prefixed UTF-8 string |
| 9 | TAG_List | Typed list of tags |
| 10 | TAG_Compound | Named collection of tags |
| 11 | TAG_Int_Array | Length-prefixed int array |
| 12 | TAG_Long_Array | Length-prefixed long array |

## Keywords

PocketMine-MP, PMMP, PocketMine, Bedrock Edition, MCPE, MCBE, level.dat, NBT editor, world editor, level name editor, Minecraft Bedrock tools, NBT viewer, online NBT editor

## License

[MIT](LICENSE)
