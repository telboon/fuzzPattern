# fuzzPattern
Creates fuzz pattern for fuzzing purpose. Use fuzzPatternCreate to create pattern and fuzzPatternSearch to find the string/hex found.

The item found is assumed to be 4 bytes (32 bit) or above.

Coded in Golang.

## Getting Started

The executables are statically built (thanks to Golang) on a 64 bit Linux machine. If there's a need to rebuild from source, you may use the sources included as well.

Dependencies:
> gopkg.in/alecthomas/kingpin.v2

## Deployment

Recommended to deploy as part of easyscripts deployment (https://github.com/telboon/easyscripts)

## Authors

* **Samuel Pua** - *Initial work* - (https://github.com/telboon)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

