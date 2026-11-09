# Flutter portfolio

A Flutter web portfolio prototype displaying the **Lucky Labrador** profile. Visitors can read an introduction and About section, follow social links, and open a contact dialog. This repository preserves the portfolio experiment previously named `Labrador`; its Dart package still uses the original internal name `term_summary`.

[GitHub Pages portfolio](https://neonat.github.io/flutter-portfolio/) · [Application source](lib/main.dart) · [Reusable widgets](lib/components.dart)

## What is implemented

- A dark single-page portfolio with a profile image, introduction, About text and footer.
- Smooth scrolling to the About section.
- Reusable image, heading, navigation and social-link widgets.
- Browser links to the profiles configured in the source, including [LoKhyeHe on GitHub](https://github.com/LoKhyeHe).
- An email composition dialog that opens a `mailto:` URL. The recipient is currently empty in the page configuration.

Profile content currently names Lucky Labrador and links LoKhyeHe. Customise those entries in `lib/main.dart` when reusing the page.

## Run in a browser

Use a Flutter SDK containing **Dart 3.6 or later compatible with the `^3.6.0` constraint**. Chrome must be installed for the device command below.

```sh
git clone https://github.com/Neonat/flutter-portfolio.git
cd flutter-portfolio
flutter pub get
flutter run -d chrome
```

The implementation imports `dart:html` for browser links, so the current implementation targets browsers. Native-platform folders are generated scaffolding, not evidence of a working native portfolio.

## Project layout and builds

| Path | Purpose |
| --- | --- |
| [lib/main.dart](lib/main.dart) | Portfolio content, page layout and scroll targets |
| [lib/components.dart](lib/components.dart) | Shared visual widgets, external links and email dialog |
| [lib/assets/](lib/assets/) | Profile and supporting images declared in the asset manifest |
| [pubspec.yaml](pubspec.yaml) | Dart constraint and Flutter dependencies |
| [web/](web/) | Web entry template |
| [docs/](docs/) | Previously generated static web build for hosting |

For a GitHub Pages project site at the renamed repository path:

```sh
flutter build web --base-href /flutter-portfolio/
```

Flutter writes fresh output to `build/web/`. The checked-in `docs/` is a separate generated snapshot; rebuilding does not automatically replace it. Serve a build over HTTP rather than opening its HTML directly.

## Prototype status

The **Experience** and **Projects** navigation items have no rendered target sections in the current page, the theme icon has an empty handler, and the contact recipient is unset. Project-card assets and helper widgets are present, but the page does not yet show a finished project or experience catalogue. Some web metadata still carries the original `term_summary` starter name.

This README describes the source as preserved; it does not claim working native builds, completed contact delivery or a fully populated portfolio.
