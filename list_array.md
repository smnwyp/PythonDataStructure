* List and tuple
  * list
    * dynamic arrays
    * can modify and resize as we store it
    * store in consequtive blocks
    * larger in memory
    * add: `O(1)`
    * 
  * tuple
    * static arrays
    * content is fixed and immutable
    * **resource caching** 
      * is cached by runtime, no need to serve memory from kernel
      * for tuple of size `1-20`, up to `20k` of each size are not garbage collected for future use
      * means extra memory overhead
      * means less time (actually NO need) communicating with OS to allocate memory
      * 
    * more **lightweight** than list due to immutability
    * can concat 2 tuples, but will not allocate new space for it
    * add: `O(N)` -- because need to copy tuple 
    * 
  * search:  
    * worst case:`O(N)`
    * sorted: `O(logN)` -- use binary search
    * best case: if ordering known `O(1)` -- index lookup
    * python `bisect` module
* Dictionary and Set
  * They are probably the best-oiled data structure in the language
  * when no intrinsic order can be assumed
  * set is just a collection containing keys
  * <img width="1281" alt="Screenshot 2022-04-01 at 18 01 14" src="https://user-images.githubusercontent.com/83515400/161300153-96320e65-45a7-4453-9f32-eed171e05295.png">
  * underlying data structure: `open address hash table`
    * a hash function that turns an arbitrary key (str or obj) into an index for a list
    * the hash function and the list can later be used to determin where any particular piece of data is right away, without a search 
  * downside:
    * large footprint in memory
    * actual speed depends on hashing function...
  * dictionary contains both keys and values
    * hashable type `__eq__` and `__cmp__`
  * **lookup** on arbitrary index: `O(1)`
    * worst case is `O(n)` if the hash function is bad and results in a lot of collisions.
  * **insertion** : `O(1)`
  * how it works:
    Python's dictionary implementation reduces the average complexity of dictionary lookups to O(1) by requiring that key objects provide a "hash" function. Such a hash function takes the information in a key object and uses it to produce an integer, called a hash value. This hash value is then used to determine which "bucket" this (key, value) pair should be placed into.

* Iterator and Generator
  * how do generators save memory
  * what is the best usecase for generators
  * how to use itertools to create complex generator workflows
  * when to use lazy evaluation when not
  *  
