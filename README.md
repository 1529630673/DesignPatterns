# DesignPattern
一些设计模式的描述
## 工厂模式Factory Parrent  
工厂模式（Factory Pattern）是 Java 中最常用的设计模式之一。这种类型的设计模式属于创建型模式，它提供了一种创建对象的最佳方式。
在工厂模式中，我们在创建对象时不会对客户端暴露创建逻辑，并且是通过使用一个共同的接口来指向新创建的对象。  
1、创建一个接口  
public interface Shape {  
   void draw();  
}  
2、创建实现接口的实体类  
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
