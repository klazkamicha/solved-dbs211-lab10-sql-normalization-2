Download Link: https://assignmentchef.com/product/solved-dbs211-lab10-sql-normalization-2
<br>
<strong>Objective:</strong>

<ul>

 <li>To continue the <strong>normalization</strong> of user views from <strong>1NF</strong> to <strong>2NF and 3NF</strong></li>

 <li>How to identify and remove <strong>partial dependencies</strong></li>

 <li>How to identify and remove <strong>transitive dependencies</strong></li>

</ul>

<strong>Definitions:</strong>

<u>Definition</u><strong>: </strong>A relation is in 1NF if it contains no multi-valued dependencies (also known as repeating groups).

<u>Definition</u><strong>: </strong>A relation is in 2NF it is in 1NF and it contains no <u>Partial Dependencies.</u>

<u>Definition</u>:<strong>  </strong>A Partial Dependency occurs when a non-key attribute(s) is dependent on (or is determined by) a part of a composite primary key.

<u>Definition</u><strong>: </strong>A relation is in 3NF it is in 2NF and it contains no <u>Transitive Dependencies.</u>

<u>Definition</u><strong>:  </strong>A Transitive Dependency occurs when a non-key  attribute (s) is dependent on (or is determined by) another non-key attribute.

<strong>Instructions:</strong>

<strong>Part A (Second Normal Form (2NF))</strong>

Note: A relation that has only a simple primary key cannot have any partial dependencies!

<ol>

 <li>Examine the following report:</li>

</ol>

<strong>                                                             Premiere Corporation</strong>

<strong>Customer Orders</strong>

<table width="641">

 <tbody>

  <tr>

   <td width="107"><strong>Customer Number</strong></td>

   <td width="107"><strong>Name</strong></td>

   <td width="107"><strong>Order Number</strong></td>

   <td width="107"><strong>Order Date</strong></td>

   <td width="107"><strong>Sales Rep</strong></td>

   <td width="107"><strong>Rep Last Name</strong></td>

  </tr>

  <tr>

   <td rowspan="2" width="107">124</td>

   <td rowspan="2" width="107">Sally Adams</td>

   <td width="107">12489</td>

   <td width="107">2016-09-02</td>

   <td rowspan="2" width="107">03</td>

   <td rowspan="2" width="107">Jones</td>

  </tr>

  <tr>

   <td width="107">12500</td>

   <td width="107">2016-09-05</td>

  </tr>

  <tr>

   <td width="107">256</td>

   <td width="107">Ann Samuels</td>

   <td width="107">12495</td>

   <td width="107">2016-09-04</td>

   <td width="107">06</td>

   <td width="107">Smith</td>

  </tr>

  <tr>

   <td width="107">311</td>

   <td width="107">Don Charles</td>

   <td width="107">12491</td>

   <td width="107">2016-09-02</td>

   <td width="107">12</td>

   <td width="107">Diaz</td>

  </tr>

  <tr>

   <td width="107">315</td>

   <td width="107">Tom Daniels</td>

   <td width="107">12494</td>

   <td width="107">2016-09-04</td>

   <td width="107">06</td>

   <td width="107">Smith</td>

  </tr>

  <tr>

   <td rowspan="2" width="107">522</td>

   <td rowspan="2" width="107">Mary   Nelson</td>

   <td width="107">12498</td>

   <td width="107">2016-09-05</td>

   <td rowspan="2" width="107">12</td>

   <td rowspan="2" width="107">Diaz</td>

  </tr>

  <tr>

   <td width="107">12504</td>

   <td width="107">2016-09-05</td>

  </tr>

 </tbody>

</table>




<strong><u>Step 1</u></strong><strong>: </strong>

Create the UNF relation by creating a relation composed of all the attributes found in the User View. Don’t forget to underline the primary key and place brackets around any multi-valued dependencies (also known as repeating groups) you may find.

<u>UNF</u>:

UNF:   Customer [ CK <strong><u>CustNo</u></strong>, CustName, RepNo, RepName,( OrderNo, OrderDate )]

<strong>____________________________________________________________________________________________</strong>

<strong><u>Step 2</u></strong><strong>:</strong>

Create the 1NF relations by resolving the multi-valued dependencies (also known as repeating groups):

<u>1NF</u>

Now you are ready to create the 2NF relations by resolving the partial dependencies from the 1NF relations.

Your 1NF solution should look something like this:1NF:   Customer [ CK <strong><u>CustNo</u></strong>, CustName, RepNo, RepName ]Cust_Order [CK <strong><u>OrderNo</u></strong>, OrderDate, FK CustNo ]

Note: if you did not get a similar solution, please talk to your instructor about it now! It is very important to get the correct UNF and 1NF relations.

<strong><u>Step 3</u></strong><strong>: </strong>

The process for taking a relation from 1NF to 2NF involves resolving the partial dependencies. We see that from our definition of 2NF (page 1) a partial Dependency is when a non-key attribute is determined by a part of the primary key. We also read in the note (page 1) that we cannot have partial dependencies when there is a one-part Primary Key).




1NF:   Customer [ CK <strong><u>CustNo</u></strong>, CustName, RepNo, RepName ]Cust_Order [CK <strong><u>OrderNo</u></strong>, OrderDate, FK CustNo ]

Now examine the CustOrder relation.  Does it have a composite primary key ( a key made up of more than 1 field) ?  ____________

Identify the key attributes._________________________________

Identify the non-key attributes. _____________________________

Are any of the non-key attributes determined by ONE of the key attributes? _______________________

Which non-key attributes are determined by only one of the PK attributes?

________________________________________.

<u>We must create new relations for the partial dependencies</u>.

Write the 3 possible PK’s:

[<u>CustNo</u> ,

<u>[OrderNo</u> ,

[<u>CustNo, OrderNo</u> ,




Place all non-key attributes on the appropriate table (hint: choose the table with the least parts.




<strong>Second Normal Form 2NF</strong>:




CUSTOMER   [ <u>CustNo</u>,

ORDER          [ <u>OrderNo</u>

CUSTORDER [ <u>CustNo, OrderNo,</u>




1NF:   Customer [ CK <strong><u>CustNo</u></strong>, CustName, RepNo, RepName ]Cust_Order [CK <strong><u>OrderNo</u></strong>, OrderDate, FK CustNo ]

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong>Part B (Third Normal Form (3NF))</strong>




We now have a set of 2NF relations from our User View.  Your 2NF solution should look something like this:




2NF:

Customer [ <u>CustNo</u>, CustName,  RepNo, RepName ]

CustOrder [ <u>CustNo, OrderNo</u> ]

Order [ <u>OrderNo</u>, Orderdate ]




If you did not correctly identify the order relation, please ask your instructor about this process now!




We are now ready to identify any transitive dependencies we may have.




Note: <u>A relation that has no transitive dependencies is already in 3NF!</u>




<ol>

 <li>Examine each of the 2NF relations and determine the following:</li>

</ol>




<strong>Customer relation</strong>:        Key attributes ___________________________________




Non-key attributes: ________________________________




<strong>CustOrder relation</strong>        Key attributes ___________________________________




Non-key attributes ___________________________________







<strong>Order relation</strong>               Key attributes ____________________________________




Non-key attributes: ___________________________________




<strong>Note</strong>: if a relation contains less than 2 non-key attributes, there cannot be any transitive dependencies. Therefore the CustOrder and Order relations cannot contain any transitive dependencies! <u>Simply copy those relations to the 3NF solution.</u>




Examine non-key attributes of the Customer relation.  Do any of the non-key attributes determine any of the other non-key attributes? __________

If you answered yes, you are right.  Fill in the blanks:

____________________________   is determined by ________________




<ol start="2">

 <li><u>We must create a new relation for the transitive dependency</u>. We do this by moving the non-key attributes involved in the transitive dependency to a new relation. The primary key of the new relation will be the non-key attribute that determines the other non-key attributes involved in the transitive dependency.</li>

</ol>




Write the DBDL for the new relation:




REP [                                                                                 ]




<ol start="3">

 <li>The last step in resolving the transitive dependency is to maintain the link (or relationship) between the relation that contained the transitive dependency (Customer) and the new relation (Rep). We do this by placing a foreign key to the new relation (Rep)  into the relation that contained the transitive dependency (Customer). The foreign key will be the primary key of the new relation. Don’t forget to identify it with <strong>(FK)</strong></li>

</ol>







<u>Complete the 3NF solution</u><strong>:</strong>




3NF:




CUSTORDER [ <u>CustNo, OrderNo</u> ]

ORDER [ <u>OrderNo</u>, Orderdate ]

CUSTOMER [<u>CustNo</u>, CustName,                     ] (fill in the foreign key)

REP [                                                   ]

<strong></strong>3NF:   Customer             [ CK <strong><u>CustNo</u></strong>, CustName, FK RepNo ]Cust_Order           [ CK <strong><u>OrderNo</u></strong>, OrderDate, FK CustNo ]Reps                     [ CK <strong><u>RepNo</u></strong>, RepName ]

<strong> </strong>

<strong> </strong>

<strong>Last Section:</strong>




<strong>Lab 10 Submission:</strong>

<strong> </strong>

<strong>For the following User View, determine the 1, 2 and 3NF and hand in this page only to your instructor. The UNF relation has been provided.</strong>

<strong> </strong>

<strong>Premiere Corporation</strong>

<strong>Order Detail Report</strong>

<strong> </strong>

<table width="676">

 <tbody>

  <tr>

   <td width="66"><strong>Order Number</strong></td>

   <td width="103"><strong>Order Date</strong></td>

   <td width="84"><strong>Cust Number</strong></td>

   <td width="84"><strong>Cust Last Name</strong></td>

   <td width="84"><strong>Part Number</strong></td>

   <td width="84"><strong>Part Desc</strong></td>

   <td width="84"><strong>Qnty Ordered</strong></td>

   <td width="84"><strong>Quoted Price</strong></td>

  </tr>

  <tr>

   <td width="66">12489</td>

   <td width="103">2016-09-02  124</td>

   <td width="84">124</td>

   <td width="84">Adams</td>

   <td width="84">AX12</td>

   <td width="84">Iron</td>

   <td width="84">11</td>

   <td width="84">14.95</td>

  </tr>

  <tr>

   <td rowspan="3" width="66">12491</td>

   <td rowspan="3" width="103">2016-09-02  311</td>

   <td rowspan="3" width="84">311</td>

   <td rowspan="3" width="84">Charles</td>

   <td width="84">BT04</td>

   <td width="84">GasGrill</td>

   <td width="84">3</td>

   <td width="84">440.00</td>

  </tr>

  <tr>

   <td width="84">BZ66</td>

   <td width="84">Washer</td>

   <td width="84">1</td>

   <td width="84">399.99</td>

  </tr>

  <tr>

   <td width="84">CX11</td>

   <td width="84">MiniBlender</td>

   <td width="84">1</td>

   <td width="84">11.98</td>

  </tr>

  <tr>

   <td width="66">12494</td>

   <td width="103">2016-09-04</td>

   <td width="84">315</td>

   <td width="84">Daniels</td>

   <td width="84">CB03</td>

   <td width="84">Bike</td>

   <td width="84">4</td>

   <td width="84">279.96</td>

  </tr>

  <tr>

   <td width="66">12495</td>

   <td width="103">2016-09-04</td>

   <td width="84">256</td>

   <td width="84">Samuels</td>

   <td width="84">CX11</td>

   <td width="84">MiniBlender</td>

   <td width="84">2</td>

   <td width="84">23.96</td>

  </tr>

  <tr>

   <td rowspan="2" width="66">12498</td>

   <td rowspan="2" width="103">2016-09-05</td>

   <td rowspan="2" width="84">522</td>

   <td rowspan="2" width="84">Nelson</td>

   <td width="84">AZ52</td>

   <td width="84">Dartboard</td>

   <td width="84">2</td>

   <td width="84">12.96</td>

  </tr>

  <tr>

   <td width="84">BA74</td>

   <td width="84">Basketbal</td>

   <td width="84">4</td>

   <td width="84">24.96</td>

  </tr>

  <tr>

   <td width="66">12500</td>

   <td width="103">2016-09-05</td>

   <td width="84">124</td>

   <td width="84">Adams</td>

   <td width="84">BT04</td>

   <td width="84">GasGrill</td>

   <td width="84">1</td>

   <td width="84">149.99</td>

  </tr>

  <tr>

   <td width="66">12504</td>

   <td width="103">2016-09-05</td>

   <td width="84">522</td>

   <td width="84">Nelson</td>

   <td width="84">CZ81</td>

   <td width="84">Treadmill</td>

   <td width="84">2</td>

   <td width="84">325.98</td>

  </tr>

 </tbody>

</table>

<strong>UNF:</strong>

<strong>Order</strong> [<strong>CK </strong><u>OrderNo</u>, Orderdate, CustNo, CustLname, (PartNo, PartDesc, QtyOrd, Price)]

<strong> </strong>

<strong>1NF:</strong>

<strong>Order</strong> [<u>OrderNo</u>, Orderdate, FK <u>CustNo</u>, CustLname]

<strong>Parts</strong> [<u>PartNo</u>, FK <u>OrderNo,</u> PartDesc, QtyOrd, Price]




<strong>2NF:</strong>

<strong>Order</strong> [<u>OrderNo</u>, Orderdate]

<strong>CustOrder</strong> [FK <u>CustNo</u>, FK <u>OrderNo</u>]

<strong>Customer</strong> [<u>CustNo</u>, CustLname]

<strong>Parts</strong> [<u>PartNo</u>, PartDesc, Price]

<strong>PartOrder</strong> [FK <u>OrderNo</u>, FK <u>PartNo</u>, QtyOrd]




<strong>3NF:</strong>

<strong>Order</strong> [<u>OrderNo</u>, Orderdate]

<strong>CustOrder</strong> [FK <u>CustNo</u>, FK <u>OrderNo</u>]

<strong>Customer</strong> [<u>CustNo</u>, CustLname]

<strong>PartOrder</strong> [FK <u>OrderNo</u>, FK <u>PartNo</u>, QtyOrd]

<strong>Parts</strong> [<u>PartNo</u>, FK <u>PartDesc</u>]

<strong>PricePart</strong> [<u>PartDesc</u>, Price]