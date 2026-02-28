# IoskeleyMono nerd font


bash script used to patch fonts
```bash
for f in ~/Downloads/IoskeleyMono-TTF-Unhinted/TTF-Unhinted/IoskeleyMono*.ttf; do 
    filename=$(basename "$f" .ttf)
    variant="${filename#IoskeleyMono-}"
    shortname="IoskNerdFontMono-${variant}"
    fontforge -script font-patcher "$f"  -c --mono --name "$shortname" --out TTF-Unhinted
done
```

### **NOTE**: the family name is `ioskNerdFontMono` becuase otherwise it will exceed 31 chars with the default font-patcher names

![Ioskeley Mono Cover](assets/SocialPreview.png)

The goal of this project is to configure the [Iosevka](https://github.com/be5invis/Iosevka) typeface to mimic the look and feel of **Berkeley Mono** as closely as possible.

It uses Iosevka's extensive build options to select character variants that replicate the distinct aesthetic of Berkeley Mono, creating a free, open-source alternative for fans of that particular style.

The name is a simple mashup: **Iosevka** + **Berkeley** = **Ioskeley**.

This repository uses GitHub Actions to automatically build the font files whenever the configuration is updated.

---

## Installation

The easiest way to get the font is to download it directly from the **Releases** page.

1. [Click here to go to the Releases Page](https://github.com/ahatem/IoskeleyMono/releases)
2. Find the latest release and download the `IoskeleyMono-Build.zip` file.
3. Unzip the file and install the fonts on your system.

---

## Preview

| Ioskeley Mono                                                                   | Berkeley Mono                                                                   |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| ![Ioskeley Mono Sample](assets/IoskeleyMono.png "Sample code in Ioskeley Mono") | ![Berkeley Mono Sample](assets/BerkeleyMono.png "Sample code in Berkeley Mono") |

> Theme used in preview: [Kintsugi Dark Flared](https://marketplace.visualstudio.com/items?itemName=ahmedhatem.kintsugi)

---

### In Action

![Ioskeley Mono in Action](assets/InAction.png "Ioskeley Mono in real use")

### Configuration Choices

This configuration uses specific character variants and custom metrics to closely match the look and feel of Berkeley Mono.

- **Custom Metrics:** The font's vertical proportions, letter spacing (`sb`), and parenthesis size have been manually adjusted. This is the key to capturing Berkeley's characteristically compact and geometric feel.
- **Distinctive Characters:** Key glyphs were chosen to match, including a **single-storey `g`**, **flat-arc parentheses `()`**, and a **two-circle `8`**.
- **Clarity and Readability:** For the best coding experience, the font uses a **dotted zero**, **open-contour `6` and `9`**, and sharp, **square punctuation**.
- **High Underscore:** The underscore character is raised to ensure it is clearly visible and never blends with the line below.

For a complete list of all choices made to match Berkeley Mono, see the [`private-build-plans.toml`](./private-build-plans.toml) file.

---

### License & Credits

**Credits**: Ioskeley Mono is a custom configuration of the Iosevka typeface. All credit for the original design and build system goes to Belleve Invis and the Iosevka contributors.

Because this is a derivative of Iosevka, it is licensed under the same **SIL Open Font License 1.1**. See the `LICENSE` file for full details.
