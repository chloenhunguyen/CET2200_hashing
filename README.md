
Hashing 
# Dictionaries (aka Maps)
* save data based on `key` -> value 
for example: A -> 01 ; B -> 02 

## Operation functions: 
`put (key , value)` // (add/update)
`get (key)` 
`containsKey (key)` // (check key)
`remove (key)`
`size ()`  

## Problem: Array and Linked / Dictionary O(n) if get(key) 
## —> Problem solved: DIRECT ACCESS MAP 
O(1) fro everything
get value at given index BUT the tradeoffs: 
* wasted space 
* only integer keys

# HASHING 
* translating a piece of data to an int 
* definition: any functions that can be used to map data of arbitrary size to fixed-size values 

`%` mod / modulo - give back the remainder of dividend 

KEY
 ↓
Hash Function
 ↓
Integer
 ↓
% tableSize
 ↓
Valid Array Index 

--- 
key 18
  ↓
18 % tableSize
  ↓
index 8
  ↓
store/find value there

---- 

## COLLISIONS

->  multiple keys translate to the same location of the array

Collision
   │
   ├── Separate Chaining
   │
   └── Open Addressing
          ├── Linear Probing
          └── Quadratic Probing 


## Separate chaining  
● turn each element of the array into a “bucket” that can hold multiple items 
If multiple things hash to the same index, then we’ll  
just put all of those in that same index bucket. Often,  
you’ll see the data structure chosen is a linked-list  
like structure

### Load Factor λ 
$\[ \lambda = \frac{n}{c} \]$
n = number of key-value pairs
c = capacity của array 

### Good Hash Function
1. String -> Integer 
	hashCode % array.length 
2. Deterministic 
3. Uniform 

## Open addressing 
● If there is a collision, apply a 2nd formula to find a new location that is hopefully  
empty, repeat until an empty location is found

**Type 1: Linear Probing** 
	If there is a collision, keep checking the next element until we find an open spot. 

	Problem: Primary Clustering 
	When probing causes long chains of  
	occupied slots within a hash table

**Type 2: Quadratic Probing** 
	Instead of checking i past the original location, check i² from the original location

	$\[ index=(hash+i^2)\%tableSize \]$

	Problem: If λ ≥ ½ we might never find an empty spot -> Infinite loop!

