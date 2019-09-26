# alaya-care

Welcome to my coding challenge for AlayaCare.
This was built with vue.js and the only library I used is vuelidate to validate the form inputs.

## Project setup
```
npm install
```

### Run using the following command
```
npm run serve
```

## Test Cases

I didn't really know what you wanted me to use for test cases so I just manually entered the following test cases

### Test 01: Correct Information

Credit Card Number: 4242424242424242
Name: Jake Santiago
Expiry: 02/23
CVV: 123

### Test 02: Short Length CC

Credit Card Number: 42424242424242
Name: Jake Santiago
Expiry: 02/23
CVV: 123

### Test 03: Missing Info (Iterated for each field)

Credit Card Number:
Name: Jake Santiago
Expiry: 02/23
CVV: 123

### Test 04: Expiry wrong format

Credit Card Number: 4242424242424242
Name: Jake Santiago
Expiry: 02/2013
CVV: 123

### Test 05: Expiry month greater than 12

Credit Card Number: 4242424242424242
Name: Jake Santiago
Expiry: 13/22
CVV: 123

### Test 06: Expiry year lesser than 19

Credit Card Number: 4242424242424242
Name: Jake Santiago
Expiry: 02/17
CVV: 123

### Test 07: CVV greater than 3 characters

Credit Card Number: 4242424242424242
Name: Jake Santiago
Expiry: 02/17
CVV: 1234

### Test 08: CVV shorter than 3 characters

Credit Card Number: 4242424242424242
Name: Jake Santiago
Expiry: 02/17
CVV: 12