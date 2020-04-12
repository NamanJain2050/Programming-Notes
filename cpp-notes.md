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
## Copy a vector
<pre>
<code>
a = b;  //I don't know why I need it in notes.
</code>
</pre>
# Map
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
