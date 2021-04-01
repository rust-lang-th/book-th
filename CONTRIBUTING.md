# Contributing

Welcome to Rustlang book Thai translation project. Contributions to the project are always very welcome! 🙏🏽  

## Licensing

This repository is under the same license as the official book and Rust itself, MIT/Apache2. You can find the full text of each license in the `LICENSE-*` files in this repository.

## Code of Conduct

The Rust project has [a code of conduct](http://rust-lang.org/policies/code-of-conduct)
that governs all sub-projects, including this one. Please respect it!

## Guideline
Have any questions? Feel free to ask in [our discussions](https://github.com/rust-lang-th/book-th/discussions) place. We're here to help!

## Translation
1. Please translate one chapter at a time from top to bottom. Jumping the translation between the context in the same chapter will make the other translator lose the context in the original language around the part that not translate yet.
3. When do the translation, please change only the texts and keep the style as same as the original version.
4. Keep transliteration words low, but if you think Thai word to describe that English word is not clear as the original one, you can decide to keep it untouched.
5. When in doubt, use the existing translation as the guideline.

## Submitting a pull request
One PR should contain only one chapter so the reviewer can focus only on that chapter also this will keep PR in a reasonable size to review.

### Commit message
For the commit message, use the following format:

```<type>::<chapter>::<line_number>::<subject(optional)>```

#### Types are
- `translate` :: Translate from the original language to Thai
- `change` :: Change incorrect translation which mean the meaning of the translation is going to change
- `fix` :: Fix typo in the translation
- `refined` :: Refined the word which already in Thai to be smoother to read but didn't change any meaning of it
- `format` :: Formatting texts or page
- `update` :: Update the detail of the page. This can happen when [the official repo](https://github.com/rust-lang/book) has change the detail in that page.

#### Chapter
Use the page type (chapter, appendix, forward, etc.) following the number of that kind of page. If there's no number specific for that kind of page, just use page type.

Example
- For _ch03-02-data-types.md_ use `ch03-02`
- For _appendix-04-useful-development-tools.md_ use `appendix-04`
- For _title-page.md_ use `title-page.md`

#### Line number
- If the change is only a single line, use format `<line_number>`
- If the change contains lines, use format as `<line_number_from>-<line_number_to>` (Note: There's a dash between these two line numbers)

Example
- For line number 5 use `5`
- For line number 5 to 27 use `5-27`

#### Subject (optional)
is a short description of what has been done

Example
- For _change_ chapter _appendix-01-keywords.md_ line number _5_ use `change::appendix-01::5`
- For _translate_ chapter _ch08-02-strings.md_ line number _19 to 42_ use `translate::ch08-02::19-42`
