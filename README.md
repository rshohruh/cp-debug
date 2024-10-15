# debug.hpp

A C++ header file for convenient debugging.

## Installation

1. Clone this repository or download the `debug.hpp` file.
2. Include the header in your C++ project:

```cpp
#include "debug.hpp"
```
## Usage
```cpp
int x = 42;
std::string name = "John Doe";
std::vector<int> numbers = {1, 2, 3};

debug(x, name, numbers);
```
This will output:

```
[x, name, numbers] = [42, "John Doe", {1, 2, 3}]
```

## Features
- Generic printing: Handles various data types.
- Variadic templates: Prints multiple arguments.
- Readable output: Includes variable names and values.
- Customization: Define custom printing functions and conditional debugging.

## Examples

### Basic Usage
```cpp
#include "debug.hpp"

int main() {
    int x = 42;
    double y = 3.14;
    std::string message = "Hello, world!";

    debug(x, y, message);

    return 0;
}
```
output
```
[x, y, message] = [42, 3.14, "Hello, world!"]
```

### Printing Containers
```cpp
#include "debug.hpp"

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    std::set<std::string> fruits = {"apple", "banana", "orange"};
    std::map<std::string, int> ages = {{"Alice", 30}, {"Bob", 25}, {"Charlie", 35}};

    debug(numbers, fruits, ages);

    return 0;
}
```
output
```
[numbers, fruits, ages] = [{1, 2, 3, 4, 5}, {"apple", "banana", "orange"}, {{"Alice", 30}, {"Bob", 25}, {"Charlie", 35}}]
```

### Custom Printing Functions
```cpp
#include "debug.hpp"

// Custom printing function for a Person object
struct Person {
    std::string name;
    int age;
};

inline void print(const Person& person) {
    std::cerr << "{name: " << person.name << ", age: " << person.age << "}";
}

int main() {
    Person p = {"Alice", 30};
    debug(p);

    return 0;
}
```
output
```
[p] = [{name: Alice, age: 30}]
```

## Contributing

- Feel free to submit pull requests or issues.

## License

This repository is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more information.