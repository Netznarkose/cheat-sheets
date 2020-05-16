## Regular expressions  

###  blacklist everything but upcase chars  
```ruby
'string' !~ /[^A-Z]/
```
###  blacklist everything but case-insensitive chars  
```ruby
'string' !~ /[^a-z]/i
```
###  blacklist everything but case-insensitive chars, numbers and whitespace  
```ruby
'string' !~ /[^a-z0-9]\s/i
```

## Operators
### .eql? versus ==

```ruby
1 == 1.0     #=> true
1.eql? 1.0   #=> false
```
