# semikeys

Type `;ohm` and get Ω. Type `;12` and get ½. No more copy and paste.

semikeys is a list of macOS Text Replacements for the symbols and emoji that
are not on your keyboard. Every shortcut starts with a semicolon, so nothing
fires while you type normally. Replacements sync to your iPhone and iPad
through iCloud, so the same shortcuts work everywhere.

No app. No background process. One file.

## Install

1. Download `semikeys.plist`.
2. Open **System Settings > Keyboard > Text Replacements**.
3. Drag `semikeys.plist` into the list.

That's it. Your existing replacements are kept; these are added alongside them.

To remove them, select the entries in the same window and press the minus button.

## Shortcuts

Type the shortcut, then a space or punctuation.

| Shortcut | Result | | Shortcut | Result |
|---|---|---|---|---|
| `;ohm` | Ω | | `;sq` | ² |
| `;mu` | µ | | `;cube` | ³ |
| `;12` | ½ | | `;sqrt` | √ |
| `;14` | ¼ | | `;pi` | π |
| `;34` | ¾ | | `;delta` | Δ |
| `;13` | ⅓ | | `;->` | → |
| `;deg` | ° | | `;<-` | ← |
| `;degf` | °F | | `;check` | ✓ |
| `;degc` | °C | | `;tm` | ™ |
| `;pm` | ± | | `;c` | © |
| `;x` | × | | `;up` | 👍 |
| `;div` | ÷ | | `;lol` | 😂 |
| `;approx` | ≈ | | `;pray` | 🙏 |
| `;ne` | ≠ | | `;mad` | 😡 |
| `;le` | ≤ | | `;fire` | 🔥 |
| `;ge` | ≥ | | `;done` | ✅ |
| | | | `;rocket` | 🚀 |
| | | | `;swim` | 🏊 |

## Make your own

Select any replacements in System Settings and drag them to your desktop. macOS
exports them in the same format as `semikeys.plist`, so you can edit the file in
any text editor and drag it back in.

Each entry looks like this:

```xml
<dict><key>phrase</key><string>Ω</string><key>shortcut</key><string>;ohm</string></dict>
```

## Contributing

Pull requests are welcome. The bar is simple: would most people reach for this
symbol more than once?

To add a shortcut:

1. Add one line to `semikeys.plist` in the matching group (math, units, arrows,
   emoji, and so on).
2. Add the same shortcut to the table in this README.
3. Check the file still parses: `plutil -lint semikeys.plist`
4. Open a pull request with a one-line note on why it earns a spot.

House rules:

- **Start with `;`.** Always. That is the whole safety model.
- **Lowercase, short, guessable.** `;deg` beats `;degreesymbol`. If you have to
  look it up, it is the wrong shortcut.
- **No collisions.** Search the file before adding. One shortcut, one result.
- **Escape XML.** Write `<` as `&lt;`, `>` as `&gt;`, and `&` as `&amp;`
  inside the plist.
- **Keep it KISS.** No scripts, no build step, no dependencies. If it needs
  more than one file to work, it does not belong here.

Found a shortcut that fires by accident or a symbol that renders wrong? Open an
issue.

## License

MIT. See [LICENSE](LICENSE).
