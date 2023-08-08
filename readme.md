
## DuitNow QR Code Generator Test

i found there's an interesting use case of DuitNow from [@kidino](https://www.github.com/kidino), where you would scan a DuitNow QR code on an electric massage chair, then the chair would work after you successfully paid.

so i tried to find a way to generate your own DuitNow QR, without going through the banking app, but it seems to be that some organisation (looking at you [@paynet-my](https://www.github.com/paynet-my)) is trying to gatekeep this info.

in case of PayNow, generating a PayNow QR code is quite straight forward when you already have your own PayNow ID. but generating a DuitNow QR is a pain in the ass with seems to be unnecessary complexity.

below is the source code of DuitNow QR generator after reverse engineering a lot of DuitNow QRs. but i still can't manage to get how we could get the `account` and `app` value, or simply implement it with our own DuitNow ID like PayNow do.

### Source

[https://gist.github.com/natsu90/f45dc88b38a037325ad9095163b82b42](https://gist.github.com/natsu90/f45dc88b38a037325ad9095163b82b42)


### Usage

```
npm install gist:f45dc88b38a037325ad9095163b82b42
```

```
const { generateDuitNowStr } = require('duitnow-js')

const qrString = generateDuitNowStr({
    account: '0000000000000000000000072339', // UNKNOWN Account ID
    app: '890087', // UNKNOWN ID
    category: '7399', // Merchant Category Code
    name: 'GINTELL REST N GO SDN BHD',
    city: 'KEPONG MENJALARA',
    postcode: '52200',
    ref5: '0.1626.0', // Reference Label
    ref6: '16881451', // Customer Label 
    ref8: 'Start machine via DuitNow', // Purpose of Transaction
    ref82: '7FFC1AC00E99EA2D7A0D7BB79755736A' // unknown Ref Number

})

```

### Tests

```
npm install

npm run test
```

### Output

![Test Output](/images/output.png "Test Output")

### Merchant Category Code

[https://global.alipay.com/docs/ac/ref/mcccodes](https://global.alipay.com/docs/ac/ref/mcccodes)

### Credit

[https://gist.github.com/chengkiang/7e1c4899768245570cc49c7d23bc394c](https://gist.github.com/chengkiang/7e1c4899768245570cc49c7d23bc394c)

### License

Licensed under the [MIT license](http://opensource.org/licenses/MIT)