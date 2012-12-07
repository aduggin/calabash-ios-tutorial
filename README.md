# Calabash iOS Tutorial

Setup your project for Calabash-iOS

	calabash-ios setup
	
Generate a skeleton features folder for your tests

	calabash-ios gen

Enable accessibility in the iOS Simulator
	
	calabash-ios sim acc

Start up the calabash console
	
	calabash-ios console
	

## Predefined Steps

Things you can do:

* see
* fill in
* enter
* clear
* touch
* toggle
* swipe
* scroll
* pinch
* wait
* take picture

Uses the Accessibility Labels (which can be seen using the Accessibility Inspector)

Step | Descripiton | Notes |
---- | ----------- | ----------- |
Then I should see "First View" | Confirm the presence of some text | insert
Then I should not see "foo" | insert | insert
Then I should see a "login" button | insert | insert
Then I should see a "Name" input field | insert | insert
Then I fill in "Name" with "Alistair" | insert | insert
Then I clear "Name" | insert | insert
Then I clear input field number 1 | insert | insert
Then I touch "login" | Touch an arbitrary view with the accessibility label "login" |
Then I touch the "login" button | Touch a button with the accessibility label "login" | insert
Then I touch button number 1 | Touch the first button | insert
Then I touch done | insert | insert
Then I touch search | insert | insert
Then I touch the user location | insert | insert
Then I touch on screen 100 from the left and 250 from the top | insert | insert
Then I toggle the switch | insert | insert
Then I toggle the "switch" switch | insert | insert
Then take picture | Take a screenshot | This will generate a .png prefixed with the step number
Then I wait to see "text or label" | insert | insert
Then I wait for "text or label" to appear | insert | insert
Then I wait until I don't see "text or label" | insert | insert
Then I wait to not see "text or label" | insert | insert
Then I wait for the "login" button to appear | insert | insert
Then I wait to see a navigation bar titled "title" | insert | insert
Then I wait for the "label" input field | insert | insert
Then I wait for 2 input fields | insert | insert
Then I wait | Wait for 2 seconds | insert
Then I wait and wait | Wait for 4 seconds | insert
Then I wait and wait and wait... | Wait for 10 seconds | insert
Then I wait for 2.3 seconds | Wait for 2.3 seconds | specify any arbitrary number of seconds
Then I go back | insert | insert
Then I swipe left | insert | insert
Then I swipe right | insert | insert
Then I swipe up | insert | insert
Then I swipe down | insert | insert
Then I swipe left on number 2 | insert | insert
Then I swipe left on number 2 at x 20 and y 10 | insert | insert
Then I swipe left on "accLabel" | insert | insert
Then I swipe on cell number 2 | insert | insert
Then I pinch to zoom in | insert | insert
Then I pinch to zoom in on "accLabel" | insert | insert
Then I scroll :direction | insert | insert
Then I scroll :direction on "accLabel" | insert | insert
Then I playback recording "mytouch" | insert | insert
Then I playback recording "mytouch on "accLabel" | insert | insert
Then I playback recording "mytouch on "accLabel" with offset 10,22 | insert | insert
Then I rotate device left | insert | insert
Then I rotate device right | insert | insert
insert | insert | insert
insert | insert | insert
insert | insert | insert


To see how these have been implement: [calabash_steps.rb](https://github.com/calabash/calabash-ios/blob/master/calabash-cucumber/features/step_definitions/calabash_steps.rb)

## Ruby API

Things you can do

* touch
* query

Directions

Example | Descripiton | Notes |
---- | ----------- | ----------- |
touch("button index:0") | touch the first button | insert
touch("tabBarButton index:1") | touch the second tabBarButton | insert
touch("tabBarButton marked:'Second'") | though the tabBarButton with the accessibility id or label 'Second' | insert
label "tableViewCell index:0" | insert | insert
query("tabBarButton") | Returns an array of all the tabBarButtons | insert
query("tabBarButton", :accessibilityLabel) | Returns an array of all the tabBarButton accessibility labels | insert
query("tabBarButton index:0", :accessibilityLabel) | insert | insert
query("tabBarButton index:0 label", :text) | Returns all the labels inside the first tabBarButton | insert
query("TabBar", :selectedItem, "title")[0] | insert | insert
query("button marked:'Player play icon'", :isSelected) | insert | insert
query "label index:0" | Returns the first label | insert
query "label marked:'Map'" | Returns the label with the accessibility label 'Map' | insert
query "label {text LIKE 'Cell 1*'}" | Returns the labels that start with 'Cell 1' | * Uses a [NSPredicate](https://developer.apple.com/library/ios/#DOCUMENTATION/Cocoa/Reference/Foundation/Classes/NSPredicate_Class/Reference/NSPredicate.html)
query "button isEnabled:1" | insert | insert
query("view marked:'switch'") | Returns a view with accessibility id or label 'switch' | insert
query("button")[0]["class"] | Returns the class of the first button | insert
element_exists("view") | insert | insert
element_exists("button marked:'#{name}'") | insert | insert
element_does_not_exist("button marked:'#{name}'") | insert | insert
view_with_mark_exists("Logout") | insert | insert
sleep(STEP_PAUSE) | insert | insert
wait_for(WAIT_TIMEOUT) | insert | insert
wait_for(5) | insert | insert
query("view:'MKMapView'") | matches a view based on the className 'MKMapView'|
scroll_to_row "tableView", 3 | insert | insert
query("tableView",numberOfRowsInSection:0) | insert | insert
query("webView css:'#header'") | insert | insert
set_text "webView css:'input.login'", "ruk" | insert | insert
scroll "webView", :up | insert | insert
scroll "webView", :down | insert | insert
scroll "webView", :left | insert | insert
scroll "webView", :right | insert | insert
scroll_to_row "tableView", 2 | insert | insert
query("webView css:'a'").first['html'] | insert | insert
touch("webView css:'a'") | insert | insert
query("webView css:'*'") | Get all the HTML associated with the webview | insert
query "webView", :request | Get the page url | insert
check_element_exists("view marked:'#{expected_mark}'") | insert | insert
keyboard_enter_char "a" | insert | insert
keyboard_enter_char "Dictation" | insert | insert
keyboard_enter_char "Shift" | insert | insert
keyboard_enter_char "Delete" | insert | insert
keyboard_enter_char "Return" | insert | insert
keyboard_enter_char "International" | insert | insert
keyboard_enter_char "More" | insert | insert
keyboard_enter_text "The Quick Brown Fox" | insert | insert
done | Enters "Done" or "Search" or "Return" | insert
rotate :left | insert | insert
rotate :right | insert | insert
screenshot "/Users/krukow/tmp", "my.png" | insert | insert
insert | insert | insert














* In general you use a [NSPredicate](https://developer.apple.com/library/ios/#DOCUMENTATION/Cocoa/Reference/Foundation/Classes/NSPredicate_Class/Reference/NSPredicate.html) by writing a filter: {selector OP comp}, where selector is the name of a selector you want to perform on the object and OP and comp are an operation and something to compare with.

## Resources

### Docs
* [Calabash](http://calaba.sh/)
	* [calabash-ios](https://github.com/calabash/calabash-ios) 
	* [01 Getting started guide](https://github.com/calabash/calabash-ios/wiki/01-Getting-started-guide)
	* [02 Predefined steps](https://github.com/calabash/calabash-ios/wiki/02-Predefined-steps)
	* [03 Writing custom steps](https://github.com/calabash/calabash-ios/wiki/03-Writing-custom-steps)
	* [03.5 Calabash iOS Ruby API](https://github.com/calabash/calabash-ios/wiki/03.5-Calabash-iOS-Ruby-API)
	* [04 Touch recording and playback](https://github.com/calabash/calabash-ios/wiki/04-Touch-recording-and-playback)
	* [05 Query syntax](https://github.com/calabash/calabash-ios/wiki/05-Query-syntax)
	* [06 WebView Support](https://github.com/calabash/calabash-ios/wiki/06-WebView-Support)
	* [calabash-cucumber - ruby files](https://github.com/calabash/calabash-ios/tree/master/calabash-cucumber/lib/calabash-cucumber)
	* [calabash_steps.rb](https://github.com/calabash/calabash-ios/blob/master/calabash-cucumber/features/step_definitions/calabash_steps.rb)
* [calabash-ios forum](https://groups.google.com/forum/?fromgroups=#!forum/calabash-ios)

* [lesspainful](https://www.lesspainful.com/)
	* [AN OVERVIEW OF CALABASH IOS](http://blog.lesspainful.com/2012/03/07/Calabash-iOS/)
	* [CALABASH: FUNCTIONAL TESTING FOR MOBILE APPS](http://blog.lesspainful.com/2012/03/07/Calabash/* )

### Tutorials
* [iOS Automated Testing With Calabash, Cucumber, and Ruby](http://www.moncefbelyamani.com/ios-automated-testing-with-calabash-cucumber-ruby/)

### Videos
* [Calabash, an open-source automated testing technology for native mobile, by Karl Krukow](http://www.youtube.com/watch?v=0an8l1RAe0M)
* [iOS Automated Testing with Calabash: Tips and Tricks](http://www.youtube.com/watch?v=mvzGAs9aD20&feature=plcp)
* [Calabash, an open-source automated testing technology for iOS and Android](http://skillsmatter.com/podcast/home/calabash-an-open-source-automated-testing-technology-for-ios-and-android)

### Related
* [uispec - Behavior Driven Development for the iPhone](http://www.hans-eric.com/share/getting-started-with-uispec/)