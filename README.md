**Naming the Files:**

To name the file, list the "session-ID", the "user-ID" and the "modeling formalism". Separate them with "-". 

For example:
sessionID-UserID-modelingFormalism

**Specific of the txt**

In the text, always place the llm_prompt and llm_response in square brackets. For the previous "columns", it must be a space, then one word, then space. Always skip a line before the first curly bracket of the dictionary. Here is an example of the format (the skipped line from the dictionary doesn't show).

S001 , U123 , 2023-07-24 12:22:54.311 , UML , OnTrigger , session_start , start , blank , [product[], list] , [1, 2, 3, r, t] , 
{
    "metadata": {
      "editing_context": "e8d6b1",
      "model_id": "a3f9c2"
    },
    "suggestions": [
      {
        "frequency": 2,
        "id": 1,
        "data": {
          "$type": "UML:Class",
          "name": "Product",
          "$container": "b1d2a7",
          "$relation": {
            "$source": "b1d2a7",
            "$name": "association",
            "$target": "c7f3e8"
          }
        }
      }
    ]
  }


If you need an empty cell, refer to it as "[]" under llm_prompt and llm_response, refer to it as "{}" for suggestion_list, and any other "column" can be blank " ".

Always put the items in this order
session_id, user_id, timestamp, modeling_formalism, element_type, event_type, event_subtype, action_taken_by_user, llm_prompt, llm_response, Suggestions List



**start of a session**

When you're starting a session, associated with the right timestamp: write "session_start" in the fifth (event_typt) column. Similarly, write "session_end" with the last timestamp that the session was active. This is for the metric of duration of session.


**rate metrics**
make sure the event type is " suggestion "

for accepted suggestions, make sure the action_taken_by_user is " accepted "

for modified suggestions, make sure the action_taken_by_user is " modified "

for accepted suggestions, make sure the action_taken_by_user is " rejected "





