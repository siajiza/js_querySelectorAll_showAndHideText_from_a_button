# **QuerySelectorAll**

    The Document method querySelectorAll() returns a static NodeList, representing a list of the document's elements that match the specified group of selectors of CSS.

**SYNTAX**

    const matches = document.querySelectorAll("element"); 

**On Console**

    NodeList(2) [div.mainHeading.showElement, div.subHeading.showElement]
        0: div.mainHeading.showElement
        1: div.subHeading.showElement
        length: 2
        [[Prototype]]: NodeList

**HOW WORKS _"querySelectorAll"_ IN OUR EXAMPLE CODE**

**Behavior**

    We are looking for on this example to show or hide the Main Title and the subtitle. 

    To find down that we´re gonna build a button where we´ll click on it and make this two actions; show and hide text are intertactives.

    We part first, from three language code locations;

    -html
    -css 
    -js

    Each one are going to contribute with part of the code 
    to create interact between them.

_To find this interact, we need to call with specific class and id names inside of each element, regardless of whether it is html or css. And from javascript we call this elements to the action._

**CSS**

Two different behaviors from each "onclick":

        .hideElement {
          visibility: hidden;
        }
    
        .showElement {
          display: block;
        }


**HTML**

We must build a two parts:

1. First part

The elements wich are gonna be used  on the behavior will be itered from forEach() and to find them that all of the elements must be called from the same name class or integreted on that name this especific word on the class on html.

In this case, this especific word will be **"showElement"**.


    <div class="mainHeading showElement">
      <h1>Hi there People!</h1>
    </div>
    
    <div class="subHeading showElement">
      My Amazing subheading...
    </div>

2. Second part

The button must be "onclick=contentToggle()", and this toggle function will be used on Javascript funtion to find the interaction.

    <button onclick="contentToggle()">Toggle Content</button>
<button onclick="contentToggle()">Toggle Content</button>

**JAVASCRIPT**

In this first step we build a variable that call the element where we´re gonna build the interaction.

    const headings = document.querySelectorAll('div');

On the second step, we´re gonna build the function on how is gonna show or hide the text. "onclick".    

    function contentToggle() {

On the third step, we´re gonna code the iteration with forEach() to go over each elements where have the name class "showElement".

        headings.forEach((heading) => {
            if (heading.classList.contains('showElement')) {

On the fourth step, we´re gonna build the behavior using the "class" comes from html and the CSS.

            if (heading.classList.contains('showElement')) {
                heading.classList.remove('showElement');
                heading.classList.add('hideElement');
            } else {
                heading.classList.remove('hideElement');
                heading.classList.add('showElement');
            }
        })       
    };

