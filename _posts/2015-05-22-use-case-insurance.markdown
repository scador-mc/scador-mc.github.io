---
layout: post
title:  "Use Case: Insurance - Scador.com"
date:   2015-05-22 19:21:45
categories: scador documentation
alias: /scador/usecase-insurance.html
---
## Background
Insurance products in present times are complex and there is nothing can stop its complexity growth besides maybe the ability to understand these products both for sales person and client. Generic insurance products with simple conditions
may be risky for providers because the reality is changing dramatically and every day may bring something new. Generic insurance may lead to costly legal disputes about interpretation and every such dispute will bring either financial loss,
settlement, or scratch on reputation which is everything in the industry.

Complex products however require time to configure if made by human. Additionally fewer and fewer customers wants to
interact with salesman trained in persuasion techniques. More and more customers wants to take quality time to make own decision and wants to make its own wise choices. 

Best solution it to make tool where time and pressure are not relevant anymore providing enough information to make wise choices and finally win win deal.


## Case A: Define Product

###Actor

PM - Product Manager - its our sales person who will actually never psychically interact with a customer. 

###Steps

##### Define product

PM needs to define structure of the product or its product line. To do that PM is using Scador Facts module to 
define insurance component classes. While for the user it will be single contract for us its still kind of 
Bill of Material :)
##### Create component instances
Second step is to define actual instances of components. These will be options to chose by customers. For us
these are defined in Scador Parts.
##### Set up prices
Now its time to define pricelists. We will stick to the one list price however keep in mind that there might be
many targeted for partners, government or corporate customers. Pricelist can have different geo location and 
currency - so you can go global if you want :) When list price is defined you can set the prices of your insurance components or "parts".
##### Set up discounts 
Important way to drive product sale is all sort of discounts. You can also define them in Scador Facts module,
simply by naming it and setting discount value.
##### Define Customer
Than PM has to define potential customer. PM needs to have some questions answered before client gets qualified for discounts. In this case PM can create set of classes in Scador Facts acting as questions to the customer.
On the beginning PM is just interested if Customer is veteran, what is value of the Car. You mark this classes as 
not a part - they will not be priced and not go to the invoice.

Last but not least PM needs to define constraints. How to do it its out of PMs scope however he has to
pass down the requirements to Developer. In bigger organizations issue tracking system and some form
of Change Management process will be highly beneficial.
### Benefits
PM acts with easy to use datastore, has access to key factors of the product and can edit data anytime. 


##Case B: Define the constraints.
### Actor
Developer - a person setting up logical constraints, creates user interface of online insurance configurator.

### Input
Set of requirements provided by PM in "Case A".

### Steps
##### Define interface structure.
Developer is using Scador Developer module to create new project and base Figure (.fig) file. Modeler has to
create view block and UI structure. He has common set of widgets to use line single select dropdown, radio
button group, radio button group with quantity fields etc. He has to decide which UI elements will fit best customer classes and component selection classes set up by PM. 
Selection of components will define base price and selection of customer "features" will influence discounts.

View structure is made using simplistic definition language. There is syntax highlighting and set of
handy presets/templates to boost productivity.
##### Writing the rules
Now its time to write constraints. At the very basic system will work with no rules. It will just accept 
user selections of product components and apply no discounts. Its good for sanity test because you can
launch configurator UI right after you define single element in UI structure document. UI is compiled
and launched almost instantly. It will be real pleasure to work in such quick create and test cycle. 
To be entirely true there are some default rules applied by the system.
To get real benefits of Scador MC some rules must be added. In fact to see Scador MC at the full swing you
may add a LOT of it. Scador MC is using Drools DSL syntax. It requires knowledge of logic and
Drools DLS constructs, luckily we are provide bunch or templates for most popular rules and we will
try to expand sample catalog as we have more feedback from the users.
Once ready Modeler gives a sign to PM to do acceptance testing.
### Benefits.
Simple and productive rule authoring environment. Works without any rules defined, Very fast create and test development cycle. 
## Case C: Customer enters the stage.
### Actor
Customer - person interested in car insurance, entering configurator page thru Google AdWords campaign.
### Input
PM after "Case B" approved configurator UI and published it to production. Marketing team started Google AdWords campaign
and linked it to landing page with product configurator.
### Steps
##### Component selection
Customer selects components variants of the car insurance. Selects coverage levels. Customer can see List price of
selected components and smaller potential price how numbers will look if few discounts would be applied.
##### Discount qualification
Customer answers questions about himself. If customer choice is linked to some discount rules instant price change
is applied. 
##### Finalizing order
Customer gets finally to the point where he/she is satisfied with the price, decides to buy it. At this point
System creates quote in the system, locks the price and transfers Customer to either eCommerce payment system
### Benefits
Customer can work without time and sales pressure. Customer can freely play with final price and get best available 
deal. There is no sales person engagement product can be sold simultaneously at fixed operational price.
 