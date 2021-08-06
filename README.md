# DesignPattern
一些设计模式的描述
## 工厂模式Factory Parrent  
工厂模式（Factory Pattern）是 Java 中最常用的设计模式之一。这种类型的设计模式属于创建型模式，它提供了一种创建对象的最佳方式。
在工厂模式中，我们在创建对象时不会对客户端暴露创建逻辑，并且是通过使用一个共同的接口来指向新创建的对象。  
1.创建一个接口  
```
public interface Shape {  
   void draw();  
}  
```
2.创建实现接口的实体类 
```
public class Rectangle implements Shape {  
   @Override  
   public void draw() {  
      System.out.println("Inside Rectangle::draw() method.");  
   }  
}  
public class Square implements Shape {  
   @Override  
   public void draw() {  
      System.out.println("Inside Square::draw() method.");  
   }  
}  
public class Circle implements Shape {  
   @Override  
   public void draw() {  
      System.out.println("Inside Circle::draw() method.");  
   }  
}  
```
3.创建一个工厂，生成基于给定信息的实体类的对象  
```
public class ShapeFactory {
    
   //使用 getShape 方法获取形状类型的对象
   public Shape getShape(String shapeType){
      if(shapeType == null){
         return null;
      }        
      if(shapeType.equalsIgnoreCase("CIRCLE")){
         return new Circle();
      } else if(shapeType.equalsIgnoreCase("RECTANGLE")){
         return new Rectangle();
      } else if(shapeType.equalsIgnoreCase("SQUARE")){
         return new Square();
      }
      return null;
   }
}
```
4.使用该工厂，通过传递类型信息来获取实体类的对象  
```
public class FactoryPatternDemo {
 
   public static void main(String[] args) {
      ShapeFactory shapeFactory = new ShapeFactory();
 
      //获取 Circle 的对象，并调用它的 draw 方法
      Shape shape1 = shapeFactory.getShape("CIRCLE");
 
      //调用 Circle 的 draw 方法
      shape1.draw();
 
      //获取 Rectangle 的对象，并调用它的 draw 方法
      Shape shape2 = shapeFactory.getShape("RECTANGLE");
 
      //调用 Rectangle 的 draw 方法
      shape2.draw();
 
      //获取 Square 的对象，并调用它的 draw 方法
      Shape shape3 = shapeFactory.getShape("SQUARE");
 
      //调用 Square 的 draw 方法
      shape3.draw();
   }
}
```
5.执行程序，输出结果  
```
Inside Circle::draw() method.
Inside Rectangle::draw() method.
Inside Square::draw() method.
```
