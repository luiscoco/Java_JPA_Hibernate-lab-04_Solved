# Java_JPA_Hibernate-lab-04_Solved

## Exercise

Entities class hierarchy

Goal

Learn how to map entity-classes hierarchy (OOP paradigm) into relational model in terms of Java Persistence API.

Subject

There are 3 domain objects: Customer, Employee and Executive. All of them have common parent class Person that is abstract and contains shared fields (id and name). The following class diagram represents the hierarchy of classes (with its attributes):

<img width="266" height="260" alt="image" src="https://github.com/user-attachments/assets/fc087e21-9bb3-4343-bad1-2621e8fdb5aa" />

You need to map this OO model into relational model using facilities provided by JPA: Single table per class hierarchy (InheritanceType.SINGLE_TABLE); Table per concrete class (InheritanceType.TABLE_PER_CLASS); and Table per class (InheritanceType.JOINED).

Description

**Inheritance type SINGLE_TABLE**

1.	Open module jpa-lab-04

2.	Look on the package edu.jpa.TABLE_PER_HIERARCHY.entity. This package contains entity-classes for the domain.

3.	Open class edu.jpa.TABLE_PER_HIERARCHY.entity.Person and add class-level annotations:

@Entity – marks class as entity-class

@Inheritance(strategy=InheritanceType.SINGLE_TABLE) – defines the hierarchy mapping strategy to use.

@DiscriminatorColumn(name="TYPE", discriminatorType=DiscriminatorType.STRING) – defines the database table field that will be used to keep discriminator value

4.	Open class edu.jpa.TABLE_PER_HIERARCHY.entity.Customer and add class-level annotations:

@Entity – marks class as entity-class

@DiscriminatorValue("Customer") – defines value “Customer” as discriminator value for this type

5.	Open class edu.jpa.TABLE_PER_HIERARCHY.entity.Employee and add class-level annotations:

@Entity – marks class as entity-class

@DiscriminatorValue("Employee") – defines value “Employee” as discriminator value for this type

6.	Open class edu.jpa.TABLE_PER_HIERARCHY.entity.Executive and add class-level annotations:

@Entity – marks class as entity-class

@DiscriminatorValue("Executive") – defines value “Executive” as discriminator value for this type

7.	Open class edu.jpa.TABLE_PER_HIERARCHY.Launcher and analyze its content: 

method init() create objects and saves them into database

method sample() finds the entity by identified and prints the “name” attribute to console

8.	Run class edu.jpa.TABLE_PER_HIERARCHY.Launcher. There should be no errors if entity is defined correctly.

9.	Analyze queries JPA runtime sends to database for data extraction.

10.	Open database DB_LAB_04_TABLE_PER_HIERARCHY using dbVisualizer application, and look on the created database objects (tables, constraints, etc.) and data. Analyze it.

**Inheritance type TABLE_PER_CLASS**

11.	Look on the package edu.jpa.TABLE_PER_CLASS.entity. This package contains entity-classes for the domain.

12.	Open class edu.jpa.TABLE_PER_CLASS.entity.Person and add class-level annotations:

@MappedSuperclass – marks this class as template for child entity clasess.

@Inheritance(strategy = InheritanceType.TABLE_PER_CLASS) – defines the hierarchy mapping strategy to use.

13.	Open class edu.jpa.TABLE_PER_CLASS.entity.Customer and add class-level annotations:

@Entity – marks class as entity-class

14.	Open class edu.jpa.TABLE_PER_CLASS.entity.Employee and add class-level annotations:

@Entity – marks class as entity-class

15.	Open class edu.jpa.TABLE_PER_CLASS.entity.Executive and add class-level annotations:

@Entity – marks class as entity-class

16.	Open class edu.jpa.TABLE_PER_CLASS.Launcher and analyze its content: 

method init() create objects and saves them into database

method sample() finds the entity by identified and prints the “name” attribute to console

17.	Run class edu.jpa.TABLE_PER_CLASS.Launcher. There should be no errors if entity is defined correctly.

18.	Analyze queries JPA runtime sends to database for data extraction.

19.	Open database DB_LAB_04_ TABLE_PER_CLASS using dbVisualizer application, and look on the created database objects (tables, constraints, etc.) and data. Analyze it.

**Inheritance type JOINED**

20.	Look on the package edu.jpa.TABLE_PER_SUBCLASS.entity. This package contains entity-classes for the domain.

21.	Open class edu.jpa.TABLE_PER_SUBCLASS.entity.Person and add class-level annotations:

@Entity – marks class as entity-class

@Inheritance(strategy = InheritanceType.JOINED) – defines the hierarchy mapping strategy to use.

22.	Open class edu.jpa.TABLE_PER_SUBCLASS.entity.Customer and add class-level annotations:

@Entity – marks class as entity-class

23.	Open class edu.jpa.TABLE_PER_SUBCLASS.entity.Employee and add class-level annotations:

@Entity – marks class as entity-class

24.	Open class edu.jpa.TABLE_PER_SUBCLASS.entity.Executive and add class-level annotations:

@Entity – marks class as entity-class

25.	Open class edu.jpa.TABLE_PER_SUBCLASS.Launcher and analyze its content: 

method init() create objects and saves them into database

method sample() finds the entity by identified and prints the “name” attribute to console

26.	Run class edu.jpa.TABLE_PER_SUBCLASS.Launcher. There should be no errors if entity is defined correctly.

27.	Analyze queries JPA runtime sends to database for data extraction.

28.	Open database DB_LAB_04 using MySQL Workbench and look on the created database objects.
 


## Solution


