# Get in the robot Shinji
### **Purpose** - To practice:
  * When to select appropriate use of the Set and Map data structures
  * How to use the Set and Map classes in ES6 JavaScript
  
  
##

### Overview of __Set__ and __Map__ features -
* The _Map_ data structure (implemented under the hood by a HashTable) allows O(1) insertion of a key-value pair, O(1) deletion of a k-v pair, and O(1) lookup of a value for a key (wow!). However, the k-v pairs are __unordered__, so we sacrifice the ability to track exactly where in the Map a k-v pair is located.
* The _Set_ data structure (also usually implemented under the hood by a HashTable) holds a collection of elements like an array, but with some important differences:
  * Sets never contain duplicate elements
  * The elements are unordered, so we can't depend on knowing where in the set an element is located like in an index-based array
* For sacrificing element order in a Set, we get not only O(1) insertion and removal like with a HashMap, but also O(1) search to see if an element is present, vs O(n) search for an element in an unsorted array   

##
### **Description** - Complete the functions which map the input data - 
* For mock data, we are referencing the franchise _Neon Genesis Evangelion_, where certain humans can synchronize with particular biomechanical mecha robots (Eva Units) in order to pilot them  
* We have a collection of synchronization test results, each one containing the sucessful ability for particular human pilots to synchronize with a biomechanical Eva Unit at the time of the test
* Each sync test is respresnted as a map of of key-vlaue pairs with a pilot key to an Eva Unit value
##
### 1. Complete the function _mapCompatibleUnitsByPilot_:

* We want to take in an array of those tests, and respresent that data by a Map of pilots to a Set of all the Eva units they are compatible of synchronizing with (we don't want duplicate Eva unit values for a given pilot, or care about the order of their compatible Evas). 

#### For example, using an array of the following three sync test Maps:
``` 
[
  Map(2) { 'Rei' => 'Eva-00', 'Shinji' => 'Eva-01' },
  Map(2) { 'Shinji' => 'Eva-01', 'Asuka' => 'Eva-02' },
  Map(3) { 'Shinji' => 'Eva-00', 'Rei' => 'Eva-01', 'Asuka' => 'Eva-02' }
]
```

 Should return a Map with a key for every pilot:
```
Map(3) {
  'Rei' => Set(2) { 'Eva-00', 'Eva-01' },
  'Shinji' => Set(2) { 'Eva-01', 'Eva-00' },
  'Asuka' => Set(1) { 'Eva-02' }
}
```
* It should be able to run in O(n) time, where n = total number of k-v pairs in all the input maps, and O(n) space 

#
### 2. Complete the function _mapCompatiblePilotsByUnit_:

* We want to take the exact same input, but return a map this time as a Map of Eva units to 
a Set of all the pilots that can synchronize with that Eva. Just Like before, we can use a Set because 
we don't want duplicate pilots or care about their order. 

#### The same input
```
[
  Map(2) { 'Rei' => 'Eva-00', 'Shinji' => 'Eva-01' },
  Map(2) { 'Shinji' => 'Eva-01', 'Asuka' => 'Eva-02' },
  Map(3) { 'Shinji' => 'Eva-00', 'Rei' => 'Eva-01', 'Asuka' => 'Eva-02' }
]
```
Should return a map with a key for every Eva Unit:
```
Map(3) {
  'Eva-00' => Set(2) { 'Rei', 'Shinji' },
  'Eva-01' => Set(2) { 'Shinji', 'Rei' },
  'Eva-02' => Set(1) { 'Asuka' }
}
```
* It should also run in O(n) time, where n = total number of k-v pairs in all the input maps, and O(n) space

#
#### 3. If we used arrays instead of Sets for our final Map values, how would that change the time complexity for both problems, assuming we still didn't want duplicates in the map value arrays? 

 



