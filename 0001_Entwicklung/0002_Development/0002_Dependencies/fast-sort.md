---
tags:
  - devdep
---
Mit Fast-Sort lässt sich ein Array sortieren. In die Funktionen  sort.asc() oder sort.desc() lassen sich weitere Funktionen einfügen, um zu bestimmen nach welchen Kriterien sortiert werden soll.


```
/**

* Sorts the given data based on the specified key and order.
* @param {Array} data - The data to be sorted.
* @param {string} key - The key to sort the data by (e.g., 'year', 'artists', 'title').
* @param {boolean} [isAscending=true] - The order of sorting, default is ascending.
* @returns {Array} - The sorted data.

*/

function sortData(data, key, isAscending = true) {

let sortedData;

switch (key) {

case 'year':

sortedData = isAscending ? sort(data).asc((u) => u.jahr) : sort(data).desc((u) => u.jahr);

break;

case 'artists':

sortedData = isAscending

? sort(data).asc((u) => u.expand.artists[0].name)

: sort(data).desc((u) => u.expand.artists[0].name);

break;

case 'title':

sortedData = isAscending ? sort(data).asc((u) => u.title) : sort(data).desc((u) => u.title);

break;

}

return sortedData;

}
```
