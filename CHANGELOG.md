0.30.4 - Fix corner case regression introduced in 0.30.0 (#107)
0.30.3 - Fix spurious warnings introduced by #103 (#105)
0.30.2 - No code changes.
0.30.1 - Made weighted wildcard shorthand parsing a little more robust (#103)
0.30.0 - Removed support for python 3.7 ([#98](https://github.com/adieyal/dynamicprompts/pull/98)), wildcard files now support weights ([#97](https://github.com/adieyal/dynamicprompts/pull/97)). Also added infrastructure to return additional metadata gatherered during sampling ([#100](https://github.com/adieyal/dynamicprompts/pull/100)).
0.29.0 - Added an option to shuffle the output of the wildcard manager
0.28.0 - WildcardManager no longer deduplicates wildcards. Return a list instead of a set
0.27.1 - Late-import of jinja2 Jinja2 to work around issues with incompatible versions of Jinja2 being installed in some downstream users' environments. See [#476](https://github.com/adieyal/sd-dynamic-prompts/issues/476)
0.27.0 - Added sort and dedup properties to wildcardcard manager. Also fixed device selection for magic prompt
0.26.1 - Fixed cyclical sampling when using the RandomPromptGenerator - see [#84](https://github.com/adieyal/dynamicprompts/issues/84)
0.26.0 - Added fall-back sentence chunker when spacy is not installed
0.25.1 - Added kwargs argument to promptgenerator.generate methods
0.25.0 - Added the ability to pass random seeds into the random prompt generator for finer control over random prompt sampling. See the documentation for details.
0.24.0 - The wildcard manager now has a fallback mode that searches the entire wildcard hierarchy if it can't find a wildcard. Addresses issues like this one - [#377](https://github.com/adieyal/sd-dynamic-prompts/issues/377)
0.23.0 - Parser performance improvements - see [#77](https://github.com/adieyal/dynamicprompts/pull/77#event-8976756671). Deprecated Legacy Parser and ActionBuilder APIs have now been removed. See [#78](https://github.com/adieyal/dynamicprompts/pull/78)
0.22.0 - Make WildcardManager trees easily composable - [#74](https://github.com/adieyal/dynamicprompts/pull/74)
0.21.2 - Added missing parser config
0.21.1 - Another fix for wildcard variants, see [#358](https://github.com/adieyal/sd-dynamic-prompts/issues/358)
0.21.0 - Introduced setting variables and parameterised templates.
0.20.2 - Fixed [#354](https://github.com/adieyal/sd-dynamic-prompts/issues/354) - No values found for wildcards on Windows
0.20.1 - Fixed parsing bug #28
0.20.0 - Backward incompatible rework of the wildcard machinery, with support for JSON/YAML structured wildcard files.
0.10.6 - Fixed a bug in the parser that didn't accept whitespace before or after a variant option - see https://github.com/adieyal/sd-dynamic-prompts/issues/324
0.10.5 - Bug fix that cause RandomPromptGenerator to incorrectly handle wildcards in variants
0.10.4 - Fixed wildcard in variant syntax `{2$$__wildcard__}`
0.10.3 - Enabled batch processing for magic prompts. Higher batch size can dramatically improve prompt generation time at the expense of slightly higher memory usage.
0.10.2 - Fixed a bug where the JinjaGenerator was not ignoring whitespace
0.10.1 - Added limit_prompts to JinjaGenerator. When set to True, `.generate(..., num_images=X)` will produced at most X prompts
0.10.0 - Added added the ability to combine random and combinatorial prompts. Also added a cyclical sampler - see documentation for details
0.9.1 - WildcardManager now uses the current working directory by default if a path is not provided
0.9.0 - Configurable wildcard symbols - it's possible to change from the default __ to any arbitrary string
0.8.0 - Added syntax for changing samplers within prompt sub-trees.
0.7.1 - Fixed missing parser_config argument in CombinatorialPromptGenerator
0.7.0 - Configurable variant braces
0.6.0 - Support symlinks for the wildcards directory
0.5.0 - A major re-organisation of the parsing machinary.
0.4.3 - Allow zero repetitions in sequence commands, e.g. `{0-3$$A|B|C}`
0.4.2 - Added type information
0.4.1 - Variant separator can now be most printables e.g. `{2$$|$$A|B|C}`. This addresses [#211](https://github.com/adieyal/sd-dynamic-prompts/issues/211).
0.4.0 - Added block regex for magicprompts to remove unwanted modifiers. Many other small improvements, thanks to @akx
0.3.2 - Added LICENCE, many code improvements,security fix that prevents wildcard searches outside the wildcard directory - thanks to @akx
0.3.1 - Clean-up with thanks to @akx
0.3.0 - Added additional models to Magic Prompt
0.2.6 - Wildcards caching for speeding up complex prompts - with thanks to @RossM - see [#pr1](https://github.com/adieyal/dynamicprompts/pull/1)
0.2.5 - Fixed decimal weights in variants
0.2.4 - Fixed missing whitespace between two wildcards
0.2.3 - Fixed unlink seed from prompt which allows for a custom random number generator to be passed to the RandomGenerator
0.2.2 - Minor bug fixes
0.2.1 - Fixed a bug that cause the CombinatorialPromptGenerator to run very slowly when many wildcards were used.
0.2.0 - The parser now treats whitespace as significant in order to not ensure that the original prompt is left unaltered
0.1.19 - Added the Jinja2 generator from the SD Dynamic Prompts extension. Also fixed the Jinja2 interface to match the other generators
0.1.18 - Removed explicit dependency on pytorch, added default arguments for number of prompts produced by DummyGenerator and RandomPromptGenerator
0.1.17 - Fixed alternating words syntax [cat|dog] - pipes are only reserved inside variants. Also standardised MagicPrompt, AttentionGenerator, and FeelingLucky to use a DummyGenerator by default so that users are not forced to provide an alternative generator if one isn't needed.
0.1.16 - Changed type annotations to use classes from the typing package instead of native type in order to support python 3.7
0.1.15 - First public release
