# CodeInterview

### new versus override

```c#

public class BaseClass
{
    public virtual void Foo() { Console.WriteLine ("BaseClass.Foo"); }
}

public class Overrider : BaseClass
{
    public override void Foo() { Console.WriteLine ("Overrider.Foo"); }
}

public class Hider : BaseClass
{
    public new void Foo() { Console.WriteLine ("Hider.Foo"); }
}

Overrider over = new Overrider();
BaseClass b1 = over;
over.Foo(); // Overrider.Foo
b1.Foo(); // Overrider.Foo

Hider h = new Hider();
BaseClass b2 = h;
h.Foo(); // Hider.Foo
b2.Foo(); // BaseClass.Foo

```

### Constructors and Inheritance

```c#

public class B
{
    int x = 1; // Executes 3rd
    public B (int x)
    {
        ... // Executes 4th
    }
}

public class D : B
{
    int y = 1; // Executes 1st

    public D (int x) 
      : base (x + 1) // Executes 2nd
    {
        ... // Executes 5th
    }
}

```
