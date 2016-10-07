# CMS Generic test

## 1. Using less, create a link using this style. It should as reusable and flexable as possible.

![Inline Select](https://github.com/ovotech/interview-tests/blob/master/cms-generic/button.png)

<details>
  <summary>Answer</summary>
* http://codepen.io/anon/pen/EgoJgz
* Check to see how they made it reusable with classes - can the color be changed with another class?
* How did they add the emoji - using pseudo selectors would be best.
* How did they deal with the border? A dotted border and a solid box shadow would be best.
* Did they use text-transform for the uppercase text.
</details>

## 2. Without changing the markup, what are some ways you could you target the middle `li` with css?

    <ul class="what-a-great-list">
      <li title="a">This list</li>
      <li title="b">is totally</li>
      <li title="c">amazing!!</li>
    </ul>

<details>
  <summary>Answer</summary>

    .what-a-great-list > li:nth-child(2)

    -- or --

    .what-a-great-list > li[title="b"]

    -- there are others --
</details>

## 3. What css will the following less output?

    @brand-primary: black;
    .primary-thing {
      color: @brand-primary;
    }
    .my-element {
      &:extend(.primary-thing);

      &,
      &:hover {
        text-decoration: @text-decoration;
      }
    }
    @text-decoration: none;


<details>
  <summary>Answer</summary>

    .primary-thing,
    .my-element {
      color: #000000;
    }
    .my-element,
    .my-element:hover {
      text-decoration: none;
    }
</details>

## 4. Define a "repeatify" function on the String object.

    console.log('hello'.repeatify(3));

    // Should return hellohellohello.

<details>
  <summary>Answer</summary>

    String.prototype.repeatify = String.prototype.repeatify || function(times) {
       var str = '';

       for (var i = 0; i < times; i++) {
          str += this;
       }

       return str;
    };

The question tests the knowledge of the developer about inheritance in JavaScript and the prototype property. It also verifies that the developer is able to extend native data type functionalities (although this should not be done).
</details>

## 5. Please create the following function.

    var wordCount = function (sentence) {
        // your implementation
    };

    var sentence = 'You shake my nerves and you rattle my brain';
    var words = wordCount(sentence);

    /*
        {
            and: 1,
            brain: 1,
            my: 2,
            nerves: 1,
            rattle: 1,
            shake: 1,
            you: 2
        }
     */
<details>
  <summary>Answer</summary>

    var wordCount = function (sentence) {
        let words = sentence.split(" ");
        let wordCount = {};

        words.forEach((word) => {
            word = word.toLowerCase();
            wordCount[word] = (wordCount[word]) ? wordCount[word] + 1 : 1;
        });

        return wordCount;
    };
</details>
