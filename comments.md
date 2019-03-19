# Code Comments 

## Validation in the Controllers
It is no longer acceptable to make request params validation in the controller method. The FormRequest feature is a better place to validate requests. Please rework your RegisterController.php file.

## JS and Styles in the Public Folder
Good work spliting your styles and js into separate folders. However, it is not best practice to put js and styles files in the public folder. Place them somewhere like /resources/assets/js or sass directory instead. Laravel 5 gives us out of the box the GULP integrated which makes it easy to sprint and manage the code.

## Laravel Facade 
This should only be used inside of controllers and middleware. Please remove from all other files and use the Dependency Injection instead.

## Foreach loops
foreach does not create a scope. Using references in foreach loops can be useful but $value will remain in scope and will hold a reference to the last element in the array. To get the benefit of using references in foreach loops without running the risk of these kinds of problems, call unset() on the variable, immediately after the foreach loop.

Don't perform queries inside of loops, this can be accomplished much more efficiently in a single SQL query. Rework authors.blade.php