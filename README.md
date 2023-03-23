# PyWebview-Update-DOM-Elements-without-Javascript-knowledge
A quick way to update dom elements in html through Pywebview, a missing gap in their repo examples. 

#
Quickstart 1: In this updated template, the update function in the HTML document takes a value parameter that will be used to update the innerHTML of the content element.
#
```javascript 
<button onclick="update('')">Update content</button>
function update(value) 
  var element = document.getElementById('content');
  element.innerHTML = value;
```

```python
def update_element():
  new_value = "new_value"
  window.evaluate_js(f"update('{new_value}')")
```
The update_element function in Python calls the evaluate_js method on the PyWebview window object to execute the update function in the HTML document, passing in the new_value parameter as a string.

When the PyWebview window is created, the update_element function is called with the new value to update the content element with.

#
Quickstart 2: In this template, the HTML content includes an input field and a button with an onclick event that calls the sendInput function in Javascript.
#
```javascript 
<button onclick="sendValue()">Send Value</button>
function sendValue() {
  var element = document.getElementById('inputValue');
  var value = element.value;
  window.pywebview.api.send_value(value);
```


```python
class InputValueReceiver:
def send_value(self, value): 
  handle_input_value(value)
```

When the sendInput function is called, it gets the value of the input field and calls the send_input_to_python function in Python using the pywebview.api object.

The send_input_to_python function in Python is decorated with @window.expose_api to make it available to Javascript. This function simply prints the received input value to the console.

When the PyWebview window is created, the send_input_to_python function is registered with the PyWebview window object using the expose_api decorator.

When the "Send value to Python" button is clicked, the input value is sent to the send_input_to_python function in Python and printed to the console.




