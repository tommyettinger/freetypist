# freetypist

Provides FreeType font loading for TextraTypist.

You can load anything FWSkin (from TextraTypist) can load, such as .fnt and (optionally compressed) Structured JSON
files from FontWriter, as well as anything FreeTypeSkin (from Stripe) can load, such as FreeType font config. This also
will load TextraTypist's Styles.Whatever types when it loads the corresponding scene2d.ui style.

This depends on FreeType, so you must have the appropriate platform dependencies for that, if you don't already. It
also, naturally, depends on TextraTypist. It has no other dependencies of its own.

# Dependency

Using Maven Central:

```gradle
implementation 'com.github.tommyettinger:freetypist:1.1.0'
```

Using JitPack:
(Instead of `93e338da1b`, [you can use any recent commit listed here](https://jitpack.io/#tommyettinger/freetypist)
under Commits.)

```gradle
implementation 'com.github.tommyettinger:freetypist:93e338da1b'
```

You could also just copy the two source files,
[FreeTypistSkin.java](src/main/java/com/github/tommyettinger/freetypist/FreeTypistSkin.java)
and
[FreeTypistSkinLoader.java](src/main/java/com/github/tommyettinger/freetypist/FreeTypistSkinLoader.java),
into your own project, which is probably the easiest route. This is what TextraTypist does for its tests. You
still will need the FreeType dependencies, including its platform dependencies.

# Quirks

You might have to add or remove padding from Table `Cell`s/`Container`s that have `TextraLabel`s or `TypingLabel`s in
them, if the dimensions of that cell or container are determined by the label. In particular, using
`someCell.padBottom(-myFont.descent);` may be all you need, and this may only be needed for some FreeType fonts. It
looks like FreeType handles some positions differently from FontWriter, which is what the .dat fonts distributed in
TextraTypist's `KnownFonts` used most of the time. 

# History

This project was previously a subproject of the [textratypist](https://github.com/tommyettinger/textratypist) repo, but
with the way that that was structured, I had some real issues when releasing. That's why the TextraTypist release 1.0.0
corresponds to FreeTypist 1.0.1 . FreeTypist was moved to its own repo because it doesn't actually depend on the latest
TextraTypist commit anyway, and it can reasonably be its own small project.

# License

[Apache 2.0](LICENSE), the same as TextraTypist.


