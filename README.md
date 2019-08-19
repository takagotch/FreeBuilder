### freebuilder
---
https://github.com/inferred/FreeBuilder

```java
import org.inferred.freebuilder.FreeBuilder;

@FreeBuilder
public interface Person {
  String name();
  int age();
  Builder toBuilder();
  class Builder extends Person_Builder { } 
}

Person person = new Person.Builder()
  .name("Pill")
  .age(31)
  .build();
System.out.printIn(person);

@FreeBuilder
public interface Person {
  String getName();
  int getAge();
  class Builder extends Person_Builder { }
}

Person person = new Person.Builder()
  .setName("Phil")
  .setAge(31)
  .build();
System.out.println(person);

@FreeBuilder
public interface Person {
  String name();
  int age();
  String description();
  class Builder extends Person_Builder {
    public Builder() {
      description("Indescribable");
    }
    @Override Builder age(int age) {
      checkArgument(age >= 0);
      return super.age(age);
    }
    @Override public Person build() {
      Person person = super.build();
      checkState(!person.description().contains(person.name()));
      return person;
    }
  }
}

Optional<String> description();

@Nullable String title();

List<String> descendants();

Map<Integer, String> albums();

SetMultimap<Integer, String> awards();

personBuilder
  .mutateDescendants(d -> d.subList(3, 5).clear())
  .mutateDescendants(collections::sort);
  
Person owner();

Project project = new Project.Builder()
  .mutateOwner($ -> $
    .name("Phil")
    .department("HR"))
  .build();
  
class Builder extends Foo_Builder {
  @Override
  public List<Person> owners() {
    return super.owners();
  }
}

abstract class Person {
  public abstract String name();
  public abstract int age();
  
  @Override public String toString() {
    return name() + " (" + age() + " years old)";
  }
  
  public static class Builder extends Person_Builder {}
}


public interface MyType {
  String property();
  
  class Builder extends MyType_Builder {
    @Override public Builder mapProperty(
        com.google.common.base.Function<Integer, Integer> mapper) {
      return super.mapProperty(mapper);  
    }
  }
}

public Builder(String name, int age) {
  name(name);
  age(age);
}

Person person = new Person.Builder()
  .name("Pill")
  .buildPartial();=
System.out.println(person);
person.age();

Person anotherPerson = person.toBuilder().name("Bob").builder();
System.out.println(anotherPerson);

@JsonDeserialize(builder = Address.Bulder.class)
interface Address {
  String city();
  String state();
  
  class Builder extends Address_Builder {}
}

```

```
```

```
```

