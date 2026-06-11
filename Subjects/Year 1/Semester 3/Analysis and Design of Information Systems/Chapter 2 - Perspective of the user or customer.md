---
aliases:
  - Perspectives
tags:
  - Notes
  - ADIS
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# Outsourcing
**Definition**
*Formal*
Turning over responsibility of some or all of an organisation's information systems applications and operations to an outside firm.
*Layman*
Turning over your responsibility over to a professional third party
## Reasons to outsource
1. Turn over development and operations to outside staff who posses knowledge and skills not found internally.
	1. Restaurant staffs have no knowledge of developing an application.
2. Cost-effective
	1. If you want to make it internally, you have to spend on server, manpower, technology, etc. 
3. Free up internal resources
	1. The staffs in restaurant can keep doing what they're doing efficiently.
	2. The staffs are not burdened with too much work. 
4. Increase process efficiencies
	1. Let the professionals to do the work
5. System development is a non-core activity for the organisation
	1. A restaurant does not have staffs whose expertise reside in application making
## Sources
1. IT services firms
2. Cloud computing 
3. Open source
	1. python
	2. linux
	3. gimp
4. In-house
5. ERP providers
6. Packaged software providers
### IT services firm
1. Help companies develop custom information systems for internal use
	- Creating a specific information system 
	- Restaurant who wants a food ordering system
2. Develop, host, and run applications for customers
3. Provide other services
	- Advise clients about the information system
4. Helps creating complex system
5. Internal staffs are needed to test the application
### Packaged Software Producers
The product you purchase, it comes with a lot of software in a package
1. Serve many market segments
	1. Microsoft office
	2. Oracle
	3. Adobe
2. Software ranges from broad-based packages (*general ledger*/ *microsoft excel*) to niche packages (*software to help in day care management*/ *specific purpose* )
	1. *microsoft excel*
		1. You can do all sorts of things with it in a company 
			1. Do calculations 
3. Pre-packaged software is **turnkey software** (*not customisable*)
	1. **Off-the-shelf** software at best meets 70% of organisation's needs
4. When the task is generic
	1. Creating powerpoint, document, spreadsheet
5. Staffs are required to determine the requirements and evaluate the software to be purchase
	1. Does it fulfil their requirements?
	2. Are they comfortable using them
### Cloud Computing
Resources available online, need to purchase cloud computing service to access the resources. --> google drive
Paying third party resources to save your own sources
1. Provision of computing resources, including applications, over the INTERNET, so customers do not have to invest in the computing infrastructure needed to run and maintain the resources
2. Usually from third party providers who run the applications at remote sites
3. Rent or pay on a per-use basis, typically month-to-month/ Subscription based
4. Instant access to an application or when supported task is generic
	1. Few staffs are needed 
	2. They can be used for other work
### Enterprise Resource Planning
Single system but operable by all staffs in the company. *Like a centralised database* .
The software has to cater to all services/uses in a single database/system
1. Integrate individual traditional business functions into modules enabling a single seamless transaction to cut across functional boundaries.
2. Includes a **single repository/database** of data for all aspects of a business process.
3. SAP AG is the leading vendor of ERP systems.
4. For complete systems that cross functional boundaries
	1. Need consultants to advise them on software/ money matters
### Open Source Software
1. Freely available including source code
2. Developed by a community of interested people
3. Performs the same functions as commercial software
4. Examples
	1. Linux
	2. Python
	3. Firefox
5. Supported task is generic but cost is an issue
	1. similar to Packaged software producers
### In-House Development
1. The staffs inside an organisation develop the system themselves
2. Hybrid solutions 
	- Purchased and some in-house components
3. Example
	- A hotel makes their own booking system for themselves. This is possible if they have the resources (professionals, money, and technology)
4. When resources and staffs are available and system must be built from scratch
	- Internal staffs are need although size may vary
### Criteria when purchasing Off-the-shelf software
1. **Cost**
	1. Compare the cost of developing the same system in-house with the purchase of a software package
	2. If it is cheaper to develop, develop the software
	3. If it is cheaper to purchase the **off-the-shelf** software, purchase it.
2. Most companies purchase these types of software for general purpose
3. **Functionality**
	1. Can the software do what the company wants
	2. Does the software contains mandatory, essential and desired system features
4. **Vendor support**
	1. How much *support* can be provider can provide and at what cost
		1. How good is the customer service?
		2. What kind of guidance/manual/training does the vendor provide
5. **Flexibility**
	1. How easy it is to customise the software
		1. Microsoft products
	2. What we can do instead is check the software itself
6. **Documentation**
	1. The user manual and technical documentation understandable/comprehensive and updated. 
		1. Godot documentation
		2. Python documentation
		3. Kali linux documentation
7. **Response time**
	1. How responsive is the software to users' interaction/requests
	2. How fast is the software/ how optimised is it
8. **Ease of installation**
	1. How is it to install and set up the software before use
9. **Viability of vendor**
	1. Is the company trustworthy?
	2. Is the company here to stay
### Information sources for purchased software
1. Vendor's proposal
	1. Request for proposal 
2. Running software through a series of tests/trial
	1. Test the software first before fully implementing it
3. Feedbacks of other users that purchased the vendor's software
	1. Search for the reviews online
4. Independent software testing services
	1. The **third-party-company**  will run test based on the criteria set by the user and prepare the report for the user to read 
5. Articles in trade publications 
	1. Obtain information from any articles online
	2. Caveat
		1. The company pays the journalists to write only the positives of the software
			- **Biased**
	3. Companies read journals and proceeding papers rather than online articles 
# Reuse
The use of previously written software resources, especially objects and components, in new applications. *For example: reusing previously written code in another project*
**Three basic steps to reusing**
1. **Abstraction (Reusing)** 
	- The design of reusable software starting from existing software assets or from scratch
	- Taking important components/assets from an existing software and reusing them in another project
		- If this is not possible, build the project from scratch
2. **Storage (Preparing the software to be reusable)**
	- Making it (*the software*) available for others to use by storing it           (*coding, database, technology, anything important*) in a storage.
	- The information inside the storage should be labelled properly for easy access
3. **Recontextualisation (Preparing the software to be reusable)**
	- (*The project*) Need to understand by others (*Write your damn comments*)
	- Prepare a proper documentation

*Example:*
A group of developers have developed a website previously. Now, there is a new project/ website. These developers can reuse their old coding/database in their new project
## Benefits of reusing
1. Decrease development time
	- You can just copy a snippet of code from Project A to B
	- The quality is good 
2. Minimising schedule overruns
	- Since most of the code has been written, the work is easier and can be done faster
3. Result in higher quality software with lower defects rates
	- Why fix something that is not broken
		- The coding has been tested and installed before
1. Decreases maintenance cost
	- The code you copy is high-quality anyway
	- The coding has been tested and installed before
	- You dont have to spend much to maintain a working code
## Approaches to Reuse
1. **Ad-hoc/free lancer**
	- Individuals are free to find or develop reusable assets on their own.
	- They are not engaged/tied to any company
	- They do it for the fun of it
	- Freelancers can decide if they wish to reuse previously written programmes
2. **Facilitated**
	- Developers are encouraged to practice resuse
	- Organisation makes tools and techniques available that enable development and sharing of codes
	- The organisation makes sure it is easy to share codes with one another
	- It is still the developers choice to reuse old codes or write everything from scratch again
3. **Managed**
	 - **Reuse is mandated**
	- **Reuse effectiveness will be measured**
	- The development, sharing, and adoption of reusable assets is mandated. (*must*)
	- Policies and processes are developed for ensuring that reuse is practiced and results are measured(*to determine if reusing old codes is beneficial or not*). 
	- The company forces the developer to reuse old coding in their new project
	- Cost level is moderate
		- You need to prepare documentation, packing and certification from testing 
5. **Designed**
	- **Reuse is mandated**
	- **Reuse effectiveness will be measured**
	- Mandating that assets be designed for reuse as they are being designed for **specific applications**
	- Developing assets by focusing on the reusable element
	- Making sure the asset being developed can be reused in the future
	- C++ libraries are reusable (anyone can use the library for themselves)
	- The cost is high
		- You have to pay programmers
		- You have to pay for testing
		- You have to 
	- Checks if the asset can be reused and is on par (**Check by corporate office**)
![[approaches_to_reuse.png]]