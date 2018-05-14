# TicTacToe - MVC

A simple tic tac toe app, to illustrate the use of MVC, MVP, and MVVM architectures to organize the application.

The master branch contains just the model - The brains & state of the tic tac toe game.

Other branches contain the model, plus a User Interface following:
* *mvc* - Is an example of using Model View Controller to model the UI / Model Interaction.
* *mvp* - Example of Model View Presenter
* *mvvm* - Example of Model View ViewModel with Databinding 


## Model

The model is the Data + State + Business logic of our Tic-Tac-Toe application.
It’s the brains of our application so to speak. It is not tied to the view or controller, and because of this, it is reusable in many contexts.

## View

The view is the Representation of the Model.
The view has a responsibility to render the User Interface (UI) and communicate to the controller when the user interacts with the application.
In MVC architecture, Views are generally pretty “dumb” in that they have no knowledge of the underlying model and no understanding of state or what to do when a user interacts by clicking a button, typing a value, etc.
The idea is that the less they know the more loosely coupled they are to the model and therefore the more flexible they are to change.

## Controller

The controller is Glue that ties the app together.
It’s the master controller for what happens in the application.
When the View tells the controller that a user clicked a button, the controller decides how to interact with the model accordingly.
Based on data changing in the model, the controller may decide to update the state of the view as appropriate.
In the case of an Android application, the controller is almost always represented by an Activity or Fragment.

View ([tictactoe.xml](https://github.com/nguyenkien25/TicTacToe-MVC/blob/master/app/src/main/res/layout/tictactoe.xml) [menu_tictactoe.xml](https://github.com/nguyenkien25/TicTacToe-MVC/blob/master/app/src/main/res/menu/menu_tictactoe.xml))
---Notify , Setup View --> Controller ([TicTacToeActivity](https://github.com/nguyenkien25/TicTacToe-MVC/blob/master/app/src/main/java/com/acme/tictactoe/controller/TicTacToeActivity.java))
---Interact with--> Model ([Board](https://github.com/nguyenkien25/TicTacToe-MVC/blob/master/app/src/main/java/com/acme/tictactoe/model/Board.java) [Cell](https://github.com/nguyenkien25/TicTacToe-MVC/blob/master/app/src/main/java/com/acme/tictactoe/model/Cell.java) [Player](https://github.com/nguyenkien25/TicTacToe-MVC/blob/master/app/src/main/java/com/acme/tictactoe/model/Player.java))

## Evaluation

MVC does a great job of separating the model and view.
Certainly the model can be easily tested because it’s not tied to anything and the view has nothing much to test at a unit testing level.
The Controller has a few problems however.

## Controller Concerns

- Testability - The controller is tied so tightly to the Android APIs that it is difficult to unit test.
- Modularity & Flexibility - The controllers are tightly coupled to the views. It might as well be an extension of the view. If we change the view, we have to go back and change the controller.
- Maintenance - Over time, particularly in applications with anemic models, more and more code starts getting transferred into the controllers, making them bloated and brittle.

## How can we address this? MVP to the rescue!
