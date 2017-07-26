## Detailed Steps for Lab 1
Follow these instructions to complete the work demonstrated in today's first lab. 

#### Steps

1. Change the skill name and invocation name to match your town.  For instance, name it "Boston Guide" and make the invocation "boston guide"
1. Click on Interaction Model to open the skill builder tool. 
1. Click save on the top left, then click build model.
1. In aws.amazon.com, open lambda console, find "Local Recommendations" and click on the name
1. Update each line item in the data variable as needed to be representative of your city of choice.
1. The weather API shouldn’t require update. We just updated the info in our data object, which will now be used by our API call.
1. Go back to developer.amazon, click 'test' in the box on the left, then scroll your page to the service simulator section.
1. Type the word dinner in the Enter Utterance box.
1. Below the Lambda Response box on the the right, click 'Listen'.
1. Type ‘yes’ for more details from your skill.
1. Type 'go outside' to ensure we're getting the current weather in our newly-changed city.  
