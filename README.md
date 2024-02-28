# Fix this Code!

- What is wrong with this code?
- Fix build and upload for review! 🙂

``` Csharp
﻿using System.Reflection.Emit;

using System;

namespace proj1;

class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Hello, World!");
        
        var myClass = new MyClass();

        //myClass.MyClassMethod();
        myClass.MyClassProperty = "Hello!";
    }

    public interface IMyClass
    {
        public string? MyClassProperty {get; set;}
        public void MyClassMethod();
        public string MyOtherMethod();
        
    }

    public class MyClass : IMyClass
    {
        private string? myClassField;

        public string? MyClassProperty 
        {
            get
            {
                return myClassField;
            }

            set
            {
                this.MyClassMethod();
                myClassField = value ?? "NULL";
            }
        }

        public void MyClassMethod()
        {
            Type[] interfaces = this.GetType().GetInterfaces();

            foreach (Type item in interfaces)
            {
                System.Console.WriteLine(item.Name);
            }

            System.Console.WriteLine("MyClassMethod!");
        }
    }
}
```
