# enhanced-email-deep-validator

A very small modification from the original [email-deep-validator](https://www.npmjs.com/package/email-deep-validator) that verifies an email address checking MX records and SMTP connection, returning the MX records whenever it exits.

## Installation

Install the module through NPM:

    $ npm install enhanced-email-deep-validator --save

**Requires Node 6 or above**

## Examples

Include the module, create a new `EmailValidator` object and call `verify` method:

```javascript
const EmailValidator = require('enhanced-email-deep-validator');

const emailValidator = new EmailValidator();
emailValidator.verify('foo@email.com')
  .then(mxRecords => console.log('Email is valid.', mxRecords);

emailValidator.verify('non-existent@email.com')
  .catch(err => console.log('Email is not valid', err.message, err.mxRecords));
```

## Configuration options

### timeout

Set a timeout in seconds for the smtp connection. Default: `10000`.

### verifyMxRecords

Enable or disable the check of mx records. Default: `true`.

### verifySmtpConnection

Enable or disable the SMTP check. Default `true`.

## Testing

    $ npm test

## Contributing

This module was originally written to be used with Conversio and is used in a production environment currently. This will ensure that this module is well maintained, bug free and as up to date as possible.

Conversio's developers will continue to make updates as often as required to have a consistently bug free platform, but we are happy to review any feature requests or issues and are accepting constructive pull requests.
