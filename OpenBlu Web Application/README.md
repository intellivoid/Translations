# OpenBlu Web Application

The OpenBlu Web Application is written under the DynamicalWeb
framework (Internal Solution developed by Intellivoid), this
framework uses a single json file to display text for individual
pages and imported sections.


## Example Document
```json
{
    "language": {
        "name": "english",
        "iso_639-1": "en"
    },
    "pages": {
        "index": {
            "PAGE_TITLE": "Example - Index",
            "HEADER": "Example Document",
            "BODY": "This is a Example Document",
            "INFO_MESSAGE": "Information!",
            "SUBMIT_BUTTON": "Submit",
            "AGE": "You are %s years old!"
        },
        "404": {
            "PAGE_TITLE": "Example - 404 Not Found",
            "HEADER": "404 Not Found",
            "BODY": "This page does not exist!"
        }
    },
    "sections": {
        "navigation_bar": {
            "NAVBAR_HOME": "Home Page",
            "NAVBAR_ABOUT": "About Page"
        },
        "footer": {
            "COPYRIGHT": "Copyright Example 2018"
        }
    }
```

The document above is an example of what a translation file
(Language File / JSON File) typically looks like. During
translating the structure should remain the same. There cannot
be removed or added values unless the primary language file
(EN) has been updated.

In the case if another translation is missing a value, the
fallback language (EN) will be used to display the missing
text

-----------------------------------------------------------------

### Language Structure

`language` Contains basic information about the language
that's presented in this document, including the language code
aka a `iso_639-1` code.

```json
"language": {
    "name": "english",
    "iso_639-1": "en"
}
```


### Pages Structure

`pages` Is a list of existing pages that the Web Application
can present, within each page it contains a `NAME`: `VALUE`
structure, `NAME` to represent the element that's being
displayed and `VALUE` which is the text that's displayed
within the element.

When translating this, the `NAME` part **DOES NOT** change, only
the `VALUE` should be translated.

In some cases you may see a value containing one or more `%s`'s.
these are placeholder values which are replaced during runtime.
If the value contains this, it should not be removed. Because
"`You are %s years old!`" will become "`You are 24 years old!`"
during runtime. You can change it's position or even put it
between two characters, for example; "`Hello, you are number #%s`"

```json
"index": {
    "PAGE_TITLE": "Example - Index",
    "HEADER": "Example Document",
    "BODY": "This is a Example Document",
    "INFO_MESSAGE": "Information!",
    "SUBMIT_BUTTON": "Submit",
    "AGE": "You are %s years old!"
}
```

### Sections Structure

`sections` Works the same way as pages, but rather translating
individual pages it translates sections of the web application,
which is typically a navigation bar, footer, banners, etc.

```json
"navigation_bar": {
    "NAVBAR_HOME": "Home Page",
    "NAVBAR_ABOUT": "About Page"
}
```