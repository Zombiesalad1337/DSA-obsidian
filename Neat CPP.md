***
1. `std::string` [supports comparison between two strings by relational operators](https://stackoverflow.com/questions/14297185/comparing-strings-lexicographically) `(<, >, <=, >=, ==)`
2. Use operator overloading to seamlessly integrate with STL.
3. `insert` can insert ranges:
`ancestorsSet[child].insert(ancestorsSet[node].begin(), ancestorsSet[node].end());`
4. Assign range to a vector, replacing previous elements:
`allAncestors[i].assign(ancestorsSet[i].begin(), ancestorsSet[i].end());`