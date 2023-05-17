Thoughts about code:
====================

The code is written neatly with comments. The snippet seems to belong to a booking application for a translator.
Further we can add up more love to the code as follows with its respective reason.

BookingController
=================

* Use type hints for better code readibility
* Use nullish coalescing operator and ternary operators carefully.
* Avoid using generic or ambigous variable names like $data. As modified in method distanceFeed, the $data array has been renamed to $distanceFeedData for clarity.
* Assuming the controller is an API, the response should be returned as JSON.
* In the response, the status of the process, the message and the data should be returned separately and in case of exception handlings, the response headers and response code should also be send as per the response.
* Arrays elements for large arrays should be indented properly for readibilty.
* While handling exceptions, a log should be maintained either on files or database. This makes easier for debugging the code in production mode.

BookingRepository
=================

* Use constants in the repository. This would help to modify the path or other information in future and rework can be avoided. For example, the path of the logs can be declared as a constant and shall be changed in future without going to every line where it is used.
* The conditional statements should be less complex. In the method store(), the conditions are quite complex and can be handled with switch/case instead.
* Use nullish coalescing operator and ternary operator where needed instead of using multiple conditions to save lines of code.
* helpers like filter can used instead to make the code more readable and more performance oriented.
* The OneSignal API key and app ID can be stored in env files instead. This would make sure the reusability of the information.
* We can use clients like Guzzle HTTP for making curl calls instead of using curl functions. This will make the code more maintainable and allow you to handle errors and exceptions more easily. Alternatively if we are compelled to use php native curl then we can define the configuration in a single array.
* There are some methods which are common in many functions. We can extract those common methods and create a new method for reusability and better readibility. This scales the application when we are developing Restful API.
* Validations should be added to the public methods.

