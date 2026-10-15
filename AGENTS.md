# Project editing guide

## Purpose

This repository is an English, beginner-friendly crypto education book. It teaches readers to understand products, charts, indicators, execution, risk, and research before they trade.

## Writing style

- Write in clear, natural English for a beginner who may have lost money.
- Explain a term before using it as part of an argument.
- Prefer a concrete BTC example over an abstract definition.
- Separate observation, interpretation, and trading decision.
- State limits and uncertainty whenever an indicator or pattern is introduced.
- Avoid hype, guaranteed predictions, signal-selling language, and unnecessary jargon.
- Keep the tone calm, practical, and respectful.
- Do not add Chinese-language words or labels to book content, captions, tables, filenames, or headings. Translate regional terminology into English and explain the equivalent English label.

## Indicator explanations

For each indicator, explain:

1. What the calculation measures.
2. What a reader can observe on a chart.
3. A realistic BTC example.
4. When the observation may be useful.
5. The main failure mode or limitation.

Do not treat multiple indicators derived from the same price data as independent confirmation. Explain platform-specific naming and formulas when they differ.

## Images

- Use one image for one concept when possible.
- Do not repeat the same screenshot in several sections unless the second use adds a clearly different analysis.
- Keep supplied BTC screenshots and explain what is visible in the image.
- Check every relative image link from the location of the Markdown file.
- Prefer PNG/JPEG screenshots for supplied app examples and SVG diagrams for simple conceptual illustrations.

## Structure

- Keep the main chapters sequential and update `README.md` when files move or are renamed.
- Put optional deep dives in `book/advanced/` rather than creating an unplanned numbered chapter.
- Keep practical exercises out of articles unless the user explicitly requests them.
- Preserve useful references from official Binance, TradingView, and primary documentation when rewriting.

## Verification

Before committing:

- Run `git diff --check`.
- Search for non-English text when the English-only requirement applies.
- Check that all referenced local images exist.
- Read the changed section in context to remove repeated explanations.
- Commit with a short, descriptive message and push to `main` when requested.
