# fuzzPattern
Creates fuzz pattern for fuzzing purpose. Use `fuzzPatternCreate` to create pattern and `fuzzPatternSearch` to find the string/hex found.

The item found is assumed to be 4 bytes (32 bit) or above.

Coded in Golang.

## Getting Started

The executables are statically built (thanks to Golang) on a 64 bit Linux machine. If there's a need to rebuild from source, you may use the sources included as well.

Dependencies:
> gopkg.in/alecthomas/kingpin.v2

## Deployment

Recommended to deploy as part of easyscripts deployment (https://github.com/telboon/easyscripts)

## Comparison Between patern_create & fuzzPatternCreate 

### Speed

fuzzPatternCreate -- 0.196s for 100,000 characters
```
$ time fuzzPatternCreate 100000
[TRUNCATED]
6Dud7Dud8Dud9

real	0m0.196s
user	0m0.016s
sys	0m0.005s
```

pattern_create -- 2.398s for 100,000 characters
```
$ time /usr/share/metasploit-framework/tools/exploit/pattern_create.rb -l 100000
[TRUNCATED]
e8Ye9Yf0Yf1Yf2Y

real	0m2.398s
user	0m1.914s
sys	0m0.350s
```


### Entropy

fuzzPatternSearch -- Repeats every 703,040 bytes
```
$ fuzzPatternSearch -l 1500000 Aaa1
Full cycle: 175760 * 4 = 703040

Pattern found: 4
Pattern found: 703044
Pattern found: 1406084
```

pattern_offset -- Repeats every 20,280 bytes
```
$ /usr/share/metasploit-framework/tools/exploit/pattern_offset.rb -l 50000 -q Aa1A
[*] Exact match at offset 3
[*] Exact match at offset 20283
[*] Exact match at offset 40563
```

## Authors

* **Samuel Pua** - *Initial work* - (https://github.com/telboon)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

