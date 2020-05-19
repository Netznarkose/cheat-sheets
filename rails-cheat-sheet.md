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

### make routes accessible in console  

```ruby 
include Rails.application.routes.url_helpers
users_path #=> '/users/
```
