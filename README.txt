1 Create the laravel project:

composer create-project laravel/laravel taskman

2 Use preset to install react component into the project folder / react scuffolding

php artisan preset react

3 install app dependencies

npm install

4 Create Models and migrations (Eg: 2 objects/tables in DB: Projects and tasks)

 php artisan make:model Task -m
 php artisan make:model Project -m

5 Define tables database/migrations and configure database in .env file

6 php artisan migrate

7 add Routing rules to routes/api.php

    Route::get('projects', 'ProjectController@index');
    Route::post('projects', 'ProjectController@store');
    Route::get('projects/{id}', 'ProjectController@show');
    Route::put('projects/{project}', 'ProjectController@markAsCompleted');
    Route::post('tasks', 'TaskController@store');
    Route::put('tasks/{task}', 'TaskController@markAsCompleted');

8 Create controller for

 php artisan make:controller ProjectController
 php artisan make:controller TaskController

9 Configure controller files .php under app/Http/Controllers/

10 define a wildcard route     // routes/web.php

    Route::view('/{path?}', 'app');

11 create app.blade.php file under resources/views/
    We add references to both a CSS file and a JavaScript file (containing React and other dependencies bundled up). We have an empty div with an id of app. This is where our React components will be rendered. Also, you’ll notice we have a meta tag containing a CSRF token, which will be attached as a common header to all outgoing HTTP requests we make using Axios. This is defined in resources/assets/js/bootstrap.js.

12 resources/assets/js/components/App.js The App component will serve as the base for our React components. Let’s rename the default Example component to App and replace it content with the following code:

13 We render a Header component (which we’ll create shortly). The Header component will be rendered for all our app pages. As you can see, we are making use of React Router, so let’s install it:

    $ npm install react-router-dom

14 While that’s installing, open and update resources/assets/js/app.js as below:

    // resources/assets/js/app.js
    require('./bootstrap')
    require('./components/App')

15 Create header component 
    // resources/js/components/Header.js

16 Create projectsList component
    // resources/js/components/ProjectsList.js

17 update App.js:  Here, we add a new route / (homepage). So whenever the / route is visited, the ProjectsList component will be rendered.

18 add 'create new project' component: NewProject.js

19 Just as we did with the ProjectsList component, let’s add the NewProject component to the App component. Update the App component as below:

                <Route path='/create' component={NewProject} />

20 Display a project: SingleProject.js

21 Update App.js add SingleProject

22 Add mark as completed function and add button action

23 create add task functions to single project.js

24 Next, add the code below inside the render method just below <hr />: --> FORM FOR NEW TASK CREATİON

25 create marks as completed function and update mark as completed button action

26 COMPILE: npm run dev

27 run the app : php artisan serve


