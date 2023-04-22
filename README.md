# useDebounce
Custom hook


```javascript
import { useState, useEffect } from 'react';


const useDebounce = (value, delay) => {
  const [debouncedValue, setDebouncedValue] = useState(value);

  useEffect(() => {
    const timer = setTimeout(() => {
      setDebouncedValue(value);
    }, delay);

    return () => {
      clearTimeout(timer);
    };
  }, [value, delay]);

  return debouncedValue;
}

export default useDebounce;
```

## Now you can use this custom hook useDebounce in any React component that needs a delay on a specific value. 
## For example, you could use it to delay the search of a term in a search bar until the user has stopped typing for a short period of time.
```javascript
import React, { useState } from 'react';
import useDebounce from './useDebounce';

const SearchBar = () => {
  const [searchTerm, setSearchTerm] = useState('');
  const debouncedSearchTerm = useDebounce(searchTerm, 500);

  // call API using debouncedSearchTerm
  // ...
}

```
