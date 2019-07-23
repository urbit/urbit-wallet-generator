# wallet-generator

A client-side app for generating Urbit HD wallets.

## Usage
You can download the `wallet-generator.html` file from the [releases page](www.github.com/urbit/urbit-wallet-generator/releases). You can run the Wallet Generator by just opening the downloaded `wallet-generator.html` file.

### Generate urbit-ships.txt
You can generate your own `urbit-ships.txt` file by following the below instructions: 
1. Get the @ud of the ship(s) you're trying to generate wallets for. You can get this by running `` `@ud`~ship-name`` in your dojo.
2. Modify this template JSON with the appropriate ship @ud's.:

```
{
  # this field was used only for record-keeping while Registration was live
  "idCode":"", 
  # replace this array with an array of planet @ud's (the numeric encoding of the ship being deeded)
  "planets":[2938474], 
  "stars":[1024],
  "galaxies":[0]
}
```
3. Encode the above JSON in base64. You can use an online tool like [Base64Encode](https://www.base64encode.org/).
4. Save the base64-encoded JSON as `urbit-ships.txt`

### Parse urbit-registration.txt
Trying to deed ships by manually reading the `urbit-registration.txt` file is error-prone, so please make sure you know what you are doing! 

You can parse the `urbit-registration.txt` file by following the below instructions:
1. Decode the contents of the `urbit-registration.txt` file in base64. You can use an online tool like [Base64Decode](https://www.base64decode.org/).
2. You'll get a JSON following the below format:

```
{
  "ship1": [
    "ownership_address", 
    "transfer_proxy", 
    "spawn_proxy", 
    "management_proxy", 
    "voting_proxy", 
    "auth_key", 
    "encryption_key"
  ],
  "ship2": [
    same format as above
  ],
  # this field was used only for record-keeping while Registration was live
  "idCode":""
}
```
3. You will want to send and deed the ships according to the given addresses.

## Development
### Install

```
$ npm install
```

### Build

You can use `npm run-script build` to execute the gulpfile. `npm run-script
release` will prepare a release and corresponding checksum in `./dist`.

## Supported Browsers

### Mac

- Chrome
- Firefox

### Windows

- Firefox

### Ubuntu

- Firefox
