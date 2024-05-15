# **Quizzes**

It seems like you're interested in incorporating quizzes into your content using LiaScript, a Markdown-based platform. Here's an explanation along with examples and code snippets for each type of quiz supported by LiaScript:

1. **`Types of Quizzes:`**

LiaScript supports 6 different types of quizzes, along with a generic type that allows for custom quizzes:

**`Multiple-Choice:`**

```
[[X|x|Option 1]] ...
```

- In this format, "X" marks the correct answer, while other options are separated by "|".

**`Single-Choice:`**

```
[(X|x|Option 1)] ...
```

- Similar to multiple-choice, but only one option is correct.

**`Matrix:`**

- A combination of multiple-choice and single-choice quizzes.

**`Text-Quiz:`**

```
[[solution]]
```

- This type is used for text-based quizzes with a single correct answer.

**`Selection-Quiz:`**

```
[[Option 1 | Option 2 | (Correct Option)]]
```

- Users select the correct option from provided choices.

**`Gap-Text:`**

- Utilizes selection and text quizzes within Markdown blocks.

**`"Generic":`**

```
[[!]]
```

- This type allows for custom quizzes of any kind.

2. **`Additional Features:`**

- You can enhance quizzes with various features:

**`Hints:`**

```
[[?]]
```

- Provides hints to users attempting the quiz.

**`Solutions:`**

- Arbitrary Markdown content can be used to explain solutions.

**`Associated Scripts:`**

- Scripts can be attached to quizzes to implement more advanced functionality or log outputs.

**`Example:`**

Here's an example of a multiple-choice quiz with hints and associated scripts:

```
[[X|x|Option 1| Option 2 | Option 3 ?]] The correct answer is hidden here.

[[?]] This is a hint to help you.

[[!]] console.log("Script executed!");
```

This code creates a multiple-choice quiz with three options, where "Option 1" is the correct answer. It includes a hint and a script that logs output when the quiz is attempted.

## Quiz Types

1. [**Multiple-Choice**](#Multiple-Choice)
2. [**Single-Choice**](#Single-Choice)
3. [**Matrix-Quiz**](#Matrix-Quiz)
4. [**Text-Quiz**](#Text-Quiz)
5. [**Selection-Quiz**](#Selection-Quiz)
6. [**Gap-Text Extreme**](#Gap-Text-Extreme)
7. [**Generic Quizzes**](#Generic-Quizzes)
8. [**Notes about Questions**](#Notes-about-Questions)

### **Multiple-Choice**

In LiaScript, a multiple-choice quiz can be represented using ASCII checkboxes, making it easy for users to interact with the quiz. Here's how you can create a multiple-choice quiz along with explanations and examples:

**`Multiple-Choice Quiz Syntax:`**

You can represent a multiple-choice quiz using ASCII checkboxes enclosed in double brackets. Here's the syntax:

`[[ ]]:` Represents an empty checkbox (not checked).

`[[X]] or [[x]]:` Represents a checked checkbox (uppercase or lowercase "X" both work).

**`Example:`**

```
[[ ]] Empty means not checked
[[X]] Uppercase X means checked ...
[[x]] ... and lowercase x too ...
[[ ]] **as defined in the first line** ...
```

**`Explanation:`**

- The checkboxes are used to indicate whether each statement is true or false. 

- Uppercase or lowercase "X" can be used interchangeably to mark a checked element.

- The statements are presented as options for the quiz.

**`OUTPUT`**

- [[ ]] Empty means not checked
- [[X]] Uppercase `X` means checked ...
- [[x]] ... and lowercase `x` too ...
- [[ ]] **as defined in the first line** ...

**`Additional Notes:`**

- The starting dashes for quizzes are optional. You can present the quiz as a single paragraph without them.

- Alternatively, you can use an indentation of at least 4 spaces, which will be interpreted as code by other Markdown renderers but will still be understood as a quiz by LiaScript.

### **Single-Choice**

Parentheses are used to define radio buttons in single-choice quizzes. Only one option can be selected. Here's the syntax:

**`[( )]:`** Represents an option that is not selected.

**`[(X)] or [(x)]:`** Represents the correct option that needs to be selected.

**`Example:`**

```
[( )] Not selected
[(X)] **This one has to be selected**
[( )] ~~Do not select this one ...~~
```

**`Explanation:`**

- Users can select only one option from the provided choices.

- The correct option is indicated by marking it with an uppercase or lowercase "X".

- Additional Markdown formatting can be applied to the options for clarity or emphasis.


**`Multiple Correct Options:`**

You can define multiple possible correct options, but users can only select one. Here's an example:

```
What is the correct spelling of H(D)D?

[(X)] hard (**disk**) drive
[( )] hard (**desk**) drive
[(x)] hard (**disc**) drive
```

**`True/False Quiz:`**

You can create a true/false quiz using single-choice quizzes. Here's an example:

```
Do you know an easier way of creating quizzes?

[( )] Yes
[(X)] No
```

**`Additional Notes:`**

- As with multiple-choice quizzes, you can omit starting dashes and/or use indentation.

- Upper- or lowercase "X" can be used interchangeably to indicate the correct option.

**`Result`**

Do you know an easier way of creating quizzes?

[( )] Yes
[(X)] No


### **Matrix-Quiz**

- Define the header row to represent the solution options. Use brackets or parentheses within the header line as needed.

- Each subsequent row represents a quiz vector, with brackets indicating multiple-choice quizzes and parentheses indicating single-choice quizzes.

**`Example:`**

Man or woman is obvious, but can you guess the remaining German grammatical genders?

[[male (der)] (female [die]) [neuter (das)]]
[    [X]           [ ]             [ ]     ]  Mann - German for man
[    ( )           (X)             ( )     ]  Frau - German for woman
[    [X]           [ ]             [ ]     ]  Junge - German for boy
[    ( )           ( )             (X)     ]  Mädchen - German for girl
[    [X]           [X]             [ ]     ]  Paprika - German for bell pepper
[    (X)           (X)             (X)     ]  Joghurt - German for yogurt


**`Explanation:`**

- The header row defines the solution options for each column.

- Each subsequent row represents a quiz vector, with checkboxes for multiple-choice quizzes and radio buttons for single-choice quizzes.

- Users can select options for each row based on the provided solution options.

**`Fun Fact:`**

The number of elements within a row doesn't necessarily have to match the number of elements within the header. Although it might be rendered strangely, this won't cause an error. This flexibility allows for customization and intentional design choices.

**`Additional Notes:`**

- You can include additional Markdown content within the quiz to provide context or instructions.

- Use comments (<!-- -->) to add annotations or additional information within the Markdown content.

### Text-Quiz

In LiaScript, you can create simple text-input quizzes by enclosing the solution string within double brackets. These quizzes allow users to input their answer as text, and the quiz is marked as solved only if the user's input matches the solution string exactly. Here's an explanation and example for creating text-input quizzes:

**`Text-Quiz Syntax:`**

A text-input quiz is defined by enclosing the solution string within double brackets.

**`Example:`**

```
What did the fish say when he swam into the wall?

[[dam]]
```

**`Explanation:`**

- The user is prompted with a question or statement.

- The solution string is enclosed within double brackets.

- Users input their answer as text, and the quiz is marked as solved only if their input matches the solution string exactly.

**`Additional Notes:`**

- Starting dashes are not allowed for text-input quizzes, but you can use optional indentation.
- The input is compared directly with the solution string, so spelling, capitalization, and other factors must match exactly unless modified by associated scripts.

**`Result:`**

What did the fish say when he swam into the wall?

[[dam]]


**`Check`**

- The user can input their answer, and if it matches the solution string "dam", the quiz will be marked as solved.

- You can also associate scripts with text-input quizzes to handle different types of spelling, capitalization, etc. This allows for greater flexibility in accepting user input.


### **Selection-Quiz**

A selection-quiz consists of LiaScript/Markdown options separated by vertical bars (|). The correct options are surrounded by parentheses.

**`Example:`**

```
What is the derivative function of $f(x) = x^6$?

[[ $f'(x) = 6$ | ( $f'(x) = 6x^5$ ) | $f'(x) = 5x^6$ ]]

Can be also written as:

    [[  $f'(x) = 6$
    | ( $f'(x) = 6x^5$ )
    |   $f'(x) = 5x^6$
    | ( **This will be counted as correct too...** )
    ]]
```

**`Explanation:`**

- Users are presented with a question or statement.

- Multiple options are provided, separated by vertical bars (|).

- Correct options are enclosed within parentheses.

- Users can select one or more correct options.


**`Additional Notes:`**

- Multiple correct options are supported.

- Starting dashes are not supported for selection-quiz, as they might be used in the future for cloze elements.

- Indentation can be used for better readability.

**`Result:`**

What is the derivative function of $f(x) = x^6$?

[[ $f'(x) = 6$
| ( $f'(x) = 6x^5$ )
| $f'(x) = 5x^6$ ]]

Can be also written as:

[[ $f'(x) = 6$
| ( $f'(x) = 6x^5$ )
| $f'(x) = 5x^6$
| ( This will be counted as correct too... )]]

Users can select the correct option(s) and submit their answer. The quiz will be marked as solved if the user selects one or more correct options.


### **Gap-Text Extreme**

Internally referred to as a multi-quiz, this type allows you to freely use text-input and selection quizzes within all other kinds of Markdown blocks.

**`Example 1:`**

```
__I (learn) [[  have been learning  ]] English for seven years now.__
But last year I (not / work) [[ was not working ]] hard enough for English,
that's why my marks (not / be) _[[ were not ]]_ really that good then.
As I (pass / want) [[ want to pass ]] my English exam successfully next year,
I (study) ~[[ am going to study ]]~ harder this term.
```

**`Explanation:`**

- Text-input quizzes are embedded within the text using the pattern __text__ [[solution]]__.

- Users can input their answers directly into the text.

- Correct answers are enclosed within double brackets.

**`Example 2:`**

```
Wladimir [[ Putin ]] is the richest (still living) dictator
with an estimated fortune of over
__4,500,000,000 [[ (US Dollar 💵) | Euro 💶 | _Rubel 💸_ | Pound 💷 ]]__!
```
**`Explanation:`**

- Selection quizzes are embedded within the text using the pattern __text__ [[option 1 | option 2 | (correct option)]]__.

- Users can select the correct option from the provided choices.

- Correct options are enclosed within parentheses.


**`Additional Notes:`**


- Markdown syntax can be used to style the quizzes and their options within the text.

- You can include additional content, such as comments or explanations, within the Markdown blocks.

**`Result:`**

__I (learn) [[  have been learning  ]] English for seven years now.__
But last year I (not / work) [[ was not working ]] hard enough for English,
that's why my marks (not / be) _[[ were not ]]_ really that good then.
As I (pass / want) [[ want to pass ]] my English exam successfully next year,
I (study) ~[[ am going to study ]]~ harder this term.

Wladimir [[ Putin ]] is the richest (still living) dictator
with an estimated fortune of over
__4,500,000,000 [[ (US Dollar 💵) | Euro 💶 | _Rubel 💸_ | Pound 💷 ]]__!

#### **More!!!**

Since text inputs and selections are now a so-called first class member within LiaScript, you can think of creating other kinds of quizzes, by not only using simple paragraphs.

This section shows only some inspirational examples that you can use and extend for your own purpose.

**`Base Math`**

Of course, basic arithmetic is quite simple now ...


````
``` ascii
.----------.      .----------.
| ⭐       |      |  ⭐ ⭐   |
|      ⭐  |      | ⭐ ⭐ ⭐ |
'----------'      '----------'
```

[[ 2 ]] + [[ 5 ]] = [[ 7 ]]
````

---

<!-- style="max-width: 300px" -->
``` ascii
.----------.      .----------.
| ⭐       |      |  ⭐ ⭐   |
|      ⭐  |      | ⭐ ⭐ ⭐ |
'----------'      '----------'
```

[[ 2 ]] + [[ 5 ]] = [[ 7 ]]

**`Who said this?`**

But, you can also, like in this example, use a simple selection within a quote to create a quiz?

```
> “How is education supposed to make me feel smarter?

> Besides, every time I learn something new, it pushes some old stuff out of my brain.

> Remember when I took that home winemaking course, and I forgot how to drive?”

>

> -- By [[ Dieter Nuhr | Nida Mohammad Nadim | (Homer Simpson)]]
```

“How is education supposed to make me feel smarter?

> Besides, every time I learn something new, it pushes some old stuff out of my brain.

> Remember when I took that home winemaking course, and I forgot how to drive?”

>

> -- By [[ Dieter Nuhr: _German comedian_ | Nida Mohammad Nadim: _Afghan minister for higher education_ | (Homer Simpson: _A cartoon character too_)]]

**`Read it aloud`**

Later in section `Effects`, you will learn about animations and text to speech output.
Effects in LiaScript are always associated with curly braces.
Adding two curly braces on top of a Markdown block will add a play-button that will read aloud loud the entire block.
Additionally, you can also change the voice, depending on the language you each.

```
The film that I saw [[(that)|those|these|then]] night wasn’t very good.
It was all [[ about ]] a man [[ who ]] built a
time machine so he [[ could ]] travel back in time.
It took him ages and ages [[ to ]] build the machine.
```


The film that I saw [[ (that)|those|these|then ]] night wasn’t very good.
It was all [[ about ]] a man [[ who ]] built a
time machine so he [[ could ]] travel back in time.
It took him ages and ages [[ to ]] build the machine.



**`Tables`**

Of course, you can use a table and add some inputs and create a structured quiz...


```
German grammar test:

| Verb    |   Person      | Präsens von "werden" | Partizip II    | Infinitiv von haben/sein |
|---------|:-------------:|:--------------------:|:--------------:|:------------------------:|
| gehen   | Ich           |     [[ werde  ]]     | [[ gegangen ]] | [[ sein ]].              |
| sage    | Du            |     [[ wirst  ]]     | [[ gesagt ]]   | [[ haben ]].             |
| machen  | Er / Sie / Es |     [[ wird   ]]     | [[ gemacht ]]  | [[ haben ]].             |
| laufen  | Wir           |     [[ werden ]]     | [[ gelaufen ]] | [[ sein ]].              |
| singen  | Ihr           |     [[ werdet ]]     | [[ gesungen ]] | [[ haben ]].             |
| spielen | Sie           |     [[ werden ]]     | [[ gespielt ]] | [[ haben ]].             |
```



German grammar test:

| Verb    |   Person      | Präsens von "werden" | Partizip II    | Infinitiv von haben/sein |
|---------|:-------------:|:--------------------:|:--------------:|:------------------------:|
| gehen   | Ich           |     [[ werde  ]]     | [[ gegangen ]] | [[ sein ]].              |
| sage    | Du            |     [[ wirst  ]]     | [[ gesagt ]]   | [[ haben ]].             |
| machen  | Er / Sie / Es |     [[ wird   ]]     | [[ gemacht ]]  | [[ haben ]].             |
| laufen  | Wir           |     [[ werden ]]     | [[ gelaufen ]] | [[ sein ]].              |
| singen  | Ihr           |     [[ werdet ]]     | [[ gesungen ]] | [[ haben ]].             |
| spielen | Sie           |     [[ werden ]]     | [[ gespielt ]] | [[ haben ]].             |



But, since tables are treated as data sets that scream for visualization (for more information checkout section `Fun with Tables`, you can use also this feature to visualize your quiz.
The following two examples are called "know your competitors" ;-) and they are used only for illustration.
Depending on the tabular structure you define and the type of data you provide, LiaScript will try to estimate an appropriate visualization.
For input fields, the value of the solution is used for classification.


```
<!-- data-title="LMS market share 2022 (North America)" -->
| Brightspace    | Canvas          | Classroom      | Moodle          | Others         | Schoology      |
|:--------------:|:---------------:|:--------------:|:---------------:|:--------------:|:--------------:|
| [[(3 %)|11 %]] | [[13 %|(28 %)]] | [[8 %|(24 %)]] | [[(11 %)|31 %]] | [[2 %|(12 %)]] | [[7 %|(22 %)]] |



| LMS | Average cost per month   |
|-----|--------------------------|
| Brightspace | [[13 $|(80 $)]]  |
| Canvas      | [[(10 $)|99 $]]  |
| Classroom   | [[(0 free)|3 $]] |
| Moodle      | [[11 $ |(15 $)]] |
| Schoology   | [[(4 $)|12 $]]   |
```

**`OUTPUT`**

<!-- data-title="LMS market share 2022 (North America)" -->
| Brightspace    | Canvas          | Classroom      | Moodle          | Others         | Schoology      |
|:--------------:|:---------------:|:--------------:|:---------------:|:--------------:|:--------------:|
| [[(3 %)|11 %]] | [[13 %|(28 %)]] | [[8 %|(24 %)]] | [[(11 %)|31 %]] | [[2 %|(12 %)]] | [[7 %|(22 %)]] |



| LMS | Average cost per month   |
|-----|--------------------------|
| Brightspace | [[13 $|(80 $)]]  |
| Canvas      | [[(10 $)|99 $]]  |
| Classroom   | [[(0 free)|3 $]] |
| Moodle      | [[11 $ |(15 $)]] |
| Schoology   | [[(4 $)|12 $]]   |


**`Galleries`**

Galleries are just a collection of multimedia links.
The text within brackets is used as `alt` or alternative text for an image, if the image cannot be displayed (which is also used by screen readers). And the additional text within quotes is commonly used for the title attribute, but it LiaScript it is also displayed as a subtitle that can contain valid LiaScript Markdown. Well, if this is the case, this can be used to contain also input fields, such that the entire gallery is then interpreted as on quiz.

```
![image 1](https://img1 "Markdown subtitle [[(option 1)|option 2|option 3]]")
![image 2](https://img2 "Another [[subtitle]]")
!?[video](https://www.youtube.com/watch?v=... "Subtitle for [[multi-media]]")
```

**`OUTPUT`**

![Self portrain](https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Self-portrait_as_the_Allegory_of_Painting_%28La_Pittura%29_-_Artemisia_Gentileschi.jpg/767px-Self-portrait_as_the_Allegory_of_Painting_%28La_Pittura%29_-_Artemisia_Gentileschi.jpg "Self-Portrait as the Allegory of Painting: [[(1638 - 1639)|1641|1641-1642]]")

![Samson and Delilah](https://upload.wikimedia.org/wikipedia/commons/thumb/7/73/Samson_und_delilah.jpg/1221px-Samson_und_delilah.jpg "Samson and Delilah: [[1628|(1630 - 1638)|1633 - 1637]]")

![Virgin with the Child](https://upload.wikimedia.org/wikipedia/commons/e/e0/Artemisia_Gentileschi_-_Madonna_con_Bambino_%281609-1610%29.jpg "Virgin with the Child: [[(1609–1610)|1618|1622-1623]]")

!?[BBC Documentary](https://www.youtube.com/watch?v=WcSRtdg9FyM "BBC Documentary: Michael Palin's Quest for Artemisia")

**`Last but not Least (ASCII-art)`**

Checkout what is possible in section `ASCII-Art`, but these are basically sketches and drawings based on a few ASCII-characters such as `+`, `|`, `-`, and some more.
To indicate such an image use a standard Markdown code-block and use `ascii` as the language prefix

```` markdown
<!-- data-show-partial-solution -->
``` ascii
                        .----------------------.
                       /                      /|
             .--------+----------------------+ +---------.
            /         |      " [[  24   ]] " |/         /|
  .--------+----------+----------+-----------+---------+ +----------.
 /         |         11          |      "[[   13   ]] "|/          /|
+----------+----------+----------+----------+----------+----------+ +
|      " [[   5   ]] "|          6          |          7          |/
+---------------------+---------------------+---------------------+
```
````

The LiaScript elements have to be placed into quotations, to separate them from the ASCII-art image, which is turned into an SVG image.
To trick the interpreter from applying a single line text-input, we need to add a space before the actual input.

<!-- data-show-partial-solution -->
``` ascii
                        .----------------------.
                       /                      /|
             .--------+----------------------+ +---------.
            /         |      " [[  24   ]] " |/         /|
  .--------+----------+----------+-----------+---------+ +----------.
 /         |         11          |      "[[   13   ]] "|/          /|
+----------+----------+----------+----------+----------+----------+ +
|      " [[   5   ]] "|          6          |          7          |/
+---------------------+---------------------+---------------------+
```




### Generic Quizzes

Generic quizzes can be used to define any kind of quiz. The course-developer can
define own types of quizzes, whereby the following combination of brackets with
an additional exclamation mark has to be associated with a script.

```
[[!]]
<script>
  const random = Math.random()

  alert("random value: "+ random)

  random < 0.2
</script>
```

This script does only generate a random number, outputs the result in an `alert`
and checks if the random value is less than 0.2. And if so, the quiz will be
marked as solved otherwise not. Thus, the last statement has to be `true` in
order to mark a quiz as solved, any other value will be accounted as `false`.

[[!]]
<script>
  const random = Math.random()
  alert("random value:"+ random)
  random < 0.2
</script>

The usage of associated scripts for quizzes will be described in detail in
section `Quizzes and Scripting`.

### Notes about Questions

Not all of the previous examples we have shown were perfect in the sense of
accessibility. Although these quizzes look good "for us", they might not be
perfectly for people that require a screen-reader to go through a course.
However, you can improve your quizzes by asking your question as a paragraph,
which is followed by your quiz. This way LiaScript will associate or label the
quiz with your question.

<!-- class="translate"-->
```
Ask a question as an ordinary Markdown paragraph,
which is followed by what?

    [[quiz]]
```


If your question requires more elements, then it is also possible to group it
with supplemental elements by putting it into a single HTML-element such as a
`div`. The `div` will get a unique ID and the question will be labeled with this
ID by using the
[aria-labelledby](https://www.w3.org/TR/wai-aria/#aria-labelledby) attribute.

<!-- class="translate"-->
```
<div>

Ask a question as an ordinary Markdown paragraph,
which is followed by what?

1. important
2. also relevant ...
3. [an image](http://...)

</div>

    [[quiz]]
```

## Tweaks

All of the following elements can be added to any type of quiz that you have
seen before. This includes and arbitrary number of hints, a more detailed
solution or a custom script that handles the user input.

<div style="width:100%;height:0;padding-bottom:63%;position:relative;"><iframe src="https://64.media.tumblr.com/2a699194b0283a157e9960aba10055ba/tumblr_ol0xsmGFQu1qmif1go1_400.gifv" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div><p><a href="http://valeris-media.tumblr.com/">via GIPHY</a></p>

### Hints

To any type of quiz you can add as many hints as you want, the pattern is simply
two brackets with an additional question mark. If you want to, you can also add
starting dashes to the hints.


```
What is $37 + 15$?

    [[52]]
    [[?]] the solution is larger than 50
    [[?]] it is less than 55
    [[?]] it should be an even number

This is also a valid quiz ...

[[52]]
- [[?]] the solution is larger than 50
- [[?]] it is less than 55
- [[?]] it should be an even number
```

The user can reveal these hints, step by step by clicking onto the light bulb or
"show hint" button.

What is $37 + 15$?

    [[52]]
    [[?]] the solution is larger than 50
    [[?]] it is less than 55
    [[?]] it should be an even number

### Solution

And finally, some quizzes might require some more explanations, if they are
solved or not. Therefor, simply use two "lines" that are defined by at least
three asterisks to group your solution. The solution explanation can contain
an arbitrary number of LiaScript elements.


````
What is $37 + 15$?

[[52]]
[[?]] the solution is larger than 50
[[?]] it is less than 55
[[?]] it should be an even number

52 is the correct solution, you get this by adding:

```
                        .------.
                        |      |
                        |      v
                        |
                        |     (1)
  37           3(7)     |     (3)x          37
+ 15         + 1(5)     |   + (1)x        + 15
---- -->     ------ --> |   ------ -->    ----
  ??           (12)     |     (5)2          52
                |       |                 ====
                '-------'
                  carry
```

??[MS-DOS Math Game](https://archive.org/embed/msdos_Super_Solvers_Teasure_MathStorm_1992)

````

In this case the solution contains an ASCII-art drawing, but it can be anything,
such as a an image, a video, or even something like a small game

What is $37 + 15$?

[[52]]
[[?]] the solution is larger than 50
[[?]] it is less than 55
[[?]] it should be an even number


52 is the correct solution, you get this by adding:

```
                        .------.
                        |      |
                        |      v
                        |
                        |     (1)
  37           3(7)     |     (3)x          37
+ 15         + 1(5)     |   + (1)x        + 15
---- -->     ------ --> |   ------ -->    ----
  ??           (12)     |     (5)2          52
                |       |                 ====
                '-------'
                  carry
```

??[MS-DOS Math Game](https://archive.org/embed/msdos_Super_Solvers_Teasure_MathStorm_1992)


### Randomization

Currently it is only possible to randomize vector and matrix quizzes, that means that the order of rows can be shuffled.
This happens only ones, when the slide is loaded for the first time, this includes also page reloads.
Just by adding the option `data-randomize` to the comment attached to the head of the quiz.
Other options might be added in the future.

```
Are the options of the quiz in order?

- [(X)] option 1 (yes)
- [( )] option 2 (no)
- [(X)] option 3 (maybe)
- [( )] option 4 (I don't care)
```

If you reload the page, the order of the options will change, but not when you go to another slide and come back.

Are the options of the quiz in order?

- [(X)] option 1 (yes)
- [( )] option 2 (no)
- [(X)] option 3 (maybe)
- [( )] option 4 (I don't care)


### Further Settings

Next to randomization you can also use the following configuration options and also combine them:

**Maximum Trials `data-max-trials`**

Pass an integer to `data-max-trials` and the quiz will be automatically solved after x wrong trials.

```
What happens if you check 3 times the wrong answer?

<!-- data-max-trials="3"-->

[( )] Absolutelly nothing?

[(X)] The quiz will be solved!
```
---
What happens if you check 3 times the wrong answer?

[( )] Absolutelly nothing?

[(X)] The quiz will be solved!

**Hide and reveal the solve button `data-solution-button`**

You can either use values such as `on|off`, `true|false`, `disable|enable` to show or hide the solution button.
By default it is always `on`, but it is also possible to pass an integer value to reveal this button at a certein user trial.
In this case `0` is not interpreted as false, but that it should be immediately visible and `1` only after the first wrong trial.

```
Can you reveal the solution button?

[( )] YES

[(X)] NO


How many trials are necessary to show the solution button?

[[3]]
```

Can you reveal the solution button?

[( )] YES
[(X)] NO


How many trials are necessary to show the solution button?

[[3]]

**Hide and reveal the hint button `data-hint-button`**

- This configuration options can be used similarly as the previous one, although there won't be many occasions to disable or enable the hintbutton when no hints were defined.
- However, you can use the numerical value to show hints only after a certain amount of wrong trials, thus `1` will reveal the button only afterthe first wrong trial.

```
How many trials are necessary to show the hints?

[[2]]

[[?]] The solution is smaller than 3

[[?]] Try an even number
```

How many trials are necessary to show the hints?

[[2]]

[[?]] The solution is smaller than 3

[[?]] Try an even number

**Revealing Partial Solutions `data-show-partial-solution`**

- If a quiz might have to many input options and you require a way to separate partially correct answers from wrong ones, then you need to usethis attribute.

- It can be applied onto `gap-texts` and `matrix-quizzes`.

- In contrast to a gap-text, which can also contain single selections, in a matrix the entire row will be highlighted as correct or wrong.

````

``` ascii
                        .----------------------.
                       /                      /|
             .--------+----------------------+ +---------.
            /         |      " [[  24   ]] " |/         /|
  .--------+----------+----------+-----------+---------+ +----------.
 /         |         11          |      "[[   13   ]] "|/          /|
+----------+----------+----------+----------+----------+----------+ +
|      " [[   5   ]] "|          6          |          7          |/
+---------------------+---------------------+---------------------+
```
````
---

``` ascii
                        .----------------------.
                       /                      /|
             .--------+----------------------+ +---------.
            /         |      " [[  24   ]] " |/         /|
  .--------+----------+----------+-----------+---------+ +----------.
 /         |         11          |      "[[   13   ]] "|/          /|
+----------+----------+----------+----------+----------+----------+ +
|      " [[   5   ]] "|          6          |          7          |/
+---------------------+---------------------+---------------------+
```

**Scoring a quiz `data-score`**

- The result of this setting will not be visible at all, instead it is used to score a quiz, if the course is exported into a SCORM package anduploaded to an LMS.
- Within an export every quiz is rated equally with a value of 1.
- It is possible to pass an integer or float value, e.g. `2`, `2.0`, `2.12345`.

**`Combinations`**

And as mentioned earlier, you can freely combine all of these configurations.

```
You have only two trials, without a solution button ;-)
<!--
  data-max-trials="2"
  data-solution-button="off"
  data-randomize
-->
[( )] Wrong
[(X)] Right
```

You have only two trials, without a solution button ;-)

<!--
  data-max-trials="2"
  data-solution-button="off"
  data-randomize
-->
[( )] Wrong
[(X)] Right

### Associated Scripts

1. [**Cleaning up**](#Cleaning-up)
2. [**Quiz @inputs**](#Quiz-@inputs)
3. [**Async & Errors**](#Async-&-Errors)
4. [**Obfuscate-Quizzes**](#Obfuscate-Quizzes)
5. [**Quizzes & Macros**](#Quizzes-&-Macros)
6. [**GFinal thoughts on wrong solution**](#Final-thoughts-on-wrong-solution)
7. [**Generic++**](#Generic++)


#### Cleaning up

If you are using for example the text-quiz, and you want to react to different ways of spelling or to clean starting and trailing white-spaces. Then you can attach a script to your quiz. The `@input` is marker that will be substituted by the current user input. `trim` and `toLowerCase` are  JavaScript functions/methods that are used to clean the input string. The last statement of your quiz-script defines if the quiz is marked as solved or not. Only if the last statement evaluates to `true` it is marked as solved, for any other value it is simply a failed trial.

```
What did the fish say when he swam into the wall?

[[dam]]
<script>
let input = "@input".trim().toLowerCase()

input == "dam" || input == "damn"
</script>
```

Try out the following quiz. You can now enter "damn" or "dam" in different ways,
surrounded by spaces.

What did the fish say when he swam into the wall?

[[dam]]
<script>
let input = "@input".trim().toLowerCase()

input == "dam" || input == "damn"
</script>

#### Quiz @inputs

`@input` will be replaced by the current state of the quiz that should be
checked. If you are not sure, how the input might look like, you can always
experiment with a simple `alert` that shows the current input.


**`Text-quiz:`**

The output or in LiaScript terms the `@input` gets substituted by a string,
without apostrophes. This might look strange since you have to add apostrophes
within the code, but all inputs are substituted without any additional type
formatting, this way they can be used in different ways and even contain peaces
of code.

```
[[text]]
<script> alert("@input") </script>
```

**Result:**

[[text]]
<script> alert("@input") </script>

**`Selection-quiz:`**

A selection quiz is defined by a number that represents the current input,
starting from `0`. The initial state is marked with `-1` to indicate that
nothing has been selected so far. In this example `A` would be represented by
`0`, `B` by `1`, `C` by `2` and so on.

```
[[A|B|C|(D)]]
<script> alert(@input) </script>
```

**Result:**

[[A|B|C|(D)]]
<script> alert(@input) </script>

**`Multiple-choice:`**

A multiple-choice quiz is represented by an array of ones and zeros, whereby a
`1` means checked and `0` the opposite.

```
[[X]] A
[[ ]] B
[[X]] C
<script> alert("@input") </script>
```

**Result:**

[[X]] A
[[ ]] B
[[X]] C
<script> alert("@input") </script>

**`Single-choice:`**

A single-choice quizzes behave similar as selections, the state is represented
by a number, starting from `0`, which represents the first option. A quiz that
has been not touched by the user will return `-1` as input value.

```
[(X)] 0
[( )] 1
[(X)] 2
<script> alert("@input") </script>
```

**Result:**

[(X)] 0
[( )] 1
[(X)] 2
<script> alert("@input") </script>

**`Matrix:`**

As matrices are arrays of "vector" quizzes, their input state is represented as
an array of multiple-choice and single-choice states. Thus, a list of lists with
zeros and ones as well as numbers.

```
Weird, isn't it ;-)

[[male (der)]   (female [die])   [neuter (das)]]
[    [X]           [ ]             [ ]     ]  Mann - German for man
[    ( )           (X)             ( )     ]  Frau - German for woman
[    [X]           [ ]             [ ]     ]  Junge - German for boy
[    ( )           ( )             (X)     ]  Mädchen - German for girl
[    [X]           [X]             [ ]     ]  Paprika - German for bell pepper
[    (X)           (X)             (X)     ]  Joghurt - German for yogurt
<script>alert("@input")</script>
```

**`Result:`**

[[male (der)]   (female [die])   [neuter (das)]]
[    [X]           [ ]             [ ]     ]  Mann - German for man
[    ( )           (X)             ( )     ]  Frau - German for woman
[    [X]           [ ]             [ ]     ]  Junge - German for boy
[    ( )           ( )             (X)     ]  Mädchen - German for girl
[    [X]           [X]             [ ]     ]  Paprika - German for bell pepper
[    (X)           (X)             (X)     ]  Joghurt- German for yogurt
<script>alert("@input")</script>

**`Generic:`**

In case of a generic quiz, the developer is responsible for defining and storing
state. Thus, there will be no input. The only case where `@input` gets
substituted by a value, is when the user clicks onto the resolve button. This is
indicated by the input `true`.

```
[[!]]

<script>alert("@input")</script>
```

[[!]]
<script>alert("@input")</script>

#### Async & Errors

There might be the rare case, where you have to send the user input to an external service to check them. Scripts in LiaScript can also define
asynchronous code, as it is displayed within the example.

```
What is $37 + 15$?

[[52]]
<script>
setTimeout(function(){
  alert("your input was: '@input'")
  send.lia("true")
}, 1000)

"LIA: wait"
</script>
```

In LiaScript, we can use some command strings that trigger a certain behavior, these are global to all scripts and will be described in more detail in section `Communication`.

- `"LIA: wait"`: mark the script as still running

- `"LIA: stop"`: halt the execution of the script

Additionally, you can see a function-call within the example. `setTimeout` triggers the execution of the internally defined function, which performs an `alert` with the  user input and then sends "true" back to the internal quiz-event handler. Every script is executed with an additional `send` object and `send.lia` means send this back to LiaScript. Thus, the result could also be evaluated by an external service, and this result will then be used to control the quiz.

- `send`: general object to for communicating with the LiaScript internal event-handler for a specific entity, for more information see section `Communication`

Let us extend this example a little bit further. The `send` to `lia` can have two meanings, one if everything was ok while the second might be the result of an error. `send.lia` can have three values, the first is the message, the second one contains more detailed information about the result, which is not required at the moment, while the last value tells LiaScript if everything was ok or by using `false` that an error has occurred. The default value is always ok.

```
What is $37 + 15$?

[[52]]
<script>
setTimeout(function(){
  alert("your input was: '@input'")

  if ("@input" === "") {
    // generic error message
    send.lia("You have to fill in something into the input field", [], false)
  } else {
    // this is equal to send.lia("some message", [], true)
    send.lia("true")
  }
}, 1000)

"LIA: wait"
</script>
```

Thus, if you try out the following example, you will have to wait one second until the result is evaluated, which in this case always results in a solved quiz. But, if you do not add any input, then an error message will be displayed.


**`Result:`**

What is $37 + 15$?

[[52]]
<script>
setTimeout(function(){
  alert("your input was: '@input'")

  if ("@input" === "") {
    // generic error message
    send.lia("You have to fill in something into the input field", [], false)
  } else {
    // this is equal to send.lia("some message", [], true)
    send.lia("true")
  }
}, 1000)

"LIA: wait"
</script>

#### Obfuscate Quizzes

We would like to note, that this is only one method to obfuscate a quiz, by using JavaScript, in this case by using the function `btoa`.

```
[[...]]
<script>
// btoa("solution") == "c29sdXRpb24="
"c29sdXRpb24=" == btoa( "@input".trim().toLowerCase() )
</script>
```

[`btoa`](https://developer.mozilla.org/en-US/docs/Web/API/btoa) creates a [Base64](https://developer.mozilla.org/en-US/docs/Glossary/Base64)-encoded ASCII string, while [`atob`](https://developer.mozilla.org/en-US/docs/Web/API/atob) does the opposite. You can try out to the following two scripts to encode and decode different strings.

* `btoa`: <script input="text" value="solution" input-always-active modify="false">btoa(`@input`)</script>

  (Beautiful TO Awful)

* `atob`: <script input="text" value="c29sdXRpb24=" input-always-active modify="false">atob(`@input`)</script>

  (Awful TO Beautiful)

The result is a quiz, where it is not possible to see the solution immediately, simply by getting a glimpse onto the raw course document.

**`Result:`**

[[...]]
<script>
// btoa("solution") == "c29sdXRpb24="
"c29sdXRpb24=" == btoa( "@input".trim().toLowerCase() )
</script>

#### Quizzes & Macros

<!--
@customQuiz
[[...]]
<script>
"@0" == btoa( "@input".trim().toLowerCase() )
</script>
@end
-->

It might look tedious to create these trailing scripts and to add them again and again to your document, which makes a course harder to maintain and to develop. However, in LiaScript you can define macros, that can be used to solve repetitive tasks.

As depicted in the example, you can define custom macros within an HTML-comment of a section or within the main comment at the head of every document. Wherever you write the macro `@customQuiz` within your document, this macro will be substituted by the content defined in the HTML-comment, which comes between `@customQuiz` and `@end`. For more information see section `Macros`.

``` 
##### Quizzes & Macros
<!--

@customQuiz
[[...]]
<script>
"@0" == btoa( "@input".trim().toLowerCase() )
</script>
@end

-->
...

@customQuiz(c29sdXRpb24=)


@customQuiz(NTI=)
```

- You can further parameterize your macros, as you can see in the code, there is an `@0`, which can be interpreted as a placeholder that shall be substituted by the first parameter of your macro call.

- That's it, you can add as much as `@customQuiz`-macros and if you do some changes, you do not have to go through all scripts, but instead you only have to change one single macro.

The solution should be "solution":

@customQuiz(c29sdXRpb24=)

What is $37 + 15$?

@customQuiz(NTI=)

By defining macros it is furthermore possible to create LiaScript libraries that can imported into other courses, see therefor also section `Macros`.

#### Final thoughts on wrong solution

The quiz for adding two numbers was actually taken from the presentation of Greg Wilson, and it gives a good example for what scripts can be used for. Instead of logging and checking if an answer is correct or not, we should use it to assist students while they are learning and try to identify patterns in wrong answers.

!?[What Everyone in Tech Should Know About Teaching and Learning](https://www.youtube.com/watch?v=ewXvFQByRqY&start=717s)

As you have seen it for `tasks`, the result of a script can also be published, in this case the topic is defined by the `output` attribute.

```
What is $37 + 15$?

[[52]]
<script output="quiz:37+15">
  if ("@input" == "52") {
    true
  } else {
    "@input"
  }
</script>
```
Other scripts can be defined, that are subscribed to the output of the quiz, see the different `@input` macro. These scripts are executed when the output of the previous script changes. Every script can be used to identify another pattern, since students can be wrong for different reasons. We need to identify such patterns and react properly instead of measuring only fail and success.

```
<script style="display: block">
//   3(7)       (3)7
// + 1(5)     + (1)5       The first and second steps were correct,
// ------ ->  ------  ->   but the student forgot to carry the 1
//   (12)       (4)2       in the 10 digit column.

if ("@input(`quiz:37+15`)" == "42") {
  send.liascript(`## Maybe you forgot to carry...

Checkout the follow video to recap carrying.

!?[Carrying for larger digits](https://www.youtube.com/watch?v=VPsYRPdlIpU)
`)
} else ""
</script>

<script style="display: block">
//   3(7)       (3)7       The first and second steps were also
// + 1(5)     + (1)5       correct, but carrying was not provided
// ------ ->  ------  ->   properly, maybe there is a problem with
//   (12)      (4)12       understanding digit columns...


if ("@input(`quiz:37+15`)" == "412") {
  send.lia(`You are nearly there, there might be a problem with the 10 digit columns...`)
} else ""
</script>
```

With LiaScript you do not have to come up immediately with a perfect online course, you can adapt it in little steps and let it increasingly grow.

What is $37 + 15$? This time you should make the mistakes 42 and 412.

[[52]]
<script output="quiz:37+15">
  if ("@input" == "52") {
    true
  } else {
    "@input"
  }
</script>

<script style="display: block">
//   3(7)       (3)7
// + 1(5)     + (1)5       The first and second steps were correct,
// ------ ->  ------  ->   but the student forgot to carry the 1
//   (12)       (4)2       in the 10 digit column.

if ("@input(`quiz:37+15`)" == "42") {
  send.liascript(`## Maybe you forgot to carry...

Checkout the follow video to recap carrying.

!?[Carrying for larger digits](https://www.youtube.com/watch?v=VPsYRPdlIpU)
`)
} else ""
</script>

<script style="display: block">
//   3(7)       (3)7       The first and second steps were also
// + 1(5)     + (1)5       correct, but carrying was not provided
// ------ ->  ------  ->   properly, maybe there is a problem with
//   (12)      (4)12       understanding digit columns...


if ("@input(`quiz:37+15`)" == "412") {
  send.lia(`You are nearly there, there might be a problem with the 10 digit columns...`)
} else ""
</script>

#### Generic++

<!--
@article: <script output="@0" value="select" input="select" options="der|die|das|dem|den|des">
            if("@input(`articles`)" == "true") {
              "@1"
            } else {
              "@input"
            }
          </script>
-->

Ok, German articles behave strangely. This is a more complex example of a generic quiz that is connected to multiple scripts with an input, which are implemented with a single LiaScript macro.

Do you know which German articles belong to which gender in which case?

```
[[!]]
<script output="articles">
if ("@input" !== "true") {
  "@input(`11`)"=="der"  &&  "@input(`21`)"=="die"  &&  "@input(`31`)"=="das"  &&  "@input(`41`)"=="die" &&
  "@input(`12`)"=="des"  &&  "@input(`22`)"=="der"  &&  "@input(`32`)"=="des"  &&  "@input(`42`)"=="der" &&
  "@input(`13`)"=="dem"  &&  "@input(`23`)"=="der"  &&  "@input(`33`)"=="dem"  &&  "@input(`43`)"=="den" &&
  "@input(`14`)"=="den"  &&  "@input(`24`)"=="die"  &&  "@input(`34`)"=="das"  &&  "@input(`44`)"=="die"
}
</script>
```

| Case      | Masculine        | Feminine         | Neuter           | Plural           |
| --------- | ---------------- | ---------------- | ---------------- | ---------------- |
| Nominativ | @article(11,der) | @article(21,die) | @article(31,das) | @article(41,die) |
| Genitiv   | @article(12,des) | @article(22,der) | @article(32,des) | @article(42,der) |
| Dativ     | @article(13,dem) | @article(23,der) | @article(33,dem) | @article(43,den) |
| Accusativ | @article(14,den) | @article(24,die) | @article(34,das) | @article(44,die) |


The following code-block shows how this quiz was actually implemented.


