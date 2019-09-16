# Docker on rails

This app is the example used in my blog post: http://brunozrk.github.io/rails-app-with-docker-for-development/

### Running:
```
# clone repo
git clone git@github.com:brunozrk/docker_on_rails_dev.git

# enter docker_on_rails_dev repo
cd docker_on_rails_dev

# run compose
docker-compose up -d

# connect to rails app container
docker-compose exec web bash

# now is nothing but what you always did

# run bundle install
bundle install

# setup database
rake db:create db:migrate db:seed

# run server
rails s -b 0.0.0.0

# open other terminal and test
curl localhost:3000/beers | json_pp

# you can also attach another terminal to container and open the console
docker-compose exec web bash
rails c
```

