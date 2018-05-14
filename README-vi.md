# TicTacToe - MVC

A simple tic tac toe app, to illustrate the use of MVC, MVP, and MVVM architectures to organize the application.

The master branch contains just the model - The brains & state of the tic tac toe game.

Other branches contain the model, plus a User Interface following:
* *mvc* - Is an example of using Model View Controller to model the UI / Model Interaction.
* *mvp* - Example of Model View Presenter
* *mvvm* - Example of Model View ViewModel with Databinding 


## Model

Mô hình bao gồm Data + State + Business logic.

## View

View là đại diện của các Model.
View có trách nhiệm render cho giao diện người dùng (UI) và giao tiếp với controller khi người dùng tương tác với các ứng dụng.
Trong kiến trúc MVC, View thường khá "dumb" trong đó nó không biết về các mô hình cơ bản và không biết về các state hoặc làm gì khi người dùng tương tác bằng cách nhấn một nút, typing một giá trị, vv

## Controller

Controller là Glue mà quan hệ ứng dụng với nhau.
Nó là điều khiển tổng thể cho những gì xảy ra trong ứng dụng.
Khi View nói với controller rằng người dùng nhấp vào một nút, controller quyết định làm thế nào để tương tác với các Model phù hợp.
Dựa trên dữ liệu thay đổi trong Model, Controller có thể quyết định để cập nhật trạng thái của điểm phù hợp.
Trong trường hợp của một ứng dụng Android, controller hầu như luôn luôn đại diện bởi một Activity hoặc Fragment.

## Evaluation

MVC làm một việc tuyệt vời của việc tách Model và View.
Chắc chắn các Model có thể dễ dàng kiểm tra bởi vì nó không gắn với bất cứ thứ gì và View không có gì nhiều để test ở mức độ unit test.
Tuy nhiên Controller có một vài vấn đề.

## Controller Concerns

- Testability : controller được gắn rất chặt chẽ đến các API Android mà rất khó để unit test.
- Modularity & Flexibility : Các controller được kết chặt chẽ với các View. Nó cũng có thể là một phần mở rộng của View. Nếu chúng ta thay đổi View, chúng ta phải quay trở lại và thay đổi Controller.
- Maintenance : Theo thời gian, đặc biệt là trong các ứng dụng với mô hình anemic, càng ngày code của controller càng nhiều, làm cho chúng cồng kềnh và dễ gãy.

## Và làm sao để sửa chúng? MVP là cứu tinh!
