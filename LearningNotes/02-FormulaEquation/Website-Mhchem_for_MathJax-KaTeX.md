# <center>mhchem for MathJax/KaTeX</center>

原文网址：https://mhchem.github.io/MathJax-mhchem/

----



*mhchem* is a tool for writing beautiful chemical equations easily.

This is the manual for mhchem’s input syntax. It covers version 3.3 of both, **mhchem for MathJax** (a third-party extension for [MathJax](https://mathjax.org/)) and **mhchem for KaTeX** (a third-party extension for [KaTeX](https://katex.org/)).

----

## configuration of mathjax

For information on how to make the `\ce` command available, see the official [MathJax docs](http://docs.mathjax.org/en/latest/configuration.html#using-in-line-configuration-options). In short, use this config to load the extension:

```
MathJax.Ajax.config.path["mhchem"] =
  "https://cdnjs.cloudflare.com/ajax/libs/mathjax-mhchem/3.3.2";
MathJax.Hub.Config({
  TeX: {
    extensions: ["[mhchem]/mhchem.js"]
  }
});
```

## configuration of katex

For information on how to make the `\ce` command available, see the [KaTeX docs](https://github.com/KaTeX/KaTeX/blob/master/contrib/mhchem/README.md). Just write this line into your pages’s ``, after the call to `katex.js`:

```
<script src="https://cdn.jsdelivr.net/npm/katex@0.10.1/dist/contrib/mhchem.min.js"></script>
```

## chemical equations (ce)

$\ce{CO2 + C -> 2 CO}$

```
$\ce{CO2 + C -> 2 CO}$
```

 

$\ce{Hg^2+ ->[I-] HgI2 ->[I-] [Hg^{II}I4]^2-}$

```
$\ce{Hg^2+ ->[I-] HgI2 ->[I-] [Hg^{II}I4]^2-}$
```

 

$C_p[\ce{H2O(l)}] = \pu{75.3 J // mol K}$

```
$C_p[\ce{H2O(l)}] = \pu{75.3 J // mol K}$
```



## chemical formulae

$\ce{H2O}$

```
$\ce{H2O}$
```

 

$\ce{Sb2O3}$

```
$\ce{Sb2O3}$
```



## charges

$\ce{H+}$

```
$\ce{H+}$
```

 

$\ce{CrO4^2-}$

```
$\ce{CrO4^2-}$
```

 

$\ce{[AgCl2]-}$

```
$\ce{[AgCl2]-}$
```

 

$\ce{Y^99+}$

```
$\ce{Y^99+}$
```

 

$\ce{Y^{99+}}$

```
$\ce{Y^{99+}}$
```



## stoichiometric numbers

$\ce{2 H2O}$

```
$\ce{2 H2O}$
```

 

$\ce{2H2O}$

```
$\ce{2H2O}$
```

 

$\ce{0.5 H2O}$

```
$\ce{0.5 H2O}$
```

 

$\ce{1/2 H2O}$

```
$\ce{1/2 H2O}$
```

 

$\ce{(1/2) H2O}$

```
$\ce{(1/2) H2O}$
```

IUPAC Green Book

 

$\ce{$n$ H2O}$

```
$\ce{$n$ H2O}$
```



## isotopes

$\ce{^{227}_{90}Th+}$

```
$\ce{^{227}_{90}Th+}$
```

 

$\ce{^227_90Th+}$

```
$\ce{^227_90Th+}$
```

 

$\ce{^{0}_{-1}n^{-}}$

```
$\ce{^{0}_{-1}n^{-}}$
```

 

$\ce{^0_-1n-}$

```
$\ce{^0_-1n-}$
```



It might be ambiguous whether a superscript belongs to the left or right element. There is automatic detection (digits only = mass number = belongs to right side), but to make sure you can type `{}` as a separator.

$\ce{H{}^3HO}$

```
$\ce{H{}^3HO}$
```

 

$\ce{H^3HO}$

```
$\ce{H^3HO}$
```



## reaction arrows

$\ce{A -> B}$

```
$\ce{A -> B}$
```

 

$\ce{A <- B}$

```
$\ce{A <- B}$
```

 

$\ce{A <-> B}$

```
$\ce{A <-> B}$
```

not to be used according to IUPAC and ACS

 

$\ce{A <--> B}$

```
$\ce{A <--> B}$
```

 

$\ce{A <=> B}$

```
$\ce{A <=> B}$
```

 

$\ce{A <=>> B}$

```
$\ce{A <=>> B}$
```

 

$\ce{A <<=> B}$

```
$\ce{A <<=> B}$
```



Each arrow can take two optional arguments: one for above and one for below. The arrow arguments use the same input syntax as the `\ce` command.

$\ce{A ->[H2O] B}$

```
$\ce{A ->[H2O] B}$
```

chemistry

 

$\ce{A ->[{text above}][{text below}] B}$

```
$\ce{A ->[{text above}][{text below}] B}$
```

upright text, see below

 

$\ce{A ->[$x$][$x_i$] B}$

```
$\ce{A ->[$x$][$x_i$] B}$
```

italic math, see below



Unfortunately, MathJax [cannot stretch](https://github.com/mathjax/MathJax/issues/1491) `<-->`, `<=>`, `<=>>` and `<<=>` arrows properly. All the arrows do stretch in LaTeX and KaTeX.

## parentheses, brackets, braces

Use parentheses `( )` and brackets `[ ]` normally. Write braces as `\{ \}`.

$\ce{(NH4)2S}$

```
$\ce{(NH4)2S}$
```

 

$\ce{[\{(X2)3\}2]^3+}$

```
$\ce{[\{(X2)3\}2]^3+}$
```



For large parentheses, `\left` and `\right` macros need to be in the same math environment, so you might have to put `\ce` into `$` into `\ce`, but that’s fine.

$\ce{CH4 + 2 $\left( \ce{O2 + 79/21 N2} \right)$}$

```
$\ce{CH4 + 2 $\left( \ce{O2 + 79/21 N2} \right)$}$
```



## states of aggregation(not fully supported for latex yet)

$\ce{H2(aq)}$

```
$\ce{H2(aq)}$
```

IUPAC recommendation

 

$\ce{CO3^2-_{(aq)}}$

```
$\ce{CO3^2-_{(aq)}}$
```

not IUPAC-conform, not ACS-conform

 

$\ce{NaOH(aq,$\infty$)}$

```
$\ce{NaOH(aq,$\infty$)}$
```



## crystal systems(not fully supported for latex yet)

$\ce{ZnS($c$)}$

```
$\ce{ZnS($c$)}$
```

 

$\ce{ZnS(\ca$c$)}$

```
$\ce{ZnS(\ca$c$)}$
```

Circa, tilde



## variables like *x*, *n*, 2*n*+1

Typographical conventions say that variables are typeset in an italic font, while other entities (like chemical elements) are typeset in an upright font. mhchem tries to recognize common patterns and use the correct (italic) font, like the *x* and *n* in the following examples.

$\ce{NO_x}$

```
$\ce{NO_x}$
```

 

$\ce{Fe^n+}$

```
$\ce{Fe^n+}$
```

 

$\ce{x Na(NH4)HPO4 ->[\Delta] (NaPO3)_x + x NH3 ^ + x H2O}$

```
$\ce{x Na(NH4)HPO4 ->[\Delta] (NaPO3)_x + x NH3 ^ + x H2O}$
```



If a more complex term is not properly recognized, you can switch to math mode (= italics) explicitly.

## greek characters

Just write `\alpha` etc. Typographical conventions say that variables are typeset in an italic font, while other entities (like chemical elements) are typeset in an upright font. In the following examples, the Greek character is *not* a variable that stands for a number, therefore an upright font *should* be used. Unfortunately, neither MathJax nor KaTeX [support](https://github.com/mathjax/mathjax-docs/wiki/Non-italic-(upright)-greek-letters) upright lower-case Greek characters.

$\ce{\mu-Cl}$

```
$\ce{\mu-Cl}$
```

 

$\ce{[Pt(\eta^2-C2H4)Cl3]-}$

```
$\ce{[Pt(\eta^2-C2H4)Cl3]-}$
```



Spaces after a greek character are ignored. This is standard TeX behavior. Insert `{}` to get the desired output.

$\ce{\beta +}$

```
$\ce{\beta +}$
```

 

$\ce{^40_18Ar + \gamma{} + \nu_e}$

```
$\ce{^40_18Ar + \gamma{} + \nu_e}$
```



## (italic) math

By using `$...$` you can escape to math mode.

$\ce{NaOH(aq,$\infty$)}$

```
$\ce{NaOH(aq,$\infty$)}$
```

 

$\ce{Fe(CN)_{$\frac{6}{2}$}}$

```
$\ce{Fe(CN)_{$\frac{6}{2}$}}$
```

 

$\ce{X_{$i$}^{$x$}}$

```
$\ce{X_{$i$}^{$x$}}$
```

 

$\ce{X_$i$^$x$}$

```
$\ce{X_$i$^$x$}$
```



(With *mhchem for LaTex* there is a difference between `$...$` and `${...}$`. But because neither MathJax nor KaTeX have a text font, both inputs will yield identical results there.)

## italic text

With the same mechanism you can mimic an italic text font.

$\ce{$cis${-}[PtCl2(NH3)2]}$

```
$\ce{$cis${-}[PtCl2(NH3)2]}$
```

 

$\ce{CuS($hP12$)}$

```
$\ce{CuS($hP12$)}$
```

Pearson Symbol



Spaces will be ignored. Use a `~` when you need to typeset a space.

## upright text, escape parsing

Enclose upright text with `{...}`.

$\ce{{Gluconic Acid} + H2O2}$

```
$\ce{{Gluconic Acid} + H2O2}$
```

 

$\ce{X_{{red}}}$

```
$\ce{X_{{red}}}$
```



With the same mechanism, you can escape parsing, for instance if you need a simple hyphen (that should not become a bond).

$\ce{{(+)}_589{-}[Co(en)3]Cl3}$

```
$\ce{{(+)}_589{-}[Co(en)3]Cl3}$
```



## bonds

$\ce{C6H5-CHO}$

```
$\ce{C6H5-CHO}$
```

 

$\ce{A-B=C#D}$

```
$\ce{A-B=C#D}$
```



mhchem tries to differentiate whether `\ce{-}` should be a bond, a charge or a hyphen.

$\ce{A\bond{-}B\bond{=}C\bond{#}D}$

```
$\ce{A\bond{-}B\bond{=}C\bond{#}D}$
```

 

$\ce{A\bond{1}B\bond{2}C\bond{3}D}$

```
$\ce{A\bond{1}B\bond{2}C\bond{3}D}$
```

 

$\ce{A\bond{~}B\bond{~-}C}$

```
$\ce{A\bond{~}B\bond{~-}C}$
```

 

$\ce{A\bond{~--}B\bond{~=}C\bond{-~-}D}$

```
$\ce{A\bond{~--}B\bond{~=}C\bond{-~-}D}$
```

 

$\ce{A\bond{...}B\bond{....}C}$

```
$\ce{A\bond{...}B\bond{....}C}$
```

 

$\ce{A\bond{->}B\bond{<-}C}$

```
$\ce{A\bond{->}B\bond{<-}C}$
```



## addition compounds

$\ce{KCr(SO4)2*12H2O}$

```
$\ce{KCr(SO4)2*12H2O}$
```

 

$\ce{KCr(SO4)2.12H2O}$

```
$\ce{KCr(SO4)2.12H2O}$
```

 

$\ce{KCr(SO4)2 * 12 H2O}$

```
$\ce{KCr(SO4)2 * 12 H2O}$
```



## oxidation states

$\ce{Fe^{II}Fe^{III}2O4}$

```
$\ce{Fe^{II}Fe^{III}2O4}$
```



## unpaired electrons, radical dots

$\ce{OCO^{.-}}$

```
$\ce{OCO^{.-}}$
```

 

$\ce{NO^{(2.)-}}$

```
$\ce{NO^{(2.)-}}$
```



## kröger-vink notation(not supported for latex yet)

$\ce{Li^x_{Li,1-2x}Mg^._{Li,x}$V$'_{Li,x}Cl^x_{Cl}}$

```
$\ce{Li^x_{Li,1-2x}Mg^._{Li,x}$V$'_{Li,x}Cl^x_{Cl}}$
```

 

$\ce{O''_{i,x}}$

```
$\ce{O''_{i,x}}$
```

 

$\ce{M^{..}_i}$

```
$\ce{M^{..}_i}$
```

 

$\ce{$V$^{4'}_{Ti}}$

```
$\ce{$V$^{4'}_{Ti}}$
```

 

$\ce{V_{V,1}C_{C,0.8}$V$_{C,0.2}}$

```
$\ce{V_{V,1}C_{C,0.8}$V$_{C,0.2}}$
```

upright V = Vanadium, italic V = vacancy



## equation operators

$\ce{A + B}$

```
$\ce{A + B}$
```

 

$\ce{A - B}$

```
$\ce{A - B}$
```

not to be confused with bonds

 

$\ce{A = B}$

```
$\ce{A = B}$
```

not to be confused with bonds

 

$\ce{A \pm B}$

```
$\ce{A \pm B}$
```



## precipitate and gas

$\ce{SO4^2- + Ba^2+ -> BaSO4 v}$

```
$\ce{SO4^2- + Ba^2+ -> BaSO4 v}$
```

 

$\ce{A v B (v) -> B ^ B (^)}$

```
$\ce{A v B (v) -> B ^ B (^)}$
```



## other symbols and shortcuts(not fully supported for latex yet)

$\ce{NO^*}$

```
$\ce{NO^*}$
```

Excited state

 

$\ce{1s^2-N}$

```
$\ce{1s^2-N}$
```

Orbitals

 

$\ce{n-Pr}$

```
$\ce{n-Pr}$
```

 

$\ce{iPr}$

```
$\ce{iPr}$
```

 

$\ce{\ca Fe}$

```
$\ce{\ca Fe}$
```

 

$\ce{A, B, C; F}$

```
$\ce{A, B, C; F}$
```

Punctuation

 

$\ce{{and others}}$

```
$\ce{{and others}}$
```



## complex examples

$\ce{Zn^2+  <=>[+ 2OH-][+ 2H+]  $\underset{\text{amphoteres Hydroxid}}{\ce{Zn(OH)2 v}}$  <=>[+ 2OH-][+ 2H+]  $\underset{\text{Hydroxozikat}}{\ce{[Zn(OH)4]^2-}}$}$

```
$\ce{Zn^2+  <=>[+ 2OH-][+ 2H+]  $\underset{\text{amphoteres Hydroxid}}{\ce{Zn(OH)2 v}}$  <=>[+ 2OH-][+ 2H+]  $\underset{\text{Hydroxozikat}}{\ce{[Zn(OH)4]^2-}}$}$
```

 

$\ce{$K = \frac{[\ce{Hg^2+}][\ce{Hg}]}{[\ce{Hg2^2+}]}$}$

```
$\ce{$K = \frac{[\ce{Hg^2+}][\ce{Hg}]}{[\ce{Hg2^2+}]}$}$
```

 

$\ce{$K = \ce{\frac{[Hg^2+][Hg]}{[Hg2^2+]}}$}$

```
$\ce{$K = \ce{\frac{[Hg^2+][Hg]}{[Hg2^2+]}}$}$
```

 

$\ce{Hg^2+ ->[I-]  $\underset{\mathrm{red}}{\ce{HgI2}}$  ->[I-]  $\underset{\mathrm{red}}{\ce{[Hg^{II}I4]^2-}}$}$

```
$\ce{Hg^2+ ->[I-]  $\underset{\mathrm{red}}{\ce{HgI2}}$  ->[I-]  $\underset{\mathrm{red}}{\ce{[Hg^{II}I4]^2-}}$}$
```





## physical units (pu)(mathjax or katex only, not for latex)

$\pu{123 kJ}$

```
$\pu{123 kJ}$
```

 

$\pu{123 mm2}$

```
$\pu{123 mm2}$
```



There are two conventions regarding the multiplication within units.

$\pu{123 J s}$

```
$\pu{123 J s}$
```

 

$\pu{123 J*s}$

```
$\pu{123 J*s}$
```



There are four conventions regarding divisions.

$\pu{123 kJ/mol}$

```
$\pu{123 kJ/mol}$
```

 

$\pu{123 kJ//mol}$

```
$\pu{123 kJ//mol}$
```

 

$\pu{123 kJ mol-1}$

```
$\pu{123 kJ mol-1}$
```

 

$\pu{123 kJ*mol-1}$

```
$\pu{123 kJ*mol-1}$
```



There are four main conventions for writing numbers in scientific notation.

$\pu{1.2e3 kJ}$

```
$\pu{1.2e3 kJ}$
```

 

$\pu{1,2e3 kJ}$

```
$\pu{1,2e3 kJ}$
```

 

$\pu{1.2E3 kJ}$

```
$\pu{1.2E3 kJ}$
```

 

$\pu{1,2E3 kJ}$

```
$\pu{1,2E3 kJ}$
```



If you need more control than is offered here, take a look at the siunitx extension.

## compatibility with mhchem for latex

Most of these examples work identically for *mhchem for MathJax*, *mhchem for KaTeX* and *mhchem and LaTeX*. Exceptions are indicated. Also, some edge-cases may render differently. I will try to minimize the differences in the future. But even then, the MathJax and KaTeX versions will always be more tolerant of sloppy input (e.g. a missing space) than *mhchem for LaTeX*.

## contact and support

If you have a question and cannot find an answer—neither here nor with a web search—then

- mail me ([mhchem@MartinHensel.de](mailto:mhchem@MartinHensel.de)) or
- create an GitHub issue (https://github.com/mhchem/MathJax-mhchem/issues) or
- ask at StackExchange (http://meta.chemistry.stackexchange.com/) with the mhchem tag.

## test drive

$\ce{H2O}$

```
\ce{H2O}
```

