# Ruby Playbook

## Code Structure

### Module and Class Metaprogramming

#### Dynamic Module and Class Access

When accessing a module or class with a namespace that was dynamically created you can check for validity via safe_constantize method

```ruby
# From https://apidock.com/rails/String/safe_constantize
'Module'.safe_constantize  # => Module
'Class'.safe_constantize   # => Class
'blargle'.safe_constantize # => nil
```

This could be used to raise an error if the namespace does not exist:

```ruby
class = 'Module::Class'.safe_constantize
raise SomeError if class.nil?
```
