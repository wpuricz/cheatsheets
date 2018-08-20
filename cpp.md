---
title: C++
category: Programming Language
---

### Command Line 
```
cin >> name 
cout << "Greeting " << "hello " << name;
endl;  # End line
getline(cin,str); # Store input entered by user in str
```

### Strings C Style
```
char name[] = "Will"; # Declare a string
strcpy(s1,s2)  # Copy a string
strcat(s1, s2) # Concatenates s2 onto s1
strlen(s1)  # Get the length of a string
strcmp(s1, s2) # Compare string 1 and 2. 0 if same, -1 if s1<s2, 1 if s1>s2
strchr(s1, ch) # Returns a pointer to the first occurance of char ch in string s1
strstr(s1, s2) # Returns a pointer to the first occurance of string s2 in string s1
```

### String Class C++
```
string str1 = "Hello"; # Declare String
string str3 = str1; # Copy String
string str3 = str1 + str2; # Concatenate String
int len = str1.size(); # Length
str = str[3]; # Get character
str.push_back('s'); # Append character
str.pop_back(); # Remove last character
str.front() # Get first character
str.back() # Get last character
str.clear(); # Deletes all char from string
str.substr(7,3); # Substring
str.find('ab'); # Index of character(s)
str.erase(2,3); # Remove char from a string
str.replace(2.7,"ese are test"); # Replace substring with string
str.replace(str.find(str2),str2.length(),str3); # replace first occurance
```

### Iterators
```
string::iterator::it; # Iterator
string::reverse_iterator it1; # Reverse iterator
it = str.begin() # Return iterator to beginning of string
it = str.end() # Return iterator to end of string
it = str.rbegin() # returns a reverse iterator pointing at the end of string
it = str.rend() # returns a reverse iterator pointing at beginning of string
```

### Vector
```
vector<string> v1; # Declare
v1.size() # length of vector
v1.empty() # check if empty
v1.push_back("str") # Add to vector
v1.pop_back() # Remove last element
v1.insert(v1.begin()+2,"new element"); # inserts an element at the 2 position
v1.emplace(v1.begin()+2,"new element"); # inserts an element at the 2 position (same as insert)
```

```
for (auto it = v1.begin(); it != v1.end(); ++it) {
    cout << *it << " ";
}
```

### Files
```

```
