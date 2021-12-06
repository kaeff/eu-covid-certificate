# eu-covid-certificate
Decode your EU COVID green pass barcode

Source: [How to Decode Your Own EU Vaccination Green Pass With a Few Lines of Python](https://hackernoon.com/how-to-decode-your-own-eu-vaccination-green-pass-with-a-few-lines-of-python-9v2c37s1) (minus the blockchain talk...)

## Initial setup

Requires: python3

```
$ git clone https://github.com/kaeff/eu-covid-certificate.git
$ cd eu-covid-certificate
$ pip install -r requirements.txt
```

## How to use

1) Scan your EU COVID green pass barcode. It should be a base45-encoded string that starts with `HC1:` and is about 470 characters long.
2) Run `decode.py` using your barcode content as the first argument:

```
$ python3 decode.py "HC1:....."
```

As a result, you should see an output similar to this example:
```
{
  "1": "DE", // issuing country
  "4": 1655209933, // expires at
  "6": 1623673933, // issued at
  "-260": { 
    "1": {
      "v": [
        {
          "ci": "URN:UVCI:01DE/IZ12345A/21E0JXD7UQY6ECLM3WT7YF#8",
          "co": "DE",
          "dn": 2,
          "dt": "2021-04-01",
          "is": "Robert Koch-Institut",
          "ma": "ORG-100031184",
          "mp": "EU/1/20/1507",
          "sd": 2,
          "tg": "840539006",
          "vp": "1119349007"
        }
      ],
      "dob": "1964-08-12",
      "nam": {
        "fn": "Mustermann",
        "gn": "Erika",
        "fnt": "MUSTERMANN",
        "gnt": "ERIKA"
      },
      "ver": "1.0.0"
    }
  }
}
```
