UI-Input-Validator
==================

validate your user data very easily with UI-Input-Validator light weight plugin.

Create the group of all input text boxes using html5's "data attribute", which you want to validate under one group,like
    
    <input type="text" data-input-group="reg-from" data-req-message="First name is required" data-secondary-check="onlyLetters">
	<br>
	<br>
	<input type="text" data-input-group="reg-from" data-req-message="Last name is required" data-secondary-check="onlyLetters">
    
    here "data-input-group" attribute specifies the group of textboxes validate under one group.
    
    In above example "data-req-message" specifies the required message to be shown for perticular input textbox,
    and "data-secondary-check" specifies the any secondary level validation to be performded after required validation succeeds.
    
    Also use the same group name for button against which you want to validate user input in the group of input textboxes,
    
    <input type="button" data-input-group="reg-from" value="click me" data-disable-on-load="true">
    
    here "data-input-group" is set to same value as above textboxes. Also "data-disable-on-load" this attribute is used to 
    enable/diable button on page load, set true(Recommended) to disable by defualt.
    
Some points:
    1) Its not neccesory to have html form element to use this framework.
    2) It uses jquery library.
    3) It jquery validation-engine's CSS.
    4) You can second-level on the fly, so you have to add reGex and error message to be shown for your second level validation in inputValidator.js as below,
    
    /*
     * key: value pair for validationType: corresponding regex.
	 */
	var patterns = {
		"telephone": /^\+([0-9]{2})\-([0-9]{10})$/,
		"multiEmail": /^(([A-Za-z0-9_\-\.])+\@([A-Za-z0-9_\-\.])+\.([A-Za-z]{2,4})+\,(\s)?)*(([A-Za-z0-9_\-\.])+\@([A-Za-z0-9_\-\.])+\.([A-Za-z]{2,4}))+$/,
		"singleEmail": /^(([A-Za-z0-9_\-\.])+\@([A-Za-z0-9_\-\.])+\.([A-Za-z]{2,4}))+$/,
		"onlyLetters": /^[a-zA-Z ]*$/,
		"onlyNumbers": /^[0-9]+$/
	};

	/*
	 * key: value pair for validationType: corresponding info/error message.
	 */
	var messages = {
		"telephone": "Please enter valid telephone number",
		"singleEmail": "Invalid email address",
		"multiEmail": "Invalid email address, you can add multiple ',' separated addresses",
		"onlyLetters": "Only letters allowed",
		"onlyNumbers": "Only numbers allowed"
	};
    
    
Initially set your button disable
