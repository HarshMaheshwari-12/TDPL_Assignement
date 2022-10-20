Q1. In the below code, list1 declared with var, list2 with final and list3 with const. What is
the difference between these lists? Will the last two lines compile?
Ans1. List1 is declares as a var and can be change because List are mutable by default. List2 is final and cannot change. List3 is declared as constant which is compiled at the compile time.

Ans for second Part
Ans. The third line will compile but here we are not reassigning the list2 list itself, but changing the value of an item in the third index position in the List2. As you know List are mutable by default. The fourth line will not compile because we cannot assign the var values to the constant values.In this list1 is declared as var and list3 is declared as constant so it's not possible to assign the lis1 to list3.


Q2.Identify the problem in the following code block and correct it.
Ans. It blocks your app because counting to ten billion is a computationally expensive task, even for a computer.
Dart code runs inside its own area of memory called an isolate — also known as memory thread. Each isolate has its own memory heap, which ensures that no isolate can access any other isolate's state.


Correct Code is - 
Future<String> makeSomeoneElseCountForMe() async {
  return await compute(playHideAndSeekTheLongVersion, 10000000000);
}

String playHideAndSeekTheLongVersion(int countTo) {
  var counting = 0;
  for (var i = 1; i <= countTo; i++) {
    counting = i;
  }
  return '$counting! Ready or not, here I come!';
}

Q3. What is the main difference between Mobx & Provider? Can we use both together?Write code to demonstrate it.
Ans 3. Provider is used only for dependency injection with mobx. It is not used for state changes.
Now when you are using mobx you don't need a stateful widget in most cases because you are handling your state changes inside your mobx store and if there is any changes in the state we use Observer to change ui.
Now don't use global providers for your all of store. Only Initialise a provider whenever you need it. So when you push a route wrap it with a provider so that Provider.of(context); can find it. Only use global store if it required globally.You mentioned creating an instance of store to use it. When you initialise a store in stateless widget it, the data will get destroyed when you close the screen and when you reopen it everything will start all over again. It is useful when you don't need to maintain state after screen pops. It will based on your use case.

Example-  class MyStore = _MyStore with _$MyStore;

abstract class _MyStore with Store {

_MyStore(){
  getData();
}
}
