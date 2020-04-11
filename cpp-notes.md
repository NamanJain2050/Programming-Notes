# Vectors
## Initialize a vector
<pre>
<code>
//1.
vector<int> vect;
vect.push_back(10);
vect.push_back(20);
vect.push_back(30);

//2.
//create a vector of size n with all values of 10
vector<int> vect(n, 10);

//3.
//C++11
vector<int> vect{10, 20, 30};
</code>
</pre>
## Insert in vector at a particular position
<pre>
<code>
vector<int> vect{1,2,3};

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
