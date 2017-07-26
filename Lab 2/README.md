
### Lab 2: Add a new Intent with Slot
Review the Intent called AttractionIntent.  It has a slot called "distance" which is defined as type ```AMAZON.NUMBER```

The sample utterance looks like this:

```AttractionIntent recommend an attraction within {distance} miles```

Within the Lambda code, we access the value of this slot via the following code:

```
        var distance = 200;
        if (this.event.request.intent.slots.distance.value) {
            distance = this.event.request.intent.slots.distance.value;
        }
```
We have code that validates the distance and substitutes a default distance in case the user says something that matches the Intent but they fail to say the slot value.


Add a new Intent and Slot of your own!  Just think of a new question a user might ask.  Give the question an Intent name.
Within the question, identify a slot that behaves like a variable, wildcard, or parameter.
You can plan to use slot types such as ```AMAZON.US_STATE```, ```AMAZON.US_FIRST_NAME```, ```AMAZON.MusicGroup```, etc.
See the [full list](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/built-in-intent-ref/slot-type-reference).

You can also create your own slot type within the Interaction Model page.
For example, you could create a slot type called LIST_OF_BIRDS with values "cardinal", "blue jay", "robin", etc.
Once this list has been created, you could define a new slot called "bird" that is type LIST_OF_BIRDS.

**Within your Lambda code, copy the format of the ```AttractionIntent``` function definition to create a new handler with the same name as your new Intent.**

**Customize the logic in your handler to retrieve the slot value, and add logic to say a response back to the user.**

