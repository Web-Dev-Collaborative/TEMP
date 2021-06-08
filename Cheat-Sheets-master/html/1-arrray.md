The Array data structure
========================

Definition
----------

> An Array data structure, or simply an Array, is a data structure consisting of a collection of elements (values or variables), each identified by at least one array index or key. The simplest type of data structure is a linear array, also called one-dimensional array. **From [Wikipedia](https://en.wikipedia.org/wiki/Array_data_structure)**

Arrays are among the oldest and most important data structures and are used by every program. They are also used to implement many other data structures.

Complexity
----------

<table><thead><tr class="header"><th>Average</th><th> </th><th> </th><th> </th></tr></thead><tbody><tr class="odd"><td>Access</td><td>Search</td><td>Insertion</td><td>Deletion</td></tr><tr class="even"><td>O(1)</td><td>O(n)</td><td>O(1)</td><td>O(n)</td></tr></tbody></table>

To get a full overview of the time and space complexity of the Array data structure, have a look to this excellent [Big O cheat sheet](http://bigocheatsheet.com/).

The code
--------

------------------------------------------------------------------------

     class MyArray {
        constructor() {
            this.array = [];
        }
        add(data) {
            this.array.push(data);
        }
        remove(data) {
            this.array = this.array.filter(function (current) {
                return current !== data;
            });
        }
        search(data) {
            let foundIndex = this.array.indexOf(data);
            if (~foundIndex) {
                return foundIndex;
            }
            return null;
        }
        getAtIndex(index) {
            return this.array[index];
        }
        length() {
            return this.array.length;
        }
        print() {
            console.log(this.array.join(" "));
        }
    }

    let array = new MyArray();
    array.add(1);
    array.add(2);
    array.add(3);
    array.add(4);
    array.print(); // => 1 2 3 4
    console.log("search 3 gives index 2:", array.search(3)); // => 2
    console.log("getAtIndex 2 gives 3:", array.getAtIndex(2)); // => 3
    console.log("length is 4:", array.length()); // => 4
    array.remove(3);
    array.print(); // => 1 2 4
    array.add(5);
    array.add(5);
    array.print(); // => 1 2 4 5 5
    array.remove(5);
    array.print(); // => 1 2 4

    /*
      1 2 3 4
    search 3 gives index 2: 2
    getAtIndex 2 gives 3: 3
    length is 4: 4
    1 2 4
    1 2 4 5 5
    1 2 4
    */

------------------------------------------------------------------------

------------------------------------------------------------------------

------------------------------------------------------------------------

[Source](http://blog.benoitvallon.com/data-structures-in-javascript/the-array-data-structure/)
