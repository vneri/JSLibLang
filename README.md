# JSLibLang
On-the-fly JavaScript translation library, for those who need a small, easy library.

## Preparing the language files
Take the example file included in the package:
```JavaScript
var lang_en = {
  "title": 'This is a title',
  "anotherTranslation": 'This is another translation',
  "changeLanguage": 'Change language',
  "buttonText": 'This is a button'
}
// tell the library here comes a new language
lib_lang.addLang('en');
```
That's all, this is how you define a new language file, and tell the library that it is available under "en".
You could create any language or dialect. The translation happens on the fly.

## Importing the libraries
First you import the base library:
```HTML
<script src="js/lib_lang.js"></script>
```
Then import the according language file, where you have defined the translations:
```HTML
        <script src="js/lang_en.js"></script>
        <script src="js/lang_it.js"></script>
```
## Defining a standard language
In your main code, you can set a standard language, or let the library take the predefined of the browser.
```JavaScript
// let's fix the language, otherwise the system language is taken
lib_lang.setLang('en');
```
## Building a language selector
A language selector could be done like this:
```HTML
<input type="button" data-lang-type="value" data-lang="buttonText" />
  <select onchange="javascript:lib_lang.changeLang(this.value)">
    <option value="en" selected="selected">EN</option>
    <option value="it">IT</option>
  </select>
```

## Preparing the HTML elements
In order for the library to discover translatable elements, you will have to mark them.
In the example file included, you will find the following elements, that can be translated:
```HTML
<h1 data-lang="title"></h5>
<input type="button" data-lang-type="value" data-lang="buttonText" />
```

The first one indicates, that it will contain any text defined with the label **text**.
The second one targets an attribute, because in the case of a button you will want the value to be translated. So in this case you indicate the name of the attribute (*value*) and a **label** for it (*buttonText*).

## Switching off auto-translate
You may want not to automatically start the translation for the page after onLoad (standard behaviour).
In this case, be sure to provide this attribute somewhere in your HTML document:
```HTML
<meta [data-lang-option="no-autostart"] />
```
