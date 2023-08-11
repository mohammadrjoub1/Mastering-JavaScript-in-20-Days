# day#6 2023-8-11
# data fetching section:
- video#1:load data from an API endpoint on the internet. If the request is successful.
- video#2:working with promises pending......
- video#3:using the await operator to wait for a Promise and obtain its resulting value.

  # destructing data section 2023-8-11
  - video#1:destructuring as a method to declare multiple variables at once by retrieving the values from the parent object.
  - video#2:complete the getBreedFromURL function with destructuring and the .string() method.
  - video#3:returning the unformatted breed name from the given URL
  - video#4:formatting the returned breed name using the .split() method. Brief demonstrations of the .reverse() and .trim() methods are also provided in this segment..

    # async section:
    - video#1:combining async fetching and parsing the resulting code into a single function to create an async function. The async function also needs to be awaited to retrieve the contents of the returned promise.

    - video#3:Create a button element for each choice in the choicesArray, attach a click event listener with the buttonHandler function, and append the button as a child of the options element.
      ## WRAPPING ALL THE WORK !
      

  # Modules section:
  - video#1:splitting large codebases into multiple smaller files using modules. The differences between JavaScript and module JavaScript, including await, scope, import, and export, are also covered in this segment.
  - video#2:q&&a
  - video#3: how to provide more information on bugs and errors using console.log, .warn(), .error(), and the console's debugger.
  - video#4: showing multiple ways of setting breakpoints to assist in finding errors.
  - video#5: error handling using try catch blocks to be aware of potential errors and then manage them if they occur.
  - video#6:recommendations for next steps.
  - video#7:answering student questions regarding how to think about programming paradigms in JavaScript and if companies are more often using pure JavaScript or JavaScript with a framework such as React.


# Project : 
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="index.css">
    <style>
        * {
            padding: 0px;
            margin: 0px;
        }

        body {
            background-color: gainsboro;
            font-family: Verdana, Geneva, Tahoma, sans-serif;
        }

        .title {
            color: black;
            font-size: 48px;
            text-align: center;
            margin: 40px;
        }

        .character-list {
            list-style: none;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            padding: 0;
        }

        .character-item {
            width: 30%;
            border: 1px solid black;
            margin: 10px;
            padding: 10px;
            background-color: white;
        }

        .character-image {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <h1 class="title">Rick & Morty Character List!</h1>
    <ul class="character-list" id="characterList"></ul>
    <p class="error" id="errorMessage"></p>

    <script type="module">

        async function fetchData() {
            try {
                let characterData = await fetch("https://rickandmortyapi.com/api/character?status=alive");
                if (!characterData.ok) {
                    throw new Error("Error fetching data");
                }
                let characterList = await characterData.json();
                displayCharacterList(characterList.results);
            } catch (error) {
                document.getElementById("errorMessage").textContent = "An error occurred: " + error.message;
            }
        }

        function displayCharacterList(characters) {
            const characterList = document.getElementById("characterList");

            characters.slice(0, 50).forEach(character => {
                const li = document.createElement("li");
                li.className = "character-item";
                li.innerHTML = `
                        <h2>${character.name}</h2>
                        <img class="character-image" src="${character.image}" alt="${character.name}">
                        <p><strong>Location:</strong> ${character.location.name}</p>
                        <p><strong>Species:</strong> ${character.species}</p>
                        <p><strong>Gender:</strong> ${character.gender}</p>
                    `;
                characterList.appendChild(li);
            });
        }

        fetchData();

    </script>
</body>
</html>
