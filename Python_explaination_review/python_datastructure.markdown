### for loop
```python
    For l in listt:
    Pass
```
I >> represent loop **iteration variable** represent the element that the loop is currently processing  and it take its value from the **iterable** (listt)
By default it convert iterable object to **iterator** to use next

```python
#For Loop Already Calls iter() Method on The Iterable(list, tuple , set, dictionary,string) Behind The Scene.
words = {"python", "hangman", "programming", "challenge", "developer", "learning"}
myiterator= iter(words)
print(next(myiterator))
print(next(myiterator))
print(next(myiterator))
print(next(myiterator))
print(next(myiterator))
print(next(myiterator))
print(next(myiterator))  # it will print StopIteration 
```
# Data structure 
## list
اما ordered ------mutable اقدر اوصل له عن طريق الindex ارقام... و متغير اقدر اغير اى عنصر زى الlist []  
list is a data structure that allows you to store and manipulate a collection of items. Lists are mutable, which means you can change their content after they are created. They are very versatile and commonly used in Python programming.

Here's a breakdown of lists and their types, along with examples and commonly used functions:

### 1. List Basics:
A list in Python is defined by enclosing comma-separated values within square brackets `[ ]`.

```python
my_list = [1, 2, 3, 4, 5]
```
### 2. Types of Lists:
   - **Homogeneous Lists:** Contains elements of the same data type.like array
   - **Heterogeneous Lists:** Contains elements of different data types.

```python
homogeneous_list = [1, 2, 3, 4, 5]
heterogeneous_list = [1, 'two', 3.0, True]
```

### 3. Common List Operations and Functions:
   - **Accessing Elements:**
   

```python 
   print(my_list[0])  # Accessing the first element (indexing starts from 0)
    print(my_list[-1]) # Accessing the last element
    print(my_list[1:3])  # Slicing from index 1 to 2 (exclusive)
    my_list.append(6)  # Appends 6 to the end of the list
    my_list.insert(2, 'inserted')  # Inserts 'inserted' at index 2
    my_list.extend([6, 7, 8])  # Appends multiple elements to the end of the list
    my_list.remove(3)  # Removes the first occurrence of 3 value 
    my_list.clear()  # Removes all elements from the list
    del my_list[2]  # Deletes the element at index 2 from the list
    popped_element = my_list.pop()  # Removes and returns the last element and we can give it index
    print(len(my_list))  # Returns the number of elements in the list
    my_list.sort()  # Sorts the list in ascending order in the origion list itself
    sorted_list = sorted(my_list)   # Returns a new sorted list.
    sorted_by_second = sorted(<collection of tuples>, key=lambda el: el[1])
    sorted_by_both   = sorted(<collection of tuples>, key=lambda el: (el[1], el[0]))
    my_list.reverse()  # Reverses the elements of the list
    reversed_list = my_list[::-1]  # Reverses the list using slicing
    concatenated_list = my_list + [7, 8, 9]
    count = my_list.count(2)  # Returns the number of occurrences of 2 value in the list
    index = my_list.index(3)  # Returns the index of the first occurrence of 3
    is_present = 3 in my_list  # Returns True if 3 is present in the list, False otherwise
    copied_list = my_list.copy()  # Creates a shallow copy of the list
    any_true = any([False, True, False])  # Returns True if any element in the list is True
    all_true = all([True, True, True])    # Returns True if all elements in the list are True
    unique_elements = list(set(my_list))  # Removes duplicates by converting list to set and back to list

    txt = "apple#banana#cherry#orange"
    x = txt.split("#", 1)         # setting the maxsplit parameter to 1, will return a list with 2 elements! [apple, banana#cherry#orange]
    # Example of split method
    sentence = "I love eating fruits like apple, banana, and orange"
    word_list = sentence.split()
    print(word_list)
    # Output: ['I', 'love', 'eating', 'fruits', 'like', 'apple,', 'banana,', 'and', 'orange']
    # Example of join method
    words = ["apple", "banana", "orange", "grape"]
    joined_string = ", ".join(words)
    print(joined_string)
    # Output: "apple, banana, orange, grape"


    letters = ['a', 'b', 'c']
    numbers = [1, 2]
    zipped = list(zip(letters, numbers))  # Combines elements from both lists into tuples  [('a',1),('b',2)]

    #enumerate() ->it add index(counter) for iterable when making for loop
    for index, value in enumerate(my_list):  # Iterates over each element with its index  ((0,'a'),(1,'b')...)
        print(index, value)             
.   #it also delete the elements from enumerate tuples not the object as it fetch all element for the variable
    l1= ['ahmed', 10, 333.33, 'mina', True]
    l1_enum = enumerate(l1)
    for abbass, test in l1_enum:
        print(f"{abbass} : {test}")
    # # cast enum to alist
    items =list(l1_enum)
    print(items) # it will be empty
    
    # Unpacking
    listt= [1,2,3,4,5]  # Unpacking list must be the same number of the list
    frist,second,*remain=listt   
    print(frist,second,remain)
    # Output >> 1 2 [3, 4, 5]
    #we can use unpacking operator to make list or combine two list in the new list
    First=[1,2]
    Second=[3,4,5]
    values =[*first, "a", *second]
    print(values)
    # >> Output= [1,2,"a",3,4,5]  # as * operator unpack the elements
   
 
    filtered_list = list(filter(lambda x: x % 2 == 0, my_list))  # Filters elements based on a condition
    mapped_list = list(map(lambda x: x * 2, my_list))  # Applies a function to each element of the list
    from functools import reduce
    reduced_value = reduce(lambda x, y: x + y, my_list)  # Reduces the list to a single value using a function

    squares = [x**2 for x in range(10)]  # Creates a list of squares of numbers from 0 to 9
    evens = [x for x in my_list if x % 2 == 0]  # Creates a list of even numbers from my_list
    doubled = [x * 2 for x in my_list]  # Creates a list by doubling each element of my_list
    
```

----------
## tuple 

اما ordered ---------immutable مش متغير ما اقدرش اعدل عليه زى الmy_tuple =1,4 
ملحوظه ينفع اعدل قيمه للlist جوه الtuple () وال string برددو

so i can't insert on it or append or delete
### What is a Tuple?

A tuple in Python is similar to a list, but with one key difference: it's immutable. This means that once a tuple is created, its elements cannot be changed, added, or removed. Tuples are defined by enclosing comma-separated values within parentheses `( )`.

### Tuple Creation:
```python
my_tuple = (1, 2, 3, 4, 5)
```

### Types of Tuples:
   - **Homogeneous Tuples:** Contains elements of the same data type.
   - **Heterogeneous Tuples:** Contains elements of different data types.

```python
homogeneous_tuple = (1, 2, 3, 4, 5)
heterogeneous_tuple = (1, 'two', 3.0, True)
```

```python
# Accessing Elements
print(my_tuple[0])   # Accessing the first element (indexing starts from 0)
print(my_tuple[-1])  # Accessing the last element

# Tuple Slicing
print(my_tuple[1:3])  # Slicing from index 1 to 2 (exclusive)

# Tuple Operations
concatenated_tuple = my_tuple + (6, 7, 8)  # Concatenating Tuples
repeated_tuple = my_tuple * 3             # Repeating Tuples

# Common Tuple Functions and Methods
print(len(my_tuple))                  # Length of Tuple
count = my_tuple.count(2)             # Counting Occurrences
index = my_tuple.index(3)             # Finding Index
packed_tuple = 1, 2, 3                # Tuple Packing
a, b, c = packed_tuple                # Tuple Unpacking
# swapping two variable using tuple 
a=10 , b=12          
b,a= a,b                           
list_from_tuple = list(my_tuple)      # Tuple Conversion
combined_tuple = my_tuple + another_tuple  # Combining Tuples

# Additional Techniques and Functions
sorted_tuple = tuple(sorted(my_tuple))  # Tuple Sorting
is_present = 3 in my_tuple              # Membership Testing
copied_tuple = my_tuple[:]              # Copying Tuples
max_value = max(my_tuple)                  # Finding Maximum
min_value = min(my_tuple)                  # Finding Minimum
nested_tuple = ((1, 2), (3, 4), (5, 6))
flattened_tuple = tuple(item for sublist in nested_tuple for item in sublist)  # Flattening Nested Tuples
a, *rest = my_tuple                        # Tuple Unpacking with Asterisk

list_of_tuples = [(1, 2), (3, 4), (5, 6)]
# unpacking operator ( * ) remove the outer pracet (list[] or tuple() ) so it divide each element so the input to the zip will be each element as individual from list_of_tuples
tuple_of_lists = tuple(zip(*list_of_tuples))  # Converting List of Tuples to Tuple of Lists output >>> ((1, 3, 5), (2, 4, 6))

for index, value in enumerate(my_tuple):  # Enumerating Tuples
    print(index, value)
```

---------
## set 
اما unordered ---------mutable الset {} مفيش فيها تكرار تنفع لو ارقام تليفونات ولانها بتظهر عشوائى فى كل مره ينفع استخدمها فى عرض اسأله امتحان مثلا it take only the immutable elements as it hash every element

### What is a Set?

A set in Python is an unordered collection of unique elements. Sets are mutable, meaning you can add or remove elements, but the elements themselves must be immutable (e.g., numbers, strings, tuples). Sets are defined by enclosing comma-separated elements within curly braces `{ }`.

### Set Creation:
```python
my_set = {1, 2, 3, 4, 5}
```

### Types of Sets:
   - **Mutable Sets:** You can add or remove elements from these sets.
   - **Immutable Sets (Frozensets):** Once created, the elements cannot be changed.
```python
   # Types of Sets
mutable_set = {1, 2, 3}
immutable_set = frozenset({4, 5, 6})
```

```python
# Set Operations
union_set = my_set.union(mutable_set) # we can make it using this operator |
intersection_set = my_set.intersection(mutable_set) # we can make it using this operator &
difference_set = my_set.difference(mutable_set)       # we can make it using this operator -
symmetric_difference_set = my_set.symmetric_difference(mutable_set)      # we can make it using this operator ^
my_set |= mutable_set  # Updates my_set with the union of itself and mutable_set
my_set &= mutable_set  # Updates my_set with the intersection of itself and mutable_set
my_set -= mutable_set  # Updates my_set with the difference between itself and mutable_set
my_set ^= mutable_set  # Updates my_set with the symmetric difference between itself and mutable_set
equal_sets = my_set == mutable_set  # Checks if my_set and mutable_set contain the same elements

is_subset = my_set.issubset(mutable_set)  # Checks if my_set is a subset of mutable_set
is_superset = my_set.issuperset(mutable_set)  # Checks if my_set is a superset of mutable_set
is_disjoint = my_set.isdisjoint(mutable_set)  # Checks if my_set and mutable_set have no common elements

# Adding Elements
my_set.add(6)   # it add one element 
my_set.update({7, 8, 9})# it add more than one element

# Removing Elements
my_set.remove(3)  # Removes the element 3 from the set, raises KeyError if element doesn't exist
my_set.discard(10)  # Removes the element 10 from the set if it exists, otherwise does nothing
my_set.clear()  # Removes all elements from the set, making it empty

# Checking Membership
is_present = 3 in my_set  # Checks if the element 3 is present in the set

# Copying a Set
copied_set = my_set.copy()  # Creates a shallow copy of the set

# Additional Set Functions and Methods
print(len(my_set))  # Prints the number of elements in the set
set_from_list = set([1, 2, 3, 4, 5])  # Creates a set from a list
tuple_list = [(1, 2), (3, 4), (5, 6)]  # List of tuples
tuple_set = set(tuple_list)  # Creates a set from a list of tuples

list_from_set = list(my_set)  # Converts the set to a list
my_set.difference_update({3, 4, 5})  # Removes elements {3, 4, 5} from my_set
my_set.symmetric_difference_update(mutable_set)  # Updates my_set with the symmetric difference between itself and mutable_set

cartesian_product_set = {(x, y) for x in range(3) for y in range(3)}  # Creates a set of tuples representing the Cartesian product

# Set Comprehensions
squared_set = {x**2 for x in range(10)}  # Creates a set containing the squares of numbers from 0 to 9

```
------
# Dictonary 
الdictionary ..طلعت immutable اقدر اعدل فى الvalue ما اقدرش اعدل فى الkey و unordered


```python 
# Dictionary Creation
my_dict = {'key1': 'value1', 'key2': 'value2', 'key3': 'value3'}

# Accessing Values
value = my_dict['key1']  # Accessing the value associated with 'key1'

# Adding and Modifying Elements
my_dict['new_key'] = 'new_value'  # Adding a new key-value pair
my_dict['key1'] = 'updated_value'  # Modifying an existing value

# Removing Elements
del my_dict['key2']  # Deleting a key-value pair by key
my_dict.pop('key3')  # Removing a key-value pair by key 
my_dict.clear()      # Removing all key-value pairs from the dictionary

# Dictionary Methods
keys = my_dict.keys()     # Returns a view of keys in the dictionary as list
values = my_dict.values() # Returns a view of values in the dictionary as list
value = my_dict.get('key', 'default_value')  # Returns the value for 'key' if it exists, otherwise returns 'default_value'
items = my_dict.items()   # Returns a view of key-value pairs (tuples) in the dictionary
copied_dict = my_dict.copy()  # Creates a shallow copy of the dictionary
other_dict = {'key4': 'value4', 'key5': 'value5'}
my_dict.update(other_dict)    # Merges other_dict into my_dict, overwriting existing keys
length = len(my_dict)   # Returns the number of key-value pairs in the dictionary
is_present = 'key1' in my_dict   # Returns True if 'key1' is present in the dictionary

#join
myDict= {"name": "John", "country": "Norway"}
mySeparator = "TEST"
x = mySeparator.join(myDict)
# More Advanced Techniques and Functions
keys = ['a', 'b', 'c']
values = [1, 2, 3]
combined_dict = dict(zip(keys, values))  # Creates a dictionary from two lists

#unpacking example
myUltimateSkills ={"HTML":{"Main":"80%","Pugjs":"80%"},
"CSS":{"Main":"90%","Sass":"70%"}}
for main_key,main_value in myUltimateSkills.items(): #.items it get all dict items in tuple like ("HTML",{"Main":"80%","Pugjs":"80%"})
    print(f"{main_key} Progress Is: ")
    for child_key,child_value in main_value.items():
        print(f"- {child_key} => {child_value}")
## unpacking dict operator 
    First={'x':1,}
    Second={'x':5,"y":4}
    my_dict =[**first, "z":3 , **second]
    print(my_dict)
    Output= {'x':5,"y":4,"z":3}


#group by
from collections import ChainMap, defaultdict
# Define your data here (list of tuples)
data = [('key1', 'value1'), ('key2', 'value2'), ('key1', 'value3'), ('key2', 'value4')]
# Create a defaultdict to map keys to multiple values
multi_dict = defaultdict(list)
# Populate multi_dict with data
for k, v in data:
    multi_dict[k].append(v)
# Print the resulting multi_dict
print("Multi Dictionary:", multi_dict)

merged_dict = dict(ChainMap(dict1, dict2))  # Merges dictionaries while preserving original dictionaries
# Dictionary Comprehensions
squared_dict = {x: x**2 for x in range(1, 6)}  # Creates a dictionary of squares from 1 to 5
inverted_dict = {v: k for k, v in my_dict.items()}  # Creates a new dictionary with keys as values and values as keys
merged_dict = {k: v for d in list_of_dicts for k, v in d.items()}  # Creates a dictionary by merging keys and values from a list of dictionaries
filtered_dict = {k: v for k, v in my_dict.items() if v != 'value_to_remove'}  # Removes key-value pairs with a specific value from the dictionary
```

## Defualt dictionary 

### **Key Differences**
1. **Default Value Handling**:
   - **Normal Dictionary**: Throws a `KeyError` if you try to access a key that does not exist.
   - **Default Dictionary**: Automatically initializes missing keys with a default value (provided by a factory function).

2. **Initialization**:
   - **Normal Dictionary**: Created using `{}` or the `dict()` constructor.
   - **Default Dictionary**: Created using `collections.defaultdict()` and requires a default value factory function (e.g., `int`, `list`).

---

### **When to Use Each**
1. **Normal Dictionary**:
   - Use when you need explicit control over keys and values and when accessing a missing key should signal an error.
   - Example:
     ```python
     data = {}
     data['a'] = 1
     print(data['b'])  # Raises KeyError
     ```

2. **Default Dictionary**:
   - Use when you want to avoid `KeyError` and require default values for non-existing keys, such as for counters or grouping.
   - Example:
     ```python
     from collections import defaultdict
     data = defaultdict(int)  # Default value is 0
     data['a'] += 1
     print(data['b'])  # Outputs 0, no KeyError
     ```
---

1. **Normal Dictionary Example**:
   ```python
   data = {}
   if 'key' not in data:
       data['key'] = 0  # Initialize manually
   data['key'] += 1
   print(data)  # {'key': 1}
   ```

2. **Default Dictionary Example**:
   ```python
   from collections import defaultdict
   data = defaultdict(int)  # Default value factory is int

   data['key'] += 1  # so this will not give me error like above 

   print(data)  # defaultdict(<class 'int'>, {'key': 1})
   ```

---


-----
## map, filter ,reduce , comperhensive list and dictonry , generator 
 
----
## files 
#r r+(can read and write)  w(when w it delete everything) w+() a()   a+()


```python 
files= open("test.txt","a+")         # if it doesn't exist it will create the file when you write or append
print(files.read())
print(files.write("omar"))
files.close()

With open('another_file.txt','r') as f:  #it will close the file after reading it
    File_data = f.read()

# So, essentially, the code reads all the PDF files from the specified directory, converts each file to HTML format, and saves the HTML output in a file with the same name as the PDF file but with an extension of ".html".
    
directory = "D:\\courses\\project_atom\\"
pdf_files = [f for f in os.listdir(directory) if f.endswith('.pdf')]
for pdf_file in pdf_files:
    text = convert_pdf(f"D:\\courses\\project_atom\\{pdf_file}","html","utf-8")
    with open(f'{pdf_file}.html',"w", encoding="utf-8") as f:
    f.write(text)

```
### jason
Json : it coud be all object into on list or one object contain list of object.   
1- To read a JSON file, you can use the json.load() function.This function reads a file-like object (which is the json [f]) and returns the data. If you have a JSON string, you can parse it to python object by using the json.loads() method >> **( it make parse Json string to python object(dictonary or list).)**
```python
    Import json
    with open('data.json') as f :
        data =json.load(f)
    
    def load_config():
        root_path = os.path.dirname(os.path.realpath(sys.argv[0]))
        file_path = os.path.join(root_path, 'config.json')
        input_file = open(file_path)
        json_data = json.load(input_file)
        return json_data

```

1. **`root_path = os.path.dirname(os.path.realpath(sys.argv[0]))`**

   - **`sys.argv[0]`**: 
     - `sys.argv` is a list in Python that contains command-line arguments passed to the script.
     - `sys.argv[0]` specifically refers to the path of the script being executed (essentially, where the current Python file is located).
   - **`os.path.realpath(sys.argv[0])`**:
     - `os.path.realpath()` resolves the absolute path of the file, converting any symbolic links (shortcuts) or relative paths to the full, absolute path.
     - For example, if `sys.argv[0]` is `"./script.py"`, then `os.path.realpath(sys.argv[0])` will return something like `"/home/user/project/script.py"`.
   - **`os.path.dirname()`**:
     - `os.path.dirname()` extracts the directory part of a given path, removing the file name.
     - Here, it removes `"script.py"` from the path, resulting in `"/home/user/project"`.
   - **Result**:
     - After these functions are combined, `root_path` will hold the directory path where the script is located. In this example, `root_path` will be `"/home/user/project"`.

   **Summary of Line 1**: This line calculates the directory path of the current Python script and assigns it to `root_path`.

2. **`file_path = os.path.join(root_path, 'config.json')`**

   - **`os.path.join(root_path, 'config.json')`**:
     - `os.path.join()` is a function that safely combines directory and file paths in a platform-independent way (Windows, Linux, macOS) by adding the appropriate separator (e.g., `/` or `\`).
     - Here, it joins `root_path` (the directory where the script is located) with `'config.json'`.
     - If `root_path` is `"/home/user/project"`, the result will be `"/home/user/project/config.json"`.
   - **Result**:
     - `file_path` now holds the full path to the `config.json` file in the same directory as the script, regardless of the operating system or specific location of the script.

   **Summary of Line 2**: This line constructs the full path to `config.json`, which is assumed to be in the same directory as the script, and assigns it to `file_path`.

#### Example Scenario
If the script is located in `"/home/user/project/"`, the two lines would work as follows:
- `root_path` will be `"/home/user/project"`.
- `file_path` will then be `"/home/user/project/config.json"`.
     
```python
   # json.dump >> Does not return anything; it writes the JSON output to the provided file-like object (which is f)
    data ={'name':'John','age':30,'city':'New York'}
    with open('users.json','w') as f:
        json.dump(data,f)

     #  json.dumps >> convert python object to Json string so,it Returns the JSON data as a string    
    data_json =json.dumps(data)
    with open('users.json','w') as f:
        f.write(data_json)
 ```

------
# crawling

## 1.using APIs

### python code example 
- Use requests.get (or other specialized methods like requests.post) when performing a specific HTTP method. It keeps the code clean and readable.
- `response = requests.get(source_url, headers=headers,timeout=20)`
- Use requests.request when the HTTP method is dynamic or when implementing more advanced use cases.
- `response = requests.request("GET", url, headers=headers, timeout=20)`
```python
import json
import requests

while True:
    part_number = input("please enter keyword you need : ")
    # when i find the need api that contains the data i need in the network
    # 1- right click on that api and then copy then Copy all as CURL (bash),  then go to postman click on import past this CURL , then you can choose GET Or any thing and you can use the api url from the postman
  
    url = f"https://www.noon.com/_next/data/bigalog-a192a309ade5161b21d4954e641eda20628175b1/egypt-en/search.json?q={part_number}&gclid=Cj0KCQjw4Oe4BhCcARIsADQ0csn46N9s8pBipkC31jb4PubCWSeIO3IzePJbQNPu6DEEUC2FrngxbO0aAlLlEALw_wcB&utm_campaign=C1000151432N_eg_en_web_performancemaxxmobilesxalwaysonx18082022_noon_web_c1000087l_remarketing_plassc_&utm_medium=cpc&utm_source=c1000087l&catalog=search"

    payload = {}

    #It helps simulate requests from a web browser, which can be crucial for accessing data on websites that restrict non-browser traffic to prevent scraping.
    #Including specific headers like user-agent and x-nextjs-data can also help ensure your requests are accepted by servers and reduce the risk of your script being blocked or your IP address being banned.
    headers = {
      'user-agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/130.0.0.0 Safari/537.36',
      'x-nextjs-data': '1'
    }

    try:
        response = requests.request("GET", url, headers=headers,timeout=20)
        #response = requests.request("GET", url, data=payload,timeout=20)
        #data=payload , It allows you to send data to the server, which can be necessary for operations like submitting form data, performing actions that modify server-side data, or querying a database via a web interface.
        #if you needed to send additional parameters via POST instead of in the URL, you would add them to payload

        #This line converts the JSON string into a Python dictionary so it can be easily worked with in the code.
        data = json.loads(response.text)
        
        products = data['pageProps']['catalog']['hits']
        skus = [product['sku'] for product in products]
        names = [product['name'] for product in products]
        urls = [product['url'] for product in products]
        brands = [product['brand'] for product in products]
        prices = [product['price'] for product in products]
        sales_prices = [product['sale_price'] for product in products]
        docs = [
            {
                'sku': sku,
                'name': name,
                'url': url,
                'brand': brand,
                'price': price,
                'sale_price': sale_price
            }
            for sku, name, url, brand, price, sale_price in zip(skus, names, urls, brands, prices, sales_prices)
        ]
        print(len(skus))

        #convert python object to Json string
        print(json.dumps(docs, indent=4))
    except Exception as e:
        print(e)
```

## 2.using XPATH

- **quote**   
    - The `quote` function from the `urllib.parse` module in Python is used to safely encode special characters in URLs.  
    - This function is crucial for web applications dealing with dynamic URLs that include user-generated content, helping to prevent URL manipulation and ensuring compatibility across different web servers and clients. 
    - The function is typically used to encode URL parameters to ensure they are valid URLs, especially when they might contain characters that are illegal in standard URL formats.
    ### Function Signature
    ```python
    urllib.parse.quote(string, safe='/', encoding=None, errors=None)
    ```

    ### Parameters
    - **string**: The text to be URL-encoded.
    - **safe**: Characters that should not be encoded. Default is `'/'`, which is common in URLs.
    - **encoding**: Character encoding to use. If none is specified, UTF-8 is used.
    - **errors**: Error handling strategy for characters that can't be converted with the specified encoding.

    ### Example
    ```python
    from urllib.parse import quote

    # A typical example where the user input might contain spaces or special characters
    user_input = "hello world & good day"
    safe_url_part = quote(user_input)

    print(safe_url_part)  # Output: hello%20world%20%26%20good%20day
    ######################################################################################

    url_part = "hello world"
    encoded_part = quote(url_part)
    print(encoded_part)  # Output: hello%20world

    # If you were to pass safe=' ' to quote, the space would not be encoded:
    encoded_part = quote(url_part, safe=' ')
    print(encoded_part)  # Output: hello world


    ```
    In this example:
    - The space characters and the ampersand (`&`) are encoded to `%20` and `%26` respectively.
    - The output ensures the string can be safely used as part of a URL.



```py

import requests
from bs4 import BeautifulSoup
from lxml import etree
from urllib.parse import quote

# Setup
# Define the part number to search for
url_part = "R-78E5.0-0.5"
# Create the full URL for the request, ensuring special characters in the part number are properly encoded
source_url = 'https://www.findchips.com/search/' + quote(url_part, safe='') + '?currency=USD'
# Set up HTTP headers if necessary (e.g., User-Agent, Authentication)
headers = {
    # Specify necessary headers here, like 'User-Agent': 'MyApp/1.0'
}



# Making a request
# Perform an HTTP GET request with the specified URL and headers
response = requests.get(source_url, headers=headers)
# Check if the HTTP request was successful
if response.status_code == 200:
    # Get the text content of the response
    html_content = response.text
    # Parse the HTML content with BeautifulSoup
    soup = BeautifulSoup(html_content, "html.parser")
    # Convert the BeautifulSoup object to a string and parse it with lxml(convert HTML to XML) for XPath querying
    dom = etree.HTML(str(soup))



    # Extracting data
    # Use XPath to find all div elements with class 'distributor-results'
    sellers = dom.xpath("//div[@class='distributor-results']")
    # Loop through each seller div and print the 'data-distributor_name' attribute
    for seller in sellers:
        print(seller.attrib['data-distributor_name'])
else:
    # If the status code is not 200, print an error message including the status code
    print(f"Failed to retrieve data, status code: {response.status_code}")

```

-----------------

# Python MULTITHREADING 
- **multithreading**: Used to perform multiple tasks concurrently (multitasking)
- Good for I/O bound tasks like reading files or fetching data from APIs
- threading.Thread(target=my_function)

```py
    # without threading (it will executed one by one it run in one thread in the main file ) 

    def walk_dog(first, last):
    time.sleep(8)
    print(f"You finish walking {first} {last}")

    def take_out_trash():
    time.sleep(2)
    print("You take out the trash")

    def get_mail():
    time.sleep(4)
    print("You get the mail")

    walk_dog("Scooby", "Doo")
    take_out_trash()
    get_mail()
    # output 
    '''You finish walking Scooby Doo 
       You take out the trash
        You get the mail  '''


    #using threading (to make the functions run at the same time divide it into threading to run in parallel  )

    import threading
    import time

    def walk_dog(first, last):
    time.sleep(8)
    print(f"You finish walking {first} {last}")

    def take_out_trash():
    time.sleep(2)
    print("You take out the trash")

    def get_mail():
    time.sleep(4)
    print("You get the mail")

    chore1 = threading.Thread(target=walk_dog, args=("Scooby", "Doo"))
    chore1.start()

    chore2 = threading.Thread(target=take_out_trash)
    chore2.start()

    chore3 = threading.Thread(target=get_mail)
    chore3.start()

    ## .join() ensures that all tasks are completed before proceeding
    chore1.join()
    chore2.join()
    chore3.join()

    print("All chores are complete!")

        # output 
    '''You take out the trash
       You get the mail
       You finish walking Scooby Doo 
       All chores are complete!
          '''

```
#### yield Function
- Unlike regular functions that return all values at once (storing them in memory), yield produces **one result at a time**, consuming less memory.
- the function’s execution state (including local variables and the execution point) is saved. The next time the generator is called, it resumes right where it left off.
- Functions with yield only execute and produce the next item when you ask for it, which is why they are called "lazy evaluation."
```Python
    def count_up_to(max):
        count = 1
        while count <= max:
            yield count  # It stop here to return one value if it called again it resumes right where it left off here.
            count += 1
    
    counter = count_up_to(3)  # the counter vairable is generator object 
    print(next(counter))  # Output: 1
    print(next(counter))  # Output: 2
    print(next(counter))  # Output: 3
    print(next(counter))  # This will raise a StopIteration exception because the generator is exhausted.
 
    

    # or you want to create a generator that yields squared values of numbers in a list:
    def squares(numbers):
    for number in numbers:
        yield number ** 2

    # Using the generator
    for square in squares([1, 2, 3, 4]):
        print(square)
    ''' output
        1
        4
        9
        16
    '''


    # yield can also be used to create more complex data flows, such as handling nested loops or conditionals:
    def flatten(nested_list):
    for sublist in nested_list:
        if isinstance(sublist, list):
            for item in sublist:
                yield item
        else:
            yield sublist

    nested = [1, [2, 3], 4, [5, [6, 7]]]
    for num in flatten(nested):
        print(num)

    ''' output
        1
        2
        3
        4
        5
        [6, 7]

    '''


```
### Real_Example
```py
     # you can add script parameter to the python script that will not run until you give this parameter to this python script 
     # sys.argv >>>> This is a list in Python that contains the command-line arguments passed to the script.
     # sys.argv[0] >>>> always the script's filename path
     # sys.argv[1] >>>> the first argument passed to the script.
     #  if the input was  "10,20,30" >> [10, 20, 30]

    loads = [int(load) for load in sys.argv[1].split(',')]  # this list will contains the argument as integer seperated with ,  
    query = {'task_name': 'FDH_Electronic', 'args': loads}
    documents = server_tasks_coll.find(query)
    task_doc = next(documents)

    def divide_batches(all_input):
    try:
        n = int(math.ceil(len(all_input) / number_of_threads))
        for i in range(0, len(all_input), n):
            yield all_input[i:i + n]
    except Exception as Batches_err:
        print("Error during dividing Input to Batches input : {}".format(Batches_err))

        while True:
        try:
            RSPartial = list(input_coll.find(mongo_filter).limit(mongo_limit))

            if len(RSPartial) >= 0:
                server_tasks_coll.update_one({'_id': task_doc['_id']},
                                             {'$set': {"IsRunning": True, "issue": None,
                                                       "last_run_date": datetime.datetime.now().strftime(
                                                           "%d/%m/%Y %H:%M:%S")}})
                # result = chunk_list(RSPartial, 1)

                batches = divide_batches(RSPartial)
                all_threads = []
                for batch in batches:
                    thread = threading.Thread(target=Engine, args=(batch, input_coll, output_coll,))
                    all_threads.append(thread)

                for thread in all_threads:
                    thread.start()

                ## .join() ensures that all tasks are completed before proceeding
                for j in all_threads:
                    j.join()

            else:
                print("No Pending Data")

                server_tasks_coll.update_one({'_id': task_doc['_id']},
                                             {'$set': {"IsRunning": False, "issue": "No Pending Data"}})

                time.sleep(60)
                continue
        except Exception as ex:
            print(ex)
            server_tasks_coll.update_one({'_id': task_doc['_id']},
                                         {'$set': {"IsRunning": False, "issue": str(ex)}})
            pass
```