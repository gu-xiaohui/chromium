# ![Logo](chrome/app/theme/cradle/product_logo_64.png) Cradle Browser

Cradle is a custom web browser built on the open-source Chromium project. It aims to provide a fast, secure, and user-friendly browsing experience while maintaining the stability and performance of the Chromium foundation.

## About Cradle

Cradle Browser is based on Chromium, the same open-source project that powers Google Chrome. By building on this solid foundation, Cradle inherits:

- **Speed**: Lightning-fast page loads and JavaScript execution
- **Security**: Built-in protection against malware and phishing
- **Stability**: Rock-solid browsing experience
- **Modern Web Standards**: Full support for the latest web technologies

## Building Cradle

### Prerequisites

Follow the standard [Chromium build instructions](docs/get_the_code.md) to set up your development environment.

### Building with Cradle Branding

To build Cradle Browser instead of Chromium, add the following GN argument:

```bash
gn gen out/Cradle --args='is_cradle_branded=true'
```

You can also combine it with other build options:

```bash
gn gen out/Cradle --args='is_cradle_branded=true is_debug=false target_cpu="x64"'
```

Then build as usual:

```bash
autoninja -C out/Cradle chrome
```

### Available Build Arguments

| Argument | Default | Description |
|----------|---------|-------------|
| `is_cradle_branded` | `false` | Enable Cradle Browser branding |
| `is_debug` | `true` | Build in debug mode |
| `target_cpu` | current | Target CPU architecture (x64, x86, arm, arm64) |

## Branding

Cradle Browser has its own branding located in:

- **Theme assets**: `chrome/app/theme/cradle/`
- **String resources**: `chrome/app/cradle_strings.grd`
- **Branding configuration**: `chrome/app/theme/cradle/BRANDING`

### Customizing Branding

To customize the Cradle branding:

1. Replace logo files in `chrome/app/theme/cradle/` with your own designs
2. Update the `BRANDING` file with your company/project information
3. Modify `chrome/app/cradle_strings.grd` to update user-facing strings

## Directory Structure

```
cradle-browser/
├── chrome/
│   └── app/
│       ├── theme/
│       │   └── cradle/          # Cradle branding assets
│       │       ├── BRANDING     # Branding metadata
│       │       ├── linux/       # Linux-specific icons
│       │       ├── mac/         # macOS-specific icons
│       │       ├── win/         # Windows-specific icons
│       │       └── product_logo_*.png
│       └── cradle_strings.grd   # Cradle-specific strings
├── build/
│   └── config/
│       └── chrome_build.gni     # Build configuration with is_cradle_branded flag
└── README_CRADLE.md             # This file
```

## Platform Support

Cradle Browser supports the same platforms as Chromium:

- **Windows** 10 and later
- **macOS** 12 (Monterey) and later
- **Linux** (various distributions)
- **Android** (planned)
- **ChromeOS** (experimental)

## Contributing

Contributions to Cradle Browser are welcome! Please follow the standard Chromium contribution guidelines and coding standards.

## License

Cradle Browser is based on Chromium and inherits its BSD-style license. See [LICENSE](LICENSE) for details.

## Links

- [Chromium Project](https://www.chromium.org/)
- [Chromium Source Code](https://chromium.googlesource.com/chromium/src/)
- [Chromium Documentation](docs/README.md)

---

*Cradle Browser - A modern browser for the modern web.*
