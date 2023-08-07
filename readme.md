
## DuitNow QR Code Generator Test


### Source

[https://gist.github.com/natsu90/f45dc88b38a037325ad9095163b82b42](https://gist.github.com/natsu90/f45dc88b38a037325ad9095163b82b42)


### Usage

```
npm install gist:f45dc88b38a037325ad9095163b82b42
```

```
const { generateDuitNowStr } = require('duitnow-js')

const qrString = generateDuitNowStr({
    account: '0000000000000000000000072339',
    app: '890087', // unknown ID
    category: '7399', // unknown Merchant Category Code
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

![Test Output](/output.png "Test Output")

### Credit

[https://gist.github.com/chengkiang/7e1c4899768245570cc49c7d23bc394c](https://gist.github.com/chengkiang/7e1c4899768245570cc49c7d23bc394c)

### License

Licensed under the [MIT license](http://opensource.org/licenses/MIT)