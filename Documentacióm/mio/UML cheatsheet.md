# Parts of a Class

The class name

The attributes (properties of the class). The properties have this format:

```
-name: string
-age: int
-id: -int
```

The dash meansthe attribute is private to that class. Setting it with a plus means it is public to any other class. Like this:


```
+name: string
+age: int
+id: -int
```


private is - 
public is +
protected is #   (protected means it can only be accessed by the same class or subclasses)


The methods are below the attributes and look like this:

```
-setName()
-doSomething()

```


Generally, attributes are private or protected and methods are often public.



# Clear arrow (Inheritance)

The clear arrows is a subclass that points to the parent class. THe subclass inherits the attributes of the parent.

# Line (Association)

A line prepresents an association between classes. The line could have text that described the association. A line between User and Food could have the text "eats"
to describe the association between a user and food.


# Clear Diamond (Aggregation)
This is an aggregation. An aggregation is a special type of association that specifies a thing and its parts.

A User might be part of a Squad, but doesn't have to be. The clear diamond in that case would point to the Squad from the User

# Black Diamond (Composition)

When a child object can't exist without its parent object.
THe black diamond would point to the parent from the child.




# Multiplicity.

You can set number values to relationships using syntax such as 1..* (one to many).

0..1 Zero to one (optional)

n specific number

0..* zero to many

1..*  one to many

m..n specific number range