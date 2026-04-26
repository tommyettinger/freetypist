# freetypist

Provides FreeType font loading for TextraTypist.

You can load anything FWSkin (from TextraTypist) can load, such as .fnt and (optionally compressed) Structured JSON
files from FontWriter, as well as anything FreeTypeSkin (from Stripe) can load, such as FreeType font config. This also
will load TextraTypist's `Styles.Whatever` types when it loads the corresponding scene2d.ui style. Importantly, this can
load both the .dat and .fnt files distributed in TextraTypist's `knownFonts/` folder.

This depends on FreeType, so you must have the appropriate platform dependencies for that, if you don't already. It
also, naturally, depends on TextraTypist. It has no other dependencies of its own.

Versions here are linked to TextraTypist versions, so version `2.2.16.0` uses TextraTypist `2.2.16`, with a bugfix or
other patch applied to append `.0`. In the case of the earlier `1.1.0.1`, that patch allows SelectBoxStyle to be read
in, and fixed some optional properties that other styles may have in a Skin JSON file. That version still depends on the
same version of TextraTypist, `1.1.0`, as the release before it. When a new TextraTypist version comes out, such as
`2.2.17`, then the corresponding version of FreeTypist would be `2.2.17.0`.

# Dependency

Using Maven Central:

```gradle
implementation 'com.github.tommyettinger:freetypist:2.2.16.0'
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

# History

This project was previously a subproject of the [textratypist](https://github.com/tommyettinger/textratypist) repo, but
with the way that that was structured, I had some real issues when releasing. That's why the release numbering was
sketchy for a while early on. FreeTypist was moved to its own repo because it doesn't actually depend on the latest
TextraTypist commit anyway, and it can reasonably be its own small project.

The code here has been mostly unchanged except to update TextraTypist versions, but when that also updates libGDX,
sometimes there are other changes involved. There were also some changes to how sizing works in version 2.2.2.0 here,
matching changes in TextraTypist 2.2.2 for all of its Skin types. Version 2.2.4.0 included some fixes for styles.

# License

[Apache 2.0](LICENSE), the same as TextraTypist.


