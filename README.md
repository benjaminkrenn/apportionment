# A Python implementation of common apportionment methods

This is a collection of common apportionment methods. Apportionment has two main applications: 
to assign a fixed number of parliamentary seats to parties (proportionally to their vote count), and to assign
representatives in a senate to states (proportionally to their population count).

The following methods are implemented:
* the largest remainder method (or Hamilton method)
* the class of divisor methods including
   - D'Hondt (or Jefferson)
   - Sainte-Laguë (or Webster)
   - Huntington-Hill
   - Adams
* the Quota method [1]


## How-to

The following example calculates the seat distribution of Austrian representatives in the 
European Parliament based on the D'Hondt method and the [2019 election results](https://www.bmi.gv.at/412/Europawahlen/Europawahl_2019). Parties that received less than 4% are excluded from obtaining seats and are thus excluded in the calculation.

```python
import apportionment
parties = ['ÖVP', 'SPÖ', 'FPÖ', 'GRÜNE', 'NEOS']
distribution = [1305956, 903151, 650114, 532193, 319024]
seats = 18
apportionment.method("dhondt", distribution, seats, parties, verbose=True)
```

Another example can be found in [example.py](example.py).

## References

[1] Balinski, M. L., & Young, H. P. (1975). The quota method of apportionment. The American Mathematical Monthly, 82(7), 701-730.
