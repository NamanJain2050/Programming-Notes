# Vectors
## Initialize a vector
<pre>
<code>
//1.
vector&lt;int&gt; vect;
vect.push_back(10);
vect.push_back(20);
vect.push_back(30);

//2.
//create a vector of size n with all values of 10
vector&lt;int&gt; vect(n, 10);

//3.
//C++11
vector&lt;int&gt; vect{10, 20, 30};
</code>
</pre>
## Insert in vector at a particular position
<pre>
<code>
vector&lt;int&gt; vect{1,2,3};

//insert at front (0 index)
vect.insert(vect.begin(), 0);

//insert at index 2
vect.insert(vect.begin()+2, 9);
</code>
</pre>
## Erase from vector at a particular position
<pre>
<code>
vector&lt;int&gt; vect{1,2,3};

//insert at front (0 index)
vect.erase(vect.begin());

//insert at index 1
vect.insert(vect.begin()+1);
</code>
</pre>
PS: Cannot use reverse iterator in erase function. To erase last element, use <b> vect.pop_back() </b>
## Copy a vector
<pre>
<code>
a = b;  //I don't know why I need it in notes.
</code>
</pre>
## Max element in a vector
<pre>
<code>
*max_element(a.begin(), a.end());
</code>
</pre>
## Find an element in vector
<pre>
<code>
auto it = find(begin(vec), end(vec), item); //std::algorithm
</code>
</pre>
# Multiset
## Erase in multiset
ms.erase(3); will erase all instances of 3 from multi_set. If you want to only erase one instance of 3, do <br>
ms.erase(ms.lower_bound(3));
# Map
## How to iterate over a map
<pre>
<code>
//1.
for (auto i : m)
  cout << i.first << " " << i.second;
  
//2.
for (auto i = m.begin(); i != m.end(); i++)
  cout << i->first << " " << i->second;
  

</code>
</pre>
## How to delete a key in map
<pre>
<code>
mp.erase(actual_key)
</code>
</pre>
## How to sort a map by value
<pre>
<code>

bool comp(pair&lt;string, int&gt;& a, pair&lt;string, int&gt;& b) {
  return a.second < b.second;
}
unordered_map&lt;string, int&gt; mp;
mp["I"] = 1;
mp["J"] = 2;
mp["K"] = 3;

vector&lt;pair&lt;string, int&gt;&gt; vect(mp.begin(), mp.end()); //initialize vector with map pairs
sort(vect.begin(), vect.end(), comp);
</code>
</pre>
# Strings
## Comparing strings
Operators <, <=, >, >= compare strings <b>lexicographically, character by character and are case-sensitive.</b>
<pre>
<code>
"A" < "B"
"App" < "Apple"
"help" > "hello"
"Apple" < "apple"
</code>
</pre>
The last one might be a bit confusing, but the ASCII value for 'A' is 65, and comes before 'a', whose ASCII value is 97. So "Apple" comes before "apple".
# Heaps
<pre>
<code>
vector&lt;int&gt; A {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
make_heap(A.begin(), A.end());    //max-heap
print(A);   //9 8 6 7 4 5 2 0 3 1 

A.push_back(10);
push_heap(A.begin(), A.end());
print(A);   //10 9 6 7 8 5 2 0 3 1 4

pop_heap(A.begin(), A.end());
A.pop_back();
print(A);   //9 8 6 7 4 5 2 0 3 1 

sort_heap(A.begin(), A.end());    //ascending order
print(A);   //0 1 2 3 4 5 6 7 8 9 
</code>
</pre>
# Priority Queue
<pre>
<code>
//1. Initialize a PQ
// by default we have max-heaps
priority_queue&lt;int&gt; pqueue;

//2. Push an element
pqueue.push(3);
pqueue.push(5);
pqueue.push(1);
pqueue.push(2);   //becomes 5,3,2,1

//3. Pop an element
pqueue.top()      //returns top element
pqueue.pop()      //removes top element, returns void

//4. comparator (< sign means maxx heap; > sign means min heap)
struct cmp {
  bool operator()(vector<int>& v1, vector<int>& v2) { 
    return dist(v1[0], v1[1]) < dist(v2[0], v2[1]);
  }
};
</code>
</pre>
# Sorting
## sort()
<pre>
<code>
vector&lt;int&gt; vect{50, 40, 30, 20, 10};
sort(vect.begin(), vect.end());
print(vect);  //10 20 30 40 50 
</code>
</pre>
## partial_sort()
Rearranges the elements in the range \[first,last), in such a way that the <b>elements before middle</b> are the smallest elements in the entire range and are sorted in ascending order, while the remaining elements are left without any specific order.
<pre>
<code>
vector&lt;int&gt; vect{9, 8, 7, 6, 5, 4, 3, 2, 1};
partial_sort(vect.begin(), vect.begin()+5, vect.end());
print(vect);  //1 2 3 4 5 9 8 7 6
</code>
</pre>
## nth_element()
Rearranges the elements in the range \[first,last), in such a way that the element at the nth position is the element that would be in that position in a sorted sequence. The other elements are left without any specific order, except that none of the elements preceding nth are greater than it, and none of the elements following it are less. If this points to last, the function call has no effect.
<pre>
<code>
vector&lt;int&gt; vect{1, 2, 3, 4, 5, 6, 7, 8, 9};
nth_element(vect.begin(), vect.begin()+5, vect.end());
print(vect);  //3 1 4 2 5 6 9 7 8
</code>
</pre>
# Partitioning
## partition()
Rearranges the elements from the range \[first,last), in such a way that all the elements for which <b>pred returns true precede all those for which it returns false</b>. The iterator returned points to the first element of the second group. The relative ordering within each group is not necessarily the same as before the call.
<pre>
<code>
bool IsOdd (int i) {
  return (i%2)==1;
}
vector&lt;int&gt; vect{1, 2, 3, 4, 5, 6, 7, 8, 9};
partition(vect.begin(), vect.end(), IsOdd);
print(vect); //1 9 3 7 5 6 4 8 2
</code>
</pre>

## partition_point()
Returns the iterator that points to the first element of the second group. The elements in the range shall already be partitioned, as if partition had been called for this function to work as expected.

# Permutations
## next_permutation()
Rearranges the elements in the range \[first,last) into the next lexicographically greater permutation. If the function can determine the next higher permutation, it rearranges the elements as such and returns true. If that was not possible (because it is already at the largest possible permutation), it rearranges the elements according to the first permutation (sorted in ascending order) and returns false.

## prev_permutation()
Rearranges the elements in the range \[first,last) into the previous lexicographically ordered permutation.
# for_each v/s range-based for loops
## for_each
std::for_each is an STL algorithm that takes a collection of elements (in the form of a begin and end iterator) and a function (or function object), and applies the function on each element of the collection. It has been there since C++98.
<pre>
<code>
std::vector<int> numbers = {1, 2, 3, 4, 5};
std::for_each(begin(numbers), end(numbers), f);
</code>
</pre>
for_each allows to keep the abstraction level of the calling code by pushing implementation down into a dedicated function or function object, and replacing it with the function name as a label.
## range-based for
Range-based for loops are a native language construct present in many languages, and were added to C++11:
<pre>
<code>
std::vector<int> numbers = {1, 2, 3, 4, 5};
for (auto number : numbers)
{
    // do something with number
}
</code>
</pre>
Range-based for loops allow to write code directly at the loop site, but to keep expressiveness this code needs to be at the same abstraction level as the code surrounding the loop.
# std::begin() v/s vector::begin()
std::begin() was added in C++11 to make it easier to write generic code (e.g. in templates). <br>
<b> The most obvious reason for it is that plain C-style arrays do not have methods, hence no .begin(). </b><br>
So you can use std::begin() with C-style arrays, as well as STL-style containers having their own begin() and end().
# Extra algorithms
## lower_bound()
Returns an iterator pointing to the first element in the range \[first,last) which <b> does not compare less than val </b>.
<pre>
<code>
 10, 10, 20, 20, 30, 40, 50    //vector
 auto it = lower_bound(a.begin(), a.end(), 15);    //it points to first 20
</code>
</pre>
If the array/vector is sorted in decreasing order, lower_bound() finds iterator to the first element that does not compare greater than to given element
## upper_bound()
Returns an iterator pointing to the first element in the range \[first,last) which <b> compares greater than val </b>.
<pre>
<code>
 10, 10, 20, 20, 30, 40, 50    //vector
 auto it = upper_bound(a.begin(), a.end(), 20);    //it points to first 30
</code>
</pre>
If the array/vector is sorted in decreasing order, upper_bound() finds iterator to the first element that is smaller than the given element
Note: s.upper_bound(x) is faster than upper_bound(s.begin(), s.end(), x)
