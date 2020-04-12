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
Rearranges the elements in the range \[first,last), in such a way that the elements before middle are the smallest elements in the entire range and are sorted in ascending order, while the remaining elements are left without any specific order.
<pre>
<code>
vector&lt;int&gt; vect{9, 8, 7, 6, 5, 4, 3, 2, 1};
partial_sort(vect.begin(), vect.begin()+5, vect.end());
print(vect);  //1 2 3 4 5 9 8 7 6
</code>
</pre>
