# Bootstrap Demo

This repository is a demo of some of the features that bootstrap offers for developers, which makes it easy to create effortlessly stylish and cohesive websites with a modern feel.

Run a development server to actively update as changes are made using the script `start_server.sh`.

## Development steps

- `index.html.erb` contains a basic website with almost no bootstrap (other than a small amount of styling with flex to make layout consistent)
- `list-group.html.erb` adds a nicer navbar (contained in the `_navbar_nice.erb` partial) and uses the list-group css class to add some styling to our lists to make them look somewhat more modern
- `card.html.erb` adds a bootstrap "card" container which has space for a picture, text, and link. All we need to do is set our current div to use that class and now we can have an even nicer looking page