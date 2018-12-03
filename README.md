# northwind-normalized-2x
"polished" Northwind traders operational database

This is a PostgreSQL script for creating a traditional Northwind traders operational database sample.

<b>"2x":</b>
<br/>
This dataset is actually made of 2 very similar Northwind datasets - this is why "2x". Northwind "orders" table is actually doubled in a continuous way - 2nd dataset's orders "continue" on the 1st datasets'. There is no overlapping in order dates. OrderItems stay the same - 1st dataset's 1st order items are the same as 2nd dataset's 1st order items, but they are also "doubled" up and each of the "twin tuples" references its own order.

<b>"normalized":</b>
<br/>
2 Northwind datasets that I had were quite denormalized. I normalized most of the database "by the book". Tables have their primary keys, but also foreign keys defined. ER database model is included.

<b>For even more polishing...</b>
<br/>
There are some inconsistencies due to e.g. versioning. E.g. there are cases where a customer obviously had their name changed and for that reason a new tuple was created. This is why customer name, address and shipping city where not removed from orders by normalizadion and were left as attributes. Feel free to find a way to resolve these "issues". 
Probably even more minor inconsistencies can be encountered, but I decided this was already "clean" enough.

<br/>
<b>How to...</b>
<br/>
This is a script to c/p in your SQL editor and just click "run".
<br/>
Doing this in a separate schema (instead of schema "public") is recomended.
To do so, uncomment the first two lines of the script.
