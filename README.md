The project includes landing page in English, landing page in Arabic, home page in English. The css file for both landing pages is the same.

The language switcher changes a language and add a class to the block with class 'content' so it changes the direction of text writing.
However, the functionality can not be completed the arabic page should be displayed. The translation can be done with the backend part.

To use the html files it is enough to add the paths of them in the backend functions.

To translate the text in html files it is needed to put variables into markup. The names of variables are taken from the backend side.
To translate the files using Twig yaml file may be used. So we need to provide the path of html file and the language to the backend server 
and there a function will be invoked and return the namespace for the specific language. It looks like { traslation.en.mainTitle }



Some tips regarding development:

When I tried to follow the principle of pixel perfect, I had some conflicts with the css rules in Sigma. I asked Anastasia about it. She answered that I should take the alternative option to combine both of them.

The validation of the phone number was performed by checkings in javascript, however it is possible to do it right in html. Also I added the title with the phone format as a prompt for users. I relied on the screen with successful phone number. The design with placeholder with “XXX XXX XXX” does not match the real phone number on the next slide “0398-3388155”. So I would specify it with the team. As I do not have this opportunity, I made the decision on my side. I suppossed that the phone number should contain only numbers and its length must be 9.

As it was not mentioned in the task, the validation of the phone number (as the validation of the pin code) was added per removing focus from input field which is responsible for the phone, because according to the desings we need to have an opportunity to click on “GET OTP” button to trigger the sending sms event to get pin code. Additionally I implemented the validation for key up event with pause of 4 sec. Although it is possible to add the validation to any step so it is better to discuss the user scenario with the team.

We have two buttons with classes button-ref in landing page.html. It was not mentioned in the task what functionality should be for them. If we need to forward a user to the other pages, we can use references with tag a. If we need to display a new block or form on the same page, it is enough to use onclick event handler.

In the arabian version I could not identify the reference ‘My account’ from the english one. So the corresponding element is absent in the arabian version. I would ask for that my colleagues in the real project. Somehow the ‘Read more’ block is shown differently from the design, however I copied it line by line.

The buttons ‘Contact us’ and ‘FAQ’ are implemented in tag button. If we need to forward a user to another page by clicking on them, it is better to use references with tag a. If we need just to perform some actions, for instance, displaying some forms or blocks, do some server requests, it is better to use button tags.



As for format the html files into Twig ones, it is a good practise to put the cycles, if operators with Twig syntax.
For instance, we could put building of list ul with class 'games-list' in cycle instead of the images list markup in home page.

<ul id="games-list">
  {% for game in navigation %}
    <li class="list-element">
      <img src="{{ game.src }}" alt="{{ game.name }}" />
    </li>
  {% endfor %}
 </ul>

Additonally we can put a condition with 'if' to display new games block or popular games block.
