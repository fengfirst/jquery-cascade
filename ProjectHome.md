## Jquery CascadeSelect ##
A brief documentation while I put together the more formal one ... something that may never happen due to my procrastinating nature.

## Firing it up ##
All you need to fire up the plugin is this bit:

```
$(document).ready(function() {
            $('#source').cascade({
                source: "/List/GetOptions/",
                cascaded: "dependent"
            });
        });
```

Where "dependent" is the id of the dependent select list. I added a few more options tho to make it more customizable.

```
$(document).ready(function() {
            $('#source').cascade({
                source: "/List/GetOptions/",
                cascaded: "dependent",
                dependentNothingFoundLabel: "No elements found",
                dependentStartingLabel: "Please select one",
                dependentLoadingLabel: "Loading ...",
                extraParams: { extra: getExtra },
                spinnerImg: "/Images/Spinner.gif"
            });
        });
```

I guess all options are self-explanatory except for the last two. In case you need to send additional data with the request you'd use the extraParams object, in this case I made a stub reference to a function called getExtra which will be evaluated with every request. If you want to give the user some sort of visual cue while the data loads you can use a spinner image from ajaxload.info and pass the url as I did in the sample.

## What does it expect from the server? ##
A json formated object like this one:
```
[{"label":"Option 1","value":1},{"label":"Option 2","value":2}]
```
And that's it, feel free to contact me with any comments, questions or suggestions you may have.