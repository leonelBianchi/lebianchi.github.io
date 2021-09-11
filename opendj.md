---
layout: default
title: OpenDJ
permalink: /opendj/

---

<script>
        /* Create a titile called Select a DJ and play its music at random! */
    var title = document.createElement('h1');
    title.innerHTML = 'Select a DJ and play its music at random!';
    document.body.appendChild(title);

    /* Create two persons with its name and image: */
    var person1 = document.createElement('div');
    person1.innerHTML = '<img src="https://www.w3schools.com/howto/img_avatar2.png" alt="Avatar" style="width:100px;height:100px;">';
    person1.innerHTML += '<h2>DJ1</h2>';
    document.body.appendChild(person1);
    var person2 = document.createElement('div');
    person2.innerHTML = '<img src="https://www.w3schools.com/howto/img_avatar2.png" alt="Avatar" style="width:100px;height:100px;">';
    person2.innerHTML += '<h2>DJ2</h2>';
    document.body.appendChild(person2);

    /* Name: Hernan Cattaneo */
    var hernan = document.createElement('div');
    hernan.innerHTML = '<h3>Hernan Cattaneo</h3>';
    document.body.appendChild(hernan);

    /* Image: https://ege.electronicgroove.com/wp-content/uploads/2019/08/Hernan-Cattaneo.jpg */
    var hernanImage = document.createElement('img');
    hernanImage.src = 'https://ege.electronicgroove.com/wp-content/uploads/2019/08/Hernan-Cattaneo.jpg';
    hernanImage.alt = 'Hernan Cattaneo';
    hernanImage.style.width = '100px';
    hernanImage.style.height = '100px';
    document.body.appendChild(hernanImage);

    /* Name: deadmau5 */
    var deadmau5 = document.createElement('div');
    deadmau5.innerHTML = '<h3>deadmau5</h3>';
    document.body.appendChild(deadmau5);

    /* Image: https://i1.wp.com/socialgeek.co/wp-content/uploads/2014/05/Deadmau5-aplicacion-movil.jpg?resize=1000%2C600&ssl=1 */
    var deadmau5Image = document.createElement('img');
    deadmau5Image.src = 'https://i1.wp.com/socialgeek.co/wp-content/uploads/2014/05/Deadmau5-aplicacion-movil.jpg?resize=1000%2C600&ssl=1';
    deadmau5Image.alt = 'deadmau5';
    deadmau5Image.style.width = '100px';
    deadmau5Image.style.height = '100px';
    document.body.appendChild(deadmau5Image);

    /* Remove the two persons */
    document.body.removeChild(person1);
    document.body.removeChild(person2);

    /* Add a dropdown with these options: Hernan Cattaneo and deadmau5 */
    var dropdown = document.createElement('select');
    dropdown.innerHTML = '<option value="hernan">Hernan Cattaneo</option>';
    dropdown.innerHTML += '<option value="deadmau5">deadmau5</option>';
    document.body.appendChild(dropdown);

    /* Add a select button */
    var selectButton = document.createElement('button');
    selectButton.innerHTML = 'Select';
    document.body.appendChild(selectButton);

    /* When hit the select button, only show the name and image of the selected person */
    selectButton.addEventListener('click', function() {
    var selected = dropdown.options[dropdown.selectedIndex].value;
    if (selected == 'hernan') {
        document.body.removeChild(deadmau5);
        document.body.removeChild(deadmau5Image);
        document.body.appendChild(hernan);
        document.body.appendChild(hernanImage);
    } else if (selected == 'deadmau5') {
        document.body.removeChild(hernan);
        document.body.removeChild(hernanImage);
        document.body.appendChild(deadmau5);
        document.body.appendChild(deadmau5Image);
    }
    });
    /* Round the images */
    hernanImage.style.borderRadius = '50%';
    deadmau5Image.style.borderRadius = '50%';

    /* Center the content */
    document.body.style.textAlign = 'center';

    /* Make the dropdown and button fancy */
    dropdown.style.border = '1px solid black';
    dropdown.style.padding = '5px';
    selectButton.style.border = '1px solid black';
    selectButton.style.padding = '5px';

    /* Add a brief description of the character selected */
    var description = document.createElement('div');
    description.innerHTML = '<h3>Description</h3>';
    document.body.appendChild(description);

    /* Hernan Cattaneo: DJ from Argentina. Creator of Resident. */
    var hernanDescription = document.createElement('div');
    hernanDescription.innerHTML = '<p>Hernan Cattaneo is a DJ from Argentina. He is the creator of the music label, <a href="https://www.residentadvisor.net/label/2405-resident">Resident</a>.</p>';
    document.body.appendChild(hernanDescription);

    /* deadmau5: DJ from Canda, Creator of Strobe */
    var deadmau5Description = document.createElement('div');
    deadmau5Description.innerHTML = '<p>deadmau5 is a DJ from Canda. He is the creator of the music label, <a href="https://www.residentadvisor.net/label/2405-resident">Strobe</a>.</p>';
    document.body.appendChild(deadmau5Description);

    /* When hit the select button, only show the description of the selected person */
    selectButton.addEventListener('click', function() {
    var selected = dropdown.options[dropdown.selectedIndex].value;
    if (selected == 'hernan') {
        document.body.removeChild(deadmau5Description);
        document.body.appendChild(hernanDescription);
    } else if (selected == 'deadmau5') {
        document.body.removeChild(hernanDescription);
        document.body.appendChild(deadmau5Description);
    }
    });

    /* Remove the "Description" word */
    document.body.removeChild(description);

    /* Add a link to a youtube video of the selected character: */
    var youtube = document.createElement('a');
    youtube.href = 'https://www.youtube.com/watch?v=dQw4w9WgXcQ';
    youtube.innerHTML = '<h3>Youtube</h3>';
    document.body.appendChild(youtube);

    /* Hernan Cattaneo: https://www.youtube.com/watch?v=KbhSZor6C1g */
    var hernanYoutube = document.createElement('div');
    hernanYoutube.innerHTML = '<p>Hernan Cattaneo: <a href="https://www.youtube.com/watch?v=KbhSZor6C1g">https://www.youtube.com/watch?v=KbhSZor6C1g</a></p>';
    document.body.appendChild(hernanYoutube);

    /* deadmau5: https://www.youtube.com/watch?v=tKi9Z-f6qX4 */
    var deadmau5Youtube = document.createElement('div');
    deadmau5Youtube.innerHTML = '<p>deadmau5: <a href="https://www.youtube.com/watch?v=tKi9Z-f6qX4">https://www.youtube.com/watch?v=tKi9Z-f6qX4</a></p>';
    document.body.appendChild(deadmau5Youtube);

    /* When hit the select button, only show the youtube link of the selected person */
    selectButton.addEventListener('click', function() {
    var selected = dropdown.options[dropdown.selectedIndex].value;
    if (selected == 'hernan') {
        document.body.removeChild(deadmau5Youtube);
        document.body.appendChild(hernanYoutube);
    } else if (selected == 'deadmau5') {
        document.body.removeChild(hernanYoutube);
        document.body.appendChild(deadmau5Youtube);
    }
    });

    /* Remove the "Youtube" word */
    document.body.removeChild(youtube);

    /* Create a dark background but body background keep it white */
    document.body.style.backgroundColor = 'black';

    /* Make text white */
    document.body.style.color = 'white';

    /* Change deadmau5 image to: https://i.ytimg.com/vi/O1Bi3tS1Aa4/maxresdefault.jpg */
    deadmau5Image.src = 'https://i.ytimg.com/vi/O1Bi3tS1Aa4/maxresdefault.jpg';

    /* Make it italics */
    notravarius.style.fontStyle = 'italic';

    /* Add a footer: created by notravarius */
    var footer = document.createElement('div');
    footer.innerHTML = '<p>created by notravarius</p>';
    document.body.appendChild(footer);

    /* Put the footer at the bottom */
    footer.style.position = 'absolute';
    footer.style.bottom = '0';

    /* Center the footer */
    footer.style.textAlign = 'center';

</script>





