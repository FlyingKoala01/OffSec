## Union
The *UNION* lets you execute one or more additional **select** queries and append the results to the orignal query:
	`SELECT a, b FROM table1 UNION SELECT c, d FROM table2`

This SQL query will return a single result set with two columns, containing values from columns `a` and `b` in `table1` and columns `c` and `d` in `table2`.


>[!done] For a `UNION` query to work
> - The individual queries must return the same number of columns.
> - The data types in each column must be compatible between the individual queries

>[!done] To carry out a SQLi `UNION` attack
>- How many columns are being returned from the original query?
>- Which columns returned from the original query are of a suitable data type to hold the results from the injected query?

