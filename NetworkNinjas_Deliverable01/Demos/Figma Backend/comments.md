# Figma Backend Architecture
The added screenshot visualizes how we have set up the backend at the moment. We have a docker network
in which we include all our microservices. At the moment we have one for Authentication, Users and Posts
as well as one for the Frontend. These four microservices are inside a docker compose. Additionally, to enable
an easier communication via ports we are using Kong in its own docker compose (to keep things nicely separated).\
Kong enables us to communicate via one port (i.e., 8000) and efficiently assigns the respective calls to the 
corresponding microservice.\
We also decided to keep the microservices Authentication and User separate to be able to still use each in case the other
is not reachable, however, for easier communication they are using the same database.\
We plan on adding more microservices corresponding to the additional features mentioned in the user stories and requirements.