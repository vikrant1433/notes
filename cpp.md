# raw string
* raw string in cpp starts with `R"(` and end with `")`
* R"foo(Hello World)foo"   // the string "Hello World"
# regex
```cpp 
template <class ST, class SA, char charT, class traits>
  bool regex_match (const basic_string<charT,ST,SA>& s,
          const basic_regex<charT,traits>& rgx,
          regex_constants::match_flag_type flags = regex_constants::match_default);
```
# regex_search
* regex_search function takes a string and regex object `regex_search(str, regex object)`
and return true if regex expression (object) matched else false
# regex_search with match_results
* smatch is typedef of std::match_results<string>
# how to get matched regex
regex_search(string, match_results object, regex_expr)
# example
```cpp
    string str="<email>xyz@gmail.com<endemail>";
    smatch  m; // typedef std::match_results<string>
    regex e("([[:w:]]+)@([[:w:]]+)\.com");
    bool found = regex_search(str, m, e);

    m.size(); // 3
    m[0];// xyz@gmail.com
    m[1];// xyz <- this is the first group
    m[2];// gmail <- this is the second group
    m.prefix().str(); // <email>
    m.suffix().str(); // <endemail>

```

## to use the regex_constants namespace
* regex_constants::icase
# to convert string to int (only in c++11 compile with -std=c)
* stoi("123") -> return integer 123
* stoi("01") -> return integer 1

