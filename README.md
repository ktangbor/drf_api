This project is for practise purposes, it is on-going and improvements are made till now.

The goal of this project is to design and implement an API for a company that 
wants to provide a platform in which programmers state up to three
programming languages that they have expertise on (together with their level i.e.
“beginner”, “experienced”, “expert”), so that they are publicly reachable to contribute to
open-source projects that anyone can submit. 
Programming languages options would be: C++, Javascript, Python, Java, Lua, Rust, Go, Julia.

This REST API has endpoints for the users to:
● Allow for the registration of their principal information, such as first_name, last_name,
email, age, country, residence, username
● Reset their password (if they are already registered).
● Add / Remove a skill (3 skills can be registered at any time)
● Create a new project and look for collaborators (see below)
● Get projects with open seats and express their interest for the corresponding pools.

For the open-source projects there are API endpoints for:
● A registered user to create a new project with the following information: project_name,
description, maximum_collaborators, collaborators.
● The completion or deletion of a project from the corresponding user.
● Accepting or declining the interest of another user to take part in the project. 
    Only the username, email and skills of the collaborators are visible to the
    original “creator” of the project.

To run the project, you can execute "docker-compose up -d --build" 
in GV_RDF/backend. You must have docker installed.

Please refer to the GV_RDF/backend/gv_rdf/urls.py for the endpoints 
that have been created and how to call them. 
You can call them using CURL / Postman, or alternatively use the 
included 'app' container (after building it) which contains httpie.

The existing testing units function as an example on how to build them, 
the possible testing scenarios are numerous, from the access and permissions 
of the users, to the actual testing of the implemented workflow, to use-cases 
like accepting a collaborator who showed interest in a project twice. 

The main app (api) is the 'gv_rdf' package.
The package 'core' contains the logic and endpoints for user registration.
The package 'projects' contains the logic and endpoints for project creation and 
management (like adding collaborators or user expressing interest in a project). 

Finally, the database (sqlite3) is empty, but there is a superuser with credentials [admin : 12345!@#$%]
