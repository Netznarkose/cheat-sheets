# Rails
### schema:load versus migrate
`db:schema:load` sets up database from schema.rb file deleting all data  
`db:migrate` sets up database structure from db/migrations sustaining all data  


### Search only user defined methods of object  
`exception.methods - Object.methods`  
### disable active-record validation
`image_asset_link.save(validate: false)`   

### View entire Pry-history
`cat ~/.pry-history`	

### make url_helpers accessible in rails console  

```ruby 
include Rails.application.routes.url_helpers
users_path #=> '/users/
```

## Eager Loading (Preloading)
```ruby
# fetch Producttests and preload associated model Participants on the fly  
pt = Bl::Producttest.preload(:participants)

# check that Participants go loaded
pt.first.association_cache.keys # => [:participants, :participation_requests]
```
