# HOMEWORK: LINKED LISTS

Aru Poleo Vargas

## Dependencies

Gtest
CMake

## How to compile:

I provide a CMakeLists.txt file which will generate a make file for your
system when, from the build directory, the following is run:

	cmake ..

After, run make from the build directory and a testing binary should be generated
in build/bin

## Notes

I added a toString method to the Node class so that it could handle the
specific weird case that is the templated type being an std::string

Regarding toString, there is still weirdness around floats and bools. bools
i will fix relatively easily, as the issue is simply that the default to_string
method that c++ has outputs 1 or 0, not true or false, which could make it confusing
for the user what the type being stored is. I will create a specialization for it.
Regarding floats, though, it is considerably more annoying. C++ does not actually
save how many significant figures a float has, so it will output a bunch even if
you didnt enter that many. Not super sure what to do there tbh...

Missing some tests to be completely through. I have only tested nodes that contain
ints in the linked list. Should absolutely be testing different types.

I fear it will break when it comes to user defined types, as i am relying on 
the std::to_string method for string representation, which does not have implementations for
non-std, non-primitive types.
