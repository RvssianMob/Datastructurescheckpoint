# Datastructurescheckpoint

Problem 1: Sum of Distinct Elements

Description

Given two sets of elements, find the sum of all distinct elements from the set. In other words, find the sum of all elements which are present in either of the given set.
Inputs
       Set1: an array of integers
       Set2: an array of integers
Output
         Sum of distinct elements: an integer
Algorithm
   1. Initialize sum to 0
   
   2. For each element x in Set1, do the following: a. If x is not in Set2, add x to sum
   
   3. For each element y in Set2, do the following: a If y is not in Set1, add y to sum
Return sum.

JavaScript Code.
 
function sumOfDistinctElements(set1, set2) {
  let sum = 0;
  for (let i = 0; i < set1.length; i++) {
    if (!set2.includes(set1[i])) {
      sum += set1[i];
    }
  }
  for (let i = 0; i < set2.length; i++) {
    if (!set1.includes(set2[i])) {
      sum += set2[i];
    }
  }
  return sum;
}

// Example 
const set1 = [3, 1, 7, 9];
const set2 = [2, 4, 1, 9, 3];
const sum = sumOfDistinctElements(set1, set2);
console.log(sum); // Output: 13


Problem 2: Orthogonal Vectors

Description
Write an algorithm that determines, for n pairs of given vectors, whether two vectors of given IR are orthogonal, by calling the dot_product procedure defined in the previous question. The dot product of two orthogonal vectors is zero.

Inputs

     Vectors: an array of arrays of integers

Output
     
      List of orthogonal vectors
Algorithm

  1. For each pair of vectors v1 and v2 in Vectors, do the following: a. Call the dot_product procedure with v1 and v2 as input parameters, and store the result in ps b. If ps is equal to 0, print "Vectors v1 and v2 are orthogonal" c. Otherwise, print "Vectors v1 and v2 are not orthogonal"

  2. End loop.


JavaScript Code.

function dotProduct(v1, v2) {
  let ps = 0;
  for (let i = 0; i < v1.length; i++) {
    ps += v1[i] * v2[i];
  }
  return ps;
}

function orthogonalVectors(vectors) {
  for (let i = 0; i < vectors.length; i += 2) {
    const v1 = vectors[i];
    const v2 = vectors[i + 1];
    const ps = dotProduct(v1, v2);
    if (ps === 0) {
      console.log(`Vectors ${v1} and ${v2} are orthogonal`);
    } else {
      console.log(`Vectors ${v1} and ${v2} are not orthogonal`);
    }
  }
}

// Example 
const vectors = [
  [1, 2, 3],
  [4, 5, 6],
  [1, 0, 0],
  [0, 1, 0],
  [1, 1, 1],
  [1, -1, 0],
];
orthogonalVectors(vectors);
