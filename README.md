# Docker Compose for Omeka S and Neatline 3

1. Clone this repo.
2. Init submodules
   `git submodule update --init --recursive`
   or if you need to update the contents of the submodules
   `git submodule foreach --recursive git pull origin master`
3. `docker-compose down`
3. `docker-compose up`
4. Visit http://localhost:9000 and fill out the Omeka S form.
