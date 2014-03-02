
Thanks for your interest in translating Fritzing into another language. So far we have Fritzing available in English, German, Spanish, Italian, French, European Portuguese, Dutch, Chinese (Simplified), Chinese (Traditional), Japanese, and Russian.
Here are the steps to complete a translation:

### 1. Contact us and let us know which language you’d like to work on.

[Send us a message](http://fritzing.org/contact) letting us know that you're interested in translating Fritzing into another language. We will then post a translation file for you to work with, which will be called something like “fritzing_your_language.ts”. This is an xml-based file that holds all the English-language words and phrases in Fritzing.

### 2. Download Linguist

Download a program called [Linguist](http://qt-apps.org/content/show.php/Qt+Linguist+Download?content=89360) which is made by the people who make Qt (our development environment). All you need for the translation task is the Linguist tool. You can also download the complete [Qt toolkit](http://www.trolltech.com/), but it's only required if you want to do development work on Fritzing. Using Linguist, you translate one line at a time and make a check mark when a line is ready.

### 3. Download Fritzing Source Code

Although it is not strictly necessary, it is very helpful to have the source code.  This is because the **ts file** only contains the phrases to be translated, and if you have the source code, you can see more of the context surrounding each phrase. Each entry in the ts file points back to the line of source code from which it originates.

There are a couple of ways to download the source files.  If you are familiar with git, this is the most straightforward approach, and the files will be the most up-to-date. You can find the repository at <http://code.google.com/p/fritzing/> (to browse, click on the 'source' tab).  You will find your **ts file** in the **translations** subfolder.

If you're not familiar with git you can download the source tarball from the fritzing/downloads page.  Once you have downloaded and extracted the files, you will find your ts file in the translations subfolder.  Note that the source tarball isn't updated as often as the git repository.

### 4. Translate Fritzing Texts

Within Linguist/QT, use the file/open menu item to load “fritzing_your_language.ts”. On the left side of the application, you’ll see a list of files. Clicking any of the files here shows all the items that need to be translated in that file. You can select those items 1-by-1--the one that's currently selected is the one you will be translating, and that's what the text entry area, in the center right, is for.
Some Helpful Notes:
Note the three tabs on the bottom--"warnings", "source code", "phrases and guesses".

a) "Source code" gives you context of where the text appears in the source code, so you can figure out the intent of the text.  The source code only appears if you have downloaded it (see Step 3, above).

b) "Phrases and guesses" tries to match what you're working on with examples you've already completed--double-clicking an example will put it into the text entry area and save a lot of typing.

c) "Warnings" lets you know about missed punctuation, and the like.

Another really handy shortcut which saves a lot of typing is to use control (command) b--it copies the currently selected untranslated text into the text entry area.

### 5. What do you mean "%1%2%3"

No these aren't curses. They represent values to be filled in at runtime. Languages have different ways to order words in phrases, so the order of these values can be changed accordingly. Here's an explanation (from the programmer's point-of-view) from Qt. The phrase you would see in Linguist is the one inside the "tr()":

```
void FileCopier::showProgress(int done, int total, const QString &currentFile){
     label.setText(tr("%1 of %2 files copied.\nCopying: %3").arg(done).arg(total).arg(currentFile));
 }
In some languages the order of arguments may need to change, and this can easily be achieved by changing the order of the % arguments. For example:
 QString s1 = "%1 of %2 files copied. Copying: %3";   // the phrase in quotes is what you would see in Qt Linguist     
 QString s2 = "Kopierer nu %3. Av totalt %2 filer er %1 kopiert.";   // the phrase in quotes is how you would translate it to Norwegian in Qt Linguist     
 qDebug() << s1.arg(5).arg(10).arg("somefile.txt");      
 qDebug() << s2.arg(5).arg(10).arg("somefile.txt");
produces the correct output in English and Norwegian:
 5 of 10 files copied. Copying: somefile.txt      
 Kopierer nu somefile.txt. Av totalt 10 filer er 5 kopiert.
```

There's also a special parameter form for plurals: %n. Qt gives a good explanation [here](http://doc.trolltech.com/qq/qq19-plurals.html).
More explanation of the translation process can be found in the [Qt Linguist manual](http://doc.trolltech.com/4.4/linguist-translators.html).

### 6. Post Your Translated File

Once you're ready to upload the “fritzing_your_language.ts” file, you can go to [issue 514](https://code.google.com/p/fritzing/issues/detail?id=514) in the issue tracker and use the "attach file" link to post us the file.  You have to click on the text area entitled "Add a Comment and Make Changes" to bring up the "attach file" link.  Alternatively, you can email it as an attachment to <info@fritzing.org>.
A couple of things to note. First, it is not necessary to translate all of Fritzing at one go. You are translating one line at a time, so any translations you make will be added. Therefore, you can post the translation file even though it isn't fully translated. Second, translations are not lost as Fritzing changes. As long as the text of a given line stays the same between Fritzing versions (which is true in the majority of cases), the translation of that line is preserved in future versions.

### 7. Translation is an ongoing process

As Fritzing is being developed, new prompts, new dialogs, new menu items, etc., are added to the program.  So after the initial translation task is done, consider returning to fritzing_your_language.ts every so often, and updating the new translations in the file (the old work isn't lost).
[Let us know](http://fritzing.org/contact/) if you run into any difficulties and thanks very much for helping out.


### Refs

* <http://fritzing.org/support-us/language-translation>