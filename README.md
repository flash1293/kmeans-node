# kmeans-node
A javascript implementation of k-means clustering algorithm that includes one/two dimentional arrays, and supports objects with coordinates.

## Install
You can install kmeans-node using NPM:

```
npm install kmeans-node
```

## Usage
In order to use kmeans-node, you must first import it:

```js
var kmeans = require('kmeans-node');
```

Once kmeans has been imported, you can call kmeans on several types of data:
- one-dimensional arrays
- two-dimensional arrays
- arrays of objects

### One-dimentioanl array
A one-dimentional array can be clustered by calling `kmeans.array(array, numberOfMeans)`

```js
var data = [1,2,4,8,10,14,18,20];
var kMeansObject = kmeans.array(data, 4);
```

### Two-dimentional array
A two-dimentional array can be clustered by calling `kmeans.array2d(arrayOfArrays, numberOfMeans)`

```js
var data = [[1,2],[3,4],[7,8],[9,10],[13,14],[15,16],[22,23],[24,25]];
var kMeansObject = kmeans.array2d(array,4);
```

### Array of objects
It is possible to use this method, if points are releated with data. E.g. when grouping coordinates with other properties such as shopping malls, cafes, etc .. The method can be called by `kmeans.object(arrayOfObjects, numberOfMeans)`

```js
var data = [
  {x:1,y:2,data:"some data"},
  {x:3,y:4,data:"some data"},
  {x:7,y:8,data:"some data"},
  {x:9,y:10,data:"some data"},
  {x:13,y:14,data:"some data"},
  {x:15,y:16,data:"some data"},
  {x:22,y:23,data:"some data"},
  {x:24,y:25,data:"some data"}
];
var kMeansObject = kmeans.object(array, 4);
```

## Output
The result output of clustering is an array of objects. The output structure varies depending on the input data structure.

### One-dimensional array
```js
{ 
  value: "median", 
  sum: "sum of distance", 
  pre: "previous distance", 
  points: "array of mean's points" 
}
```

### Two-dimentioanl array
```js
{
  values: "array of length 2 that contains medians",
  sum: "sum of distance",
  pre: "previous distance",
  sum0: "distance of array[0]",
  sum1: "distance of array[1]",
  points: "array of mean's points"
}
```

### Array of objects
```js
{   
    x: "median of X",
    y: "median of Y",
    sum: "sum of distance",
    pre: "previous distance",
    sumX: "distance of X",
    sumY: "distance of Y",
    points: "array of mean's points" 
}
```

## MIT License
The MIT License (MIT)

Copyright (c) 2015 Abdullah Shahin

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
