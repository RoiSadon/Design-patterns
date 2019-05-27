# Facade: (חזית)
software design pattern commonly used with object-oriented programming
A facade is an object that provides a simplified interface to a larger body of code, such as a class library. A facade can:
* make a software library easier to use, understand and test, since the facade has convenient methods for common tasks;
* make the library more readable, for the same reason;
* reduce dependencies of outside code on the inner workings of a library, since most code uses the facade, thus allowing more flexibility in developing the system;
* wrap a poorly designed collection of APIs with a single well-designed API.
## shape interface:
```java
package facade;

public interface Shape {
	void draw();
}
```
## Rectangle class
```java
package facade;

public class Rectangle implements Shape {
	@Override
	public void draw() {
		System.out.println("Rectangle::draw()");		
	}
}
```
## Circle class
```java
package facade;

public class Circle  implements Shape{
	@Override
	public void draw() {
		System.out.println("Circle::draw()");	
	}
}
```
## ShapeMaker class 
This is the facade class. 
creates two instances and use their implementation. 
```java
package facade;

// This is the facade: 

public class ShapeMaker {
	private Shape circle;
	private Shape rectangle;
	
	public ShapeMaker() {
		circle = new Circle();
		rectangle = new Rectangle();
	}
	
	public void DrawCircle() {
		circle.draw();
	}
	public void DrawRectangle() {
		rectangle.draw();
	}
}
```
## FacadeDemo class
```java
package facade;

public class FacadeDemo {
	public static void main(String[] args) {
		ShapeMaker s1 = new ShapeMaker();
	
		s1.DrawCircle();
		s1.DrawRectangle();
	}
}
```
## Result in console
```
Circle::draw()
Rectangle::draw()
```