# pokemonAPI

Running Instructions:
------------------
1. Install docker on your machine
> https://www.thegeekdiary.com/how-to-install-docker-on-mac/
2. Download the code and extract the code - ensure to also extract the requiredFiles folder.
3. Open the command line shell
4. cd to the project directory
5. Type command: docker-compose up
> Wait until you see 'Watching for file changes with StatReloader' message in your console.
6. Open browser and run http://localhost:8000/pokemon/charizard/

Solution Approach:
------------------
1. We used Python as Programming language and DjangoRestFramework as application framework.
2. We are using REST API to return the response
One of the key advantages of REST APIs is that they provide a great deal of flexibility. 
Data is not tied to resources or methods, so REST can handle multiple types of calls, 
return different data formats and even change structurally with the correct implementation of hypermedia. 
This flexibility allows developers to build an API that meets your needs while also meeting the needs of very diverse customers.
3. Why choose Python/DjangoRestframework?
Django is an open-source python web framework used for rapid development, pragmatic, maintainable, clean design, and secure websites. 
A web application framework is a toolkit of all components needed for application development.
4. We used Docker to containerize the application. 
Docker containers encapsulate everything an application needs to run (and only those things), 
they allow applications to be shuttled easily between environments. 
Any host with the Docker runtime installed, be it a developer's laptop or a public cloud instance—can run a Docker container. 
We used Python 3.6 as base docker image and installed our application in that image. 
You can find the commands of how to setup the application in instructions.txt file.

Data Access Flow:
-----------------
When user enters the url(http://localhost:8000/pokemon/charizard/) and hits enter, the flow is as follows:
1. It goes to urls.py in pokemonrest/urls.py
2. The url is pointed to function pokemon_api in views.py
3. We take the name(charizard) from the url and call pokeapi url the https://pokeapi.co/api/v2/pokemon/<id or name>/
4. We get the json response from the API loop over the abilities json array.
5. Call each URL from the json array and create description string.
6. Return JSON data with 200 OK status code in the following format
{'name': <name>, 'description': <description formed from step6>}
