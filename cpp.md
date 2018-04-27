## Notes on c++

```
using std::vector; // to avoid repeating the std:: part

size_t  // can hold any object's size
vector<int>::size_type // better to use size_type

v.begin();         // iterator for first element
v.end()            // iterator for one past last element
v.size()           // size of vector
v.push_back(e)     // add element to the end of a vector
v.rbegin(), v.rend() // reverse iterators, last and one before first

sort(b, e)  // sort in place; b and e are iterators
max(e1, e2) // larger of two elements that have the same type

c.empty()   // is container empty?
c.insert(d, b, e) // copy elements from b and e and inserts them before d
c.erase(it), c.erase(b,e) // remove it or range from b to e
*it // value of element indicated by iterator it
it->x // same as (*it).x

s.substr(i,j) // substring

v.reserve(n) // reserve space for n elements
v.resize(n)  // change size to n

back_inserter(c)
front_inserter(c)
inserter(c, it)

accumulate(b, e, t)
find(b, e, t)
find_if(b, e, p)
search(b, e, b2, e2)
copy(b, e, d)
remove_copy(b, e, d, t)
remove_copy_if(b, e, d, p)
remove_if(b, e, p)
remove(b, e, t)
transform(b, e, d, f)
partition(b, e, p)
stable_partition(b, e, p)

Exception classes:
logic_error
length_error
invalid_argument
out_of_range
domain_error
range_error
invalid_argument
overflow_error
underflow_error
runtime_error
```

---

- `NDEBUG` flag for "not debugging"

- With R, it's defined by default

- Use `-UNDEBUG` in `~/.R/Makevars` to turn force it to be undefined
