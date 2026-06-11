---
aliases:
  - Database Lecture 3
tags:
  - Notes
  - Database
Date: 2025-03-21
Completion: true
obsidianUIMode: preview
---
>[!INFO] Lecture
>[[lecture_3_database_design_methodology.pdf]]


>[!DEFINITION] Database Design Methodology
>A structured approach that uses procedures, techniques, tools and documentation to help the design of a database.

# Database SDLC
## Database Planning
This phase revolves around:
1. Determining the purpose of the database system
2. Determining the aim of the database system
3. Resources needed for the database system

## Requirements collection and analysis
This phase mainly revolves around:
1. The type of data to be used and their description
2. How the data would be used and generated
3. Other relevant system's requirements

## Prototyping
>[!Prototyping]
>The process of creating initial version of the *database* system for user experimentation or testing. It is also used for developers to test new features or design to determine their suitability

There are vertical prototyping and horizontal prototyping. 
>[!DEFINITION] Vertical Prototyping
>The prototype has a lot of features, but they're mostly non-functional

>[!DEFINITION] Horizontal Prototyping
>The prototype has few features, but are mostly functional

## Database Design
### Conceptual Database Design
>[!DEFINITION] Conceptual Database Design
>Means that the model of the data to be used independent of any physical consideration is to be constructed. The model of the data is dependent on the system's requirements.

In conceptual database design, a couple of tools are used:
1. Data Dictionary
2. Entity relationship diagram

In this phase, you would determine:
1. Entities involved
2. Their relationships
3. Their attributes and descriptions
4. The candidate, primary and alternate key attributes

### Logical Database Design
>[!DEFINITION] Logical Database Design
>Means that the model of the data is based on a specific data model, but independent of any specific database management.
>
### Physical Database Design
>[!DEFINITION] Physical Database Design
>Implementation of the database on a secondary storage

## Application Design
>[!DEFINITION] Application Design
>Designing the user interface or application that would be using the database developed. 

## Data Conversion and Loading
This is only done when there is a need to import data from an old database to a new database.

## Testing
This phase is important to determine if the system developed meet the user requirements.

## Operational Maintenaince
Operational maintenance is divided into two:
1. Monitoring
	- Make observations on the performance of the system
		- If the performance of the system drops below acceptable level, changes may need to be made to the database system 
2. Maintenance
	- Make changes to the database system according to changing user requirements
	- New development life cycle

# Relations and Relationships

## Terminologies
>[!DEFINITION] Cardinality
>The cardinality describes the number of possible relationships for each participating entity

>[!DEFINITION] Participation
>This describes whether all or only some entities participate in the relationship
>

>[!DEFINITION] Strong entity
>Entities where its primary keys are not derived from any other entity. It can also exist on its own. 

>[!DEFINITION] Weak Entities
>Entities where its primary keys are derived from other entities. The instance of the entity cannot exist on its own and is dependent of the instance of a stronger entity. 
## Deriving Relations from relationship
The entities in a database can be divided into:
1. Strong entities
2. Weak entities

The relationships of the entities can be divided:
1. One-to-one binary relationship
2. One-to-many binary relationship
3. Many-to-many binary relationship
4. Complex relationship

### One-to-one binary relationship
This form of relationship can exist between two entities or within the same entity. 

> *Assume it's separate entities for now*

 If the relationship is mandatory on both sides, depending on the situation, the entities can be merged into a single entity. The primary key of the new singular entity can be taken from either one of the ex-entity. 

*Why does it depend on the situation?*<br>In some cases, merging the two entities would result in a lot of duplication of values. If that's desired to be avoid, it's best to keep the two entities separated. 

If it's optional on one of the two sides, the entity on the optional end would be the strong entity, and the entity on the mandatory end would be the weak entity. 

If both ends are optional, the relationship between the two entities are ultimately arbitrary and can only be decided with having more information regarding their relationship.

The same rule applies to recursive relationships
### Many-to-many binary relationship type
Create a junction table that has the primary keys of involving relations of the foreign keys. 

### Complex relationship types
This usually involves more than 2 entities that are related to each other. To solve this, you would also create a junction table with the primary keys of the involved entities along with other attributes. 

# Solving multi-valued attribute
There are two ways to go about this:
1. Create a new entity containing each value of the multi-valued attribute
2. Create multiple columns to hold each of the multi values. 
