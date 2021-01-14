# Java8-features

Java 8 features 
----------------------------------------------------
Lambda expression 

Functional Interfaces

Default method in interface

states method in interface

Predicate -Predefined functional interface

Function -Predefined functional interface

Consumer -Predefined functional interface

Method reference and Constructor reference by :: Operator

Streams

Date and Time API (Joda.org)

Need of Java8
----------------------------------------------------
To Simplify Programming

To utilize functional programming benefits in java

To Enable parallel process come in picture Multicore processing


What is Lambda Expression
-------------------------------------------------------------
Lisp is first programming language  used Lambda 

Why Lambda ?
------------
To enable functional programming in java

write more readable , maintainable and concise code

To user API very easily and effective

To enable parallel Programming


What is Lambda Expression ?
----------------------------

Lambda expression is anonyms function, 

Not Having name

not having Modifiers

Not having any return type


How to write Lambda expression ?
-------------------------------
Example1: Print Hello

public void main(){

System.out.println(hello)

}

No name

No return type

No modifier


() -> {System.out.println(hello)}


Example2: With 2 params and print sum


public void add(int a, int b){

System.out.println(a+b);

}

(int a , int b)-> {}

Example3: With String and return Length

public void getLength(String s){

retrun s.length();

}


(String s) -> { return s.length();}

------------------------------

Rules to write Lambda expression
-------------------------------

Body contain single statement then curly braces can avoid

() -> System.out.println(hello)

Compiler get the type automatically by guessing based on context(type inference)

(a , b)-> System.out.println(a+b);

we don’t need to right return key

(s) ->  s.lenght();

if there is only 1 param then no need to write parenthesis

s -> s.lenght();


-------------------------------------
Characteristics and properties of lambda expression
------------------------------------


------------------------------
Functional Interface 
------------------------------
Why we used Functional Interface?

To invoke Lemda expression we required functional interface

Simplae Abstract Method 

Example of functional interface(All conatns only 1 method)

Runnable - run()

Callable -call()

ActionListener-actionPerformed()

Comparable- compareTo()

What is Functional interface? 

If the interface contain only single absatrcat method that interface call functional interface

Functional
................
Example : -

interface FunctionalTest{

public void main();

default public void main(){}

public static void main(){}

}

interface NonFunctionalTest{

public void main1();

public void main2();

}

Annotaion 
-------------------

@functioalInterface - byMistake if anyone try to update functional interface by adding more the abstract method 
Compiler will give error

@functioalInterface// correct
interface FunctionalTest{

public void main();

}

@functioalInterface //invaild
interface FunctionalTest{

//Error unexpected @functionalInterface no abstract method found in interfca

}

@functioalInterface//invaild
interface FunctionalTest{

public void main1();

public void main2();

}


Functinaol interface inheritance
------------------------------------------
1) @functioalInterface

interface FunctionalTest{

public void main();

}

@functioalInterface// correct (Child interface also will be functinaol interface)

interface a implements FunctionalTest{

//doesnt contain abstract method

}



2) @functioalInterface

interface FunctionalTest{

public void main

}

@functioalInterface// correct (Child interface also will be functinaol interface)

interface a implements FunctionalTest{

public void main();

}

3) @functioalInterface

interface FunctionalTest{

public void main();

}

@functioalInterface// incorrect (Child interface  will not be functinaol interface) it will give compile error

interface a implements FunctionalTest{

public void main2();

}

4) @functioalInterface (valid)
interface FunctionalTest{
public void main();
}

 (Here child is not declared as funcInterface it will work)
 
interface a implements FunctionalTest{

public void main2();

}


Invoing functional interface using Lambda expression 
--------------------------------------------------------
@functioalInterface

interface FunctionalTest{

public void main();

}

class a implements FunctionalTest{

public void main(){

}
}

class test{

stsic void main(String[] args){

FunctionalTest f = new a();

f.main();

}

}

with lambda -
...............

@functioalInterface
interface FunctionalTest{
public void main();
}

class test{
stsic void main(String[] args){
FunctionalTest i =()->sysout(main() method implementation);

i.main();// it will call interface using lambda

}
}


----------------------------------------
default mnethod
interfacename.super.methodName();
---------------------------------------------

1)Autoboxing - Integer i= 30
Wrapper onject -> primitive type
2)Autounboxing -> Integer i = new Integer(10);
int x = i;
primitive type-> Wrapper onject
3)generic type Param -

-----------------------------------------------------
Primitive type of functional interface -
-----------------------------------------------------------

interface Predicate<T>

public boolean test(T t);


Predicate<Integer> p = i -> i% 2==0;


-------------------------------------------------------------------



Suppliers -
---------------------------------------------------------

private someObject getValidationService(String param) {
Optional<Object> Object1 = Object.of( param );
Object Object = Object1
.orElseThrow(supplyInvalidObjectError());
return validationFactory.getValidationService(agencyRelation);
}

private Supplier<InvalidException> supplyInvalidObjectError() {
return this::createInvalidObjectError;
}

private InvalidObjectException createInvalidObjectError() {

return new InvalidObjectException(error);
}
--------------------------------------------------------------

List<Long> existingIds = listObjects
.stream()
.filter(classObject -> Objects.nonNull(classObject.getId()))
.map(class::getId)
.collect(Collectors.toList());
--------------------------------------------------------------------

 newClass1ListObjects.stream().map(beanToObjects()).collect(Collectors.toList());
 
 private Function<class1, class2> beanToObjects() {
return obj -> {
class2 class2Obj = new class2();
class2Obj.setter(obj.getMethod);
return obj;
};
}
--------------------------------------------------------------------------------
list.forEach(object -> createMethod(obj1,obj2));

-----------------------------------------------------------------------------------

StopWatch watch = new StopWatch();
watch.start();
watch.stop();
DateTimeUtil.logWatch("complete", watch);

Date currentDate = new Date(new java.util.Date().getTime());
endDate.before(currentDate)

DateTimeUtil.getDifferenceInMonthsBetweenDates(new java.util.Date(currentDate.getTime()),
new java.util.Date(startDate.getTime())) > 12
--------------------------------------------------------------------------------------
Optional<Class> object = list.stream()
.filter(obj -> ""
.equals(obj.get()))
.findFirst();
---------------------------------------------------------------------------
Class obj = new Class();
obj.setValue1(list.stream().map(listObj -> getSomeMethods(listObj.getValue1())).collect(Collectors.toList()));
obj.setValue2(Collections.max(obj, Comparator.comparing(class::getValue1)).getValue1());

------------------------------------------------------------------------------

lisClass.stream().map(this::getMethod).collect(Collectors.toList());

private class getMethod(class2 obj2) {
        class obj = new class();
        obj.setValue1(obj2.value1);
              return obj;
    }
