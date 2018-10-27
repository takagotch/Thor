### Thor
---
https://github.com/erikhuda/thor
https://github.com/erikhuda/thor/wiki


```
gem install thor

thor app:install myname --force


```


```ruby
class Test < Thor
  desc "example", "an example task"
  def example
    puts "I'm a thor task!"
  end
end

class Test < Thor
  desc "example FILE", "an example task that does someghing with a file"
  def example(file)
    puts "You suppied the file: #{file}"
  end
end

class Test < Thor
  desc ""
  method_option :delete, :aliases => "-d", :desc => "Delete the file after parsing it"
  def example(file)
    puts "You supplied the file: #{file}"
    delete_file = options[:delete]
    if delete_file
      puts "You specified that you would like to delete #{file}"
    else
      puts "You do not want to delete #{file}"
    end
  end
end



```

```
Usage:
  thor test:example FILE
an example task that does something with a file

test
---
thor test:example

Usage:
  thor test:example FILE
Options:
  -d, [--delete=DELETE]
an example task


```
