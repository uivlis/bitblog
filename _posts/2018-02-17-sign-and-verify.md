---
layout: default
title:  "Sign & Verify"
date:   2018-02-17
---

BITBOX enables you to cryptographically prove ownership of an address via signing messages. You can also verify that ownership of an address from another person.

If, for example, you lost access to an account you could prove you were the owner that had been sending payments to that account by signing a specific message from that address.

Or someone could potentially give you a loan or credit using a signature from a wallet holding a certain amount of funds as proof that you could repay them.

## Sign a message

You can sign a message w/ any address in your BITBOX. It doesn't matter if it's in cashaddr or legacy encoding. Just paste the address into the address field and type the message that you want to sign. Then click the 'Sign' button and if you have entered a valid address that has keys in your BITBOX you'll see a signature appear.

![Converter]({{ "/assets/verify-cashaddr.png" | absolute_url }})

You can share this message, address and signature w/ anyone and they can verify that you are the owner of that address.

## Verify a message

You can verify a message from any address on the Bitcoin Cash network. Just paste in the message, address and signature provided and click the 'Verify' button. If the address and signature are both valid format and the signature matches the message and the address you'll get a green 'Valid message' response.

![Converter]({{ "/assets/verify-legacy.png" | absolute_url }})

If the address or signature are incorrectly formatted or the signature doesn't match the message and address you'll get an error message.

![Converter]({{ "/assets/verify-fail.png" | absolute_url }})

## Using the command line

BITBOX supports the entire Bitcoin Cash RPC. [`bitbox-cli`](https://www.npmjs.com/package/bitbox-cli) now supports, `signmessagewithprivkey` and `verifymessage` in cashaddr (w/ or w/out the prefix) and legacy.

### Sign

```
BITBOX.BitcoinCash.signMessageWithPrivKey('KxtpRDUJDiutLaTV8Vuavhb6h7zq9YV9ZKA3dU79PCgYmNVmkkvS', "EARTH");
 // IIYVhlo2Z6TWFjYX1+YM+7vQKz0m+zYdSe4eYpFLuAQDEZXqll7lZC8Au22VI2LLP5x+IerZckVk3QQPsA3e8/8=
```

### Verify

```
BITBOX.BitcoinCash.verifyMessage('bitcoincash:qp2zvw3zpk5xx43w4tve7mtekd9kaxwj4uenq9eupv', 'IIYVhlo2Z6TWFjYX1+YM+7vQKz0m+zYdSe4eYpFLuAQDEZXqll7lZC8Au22VI2LLP5x+IerZckVk3QQPsA3e8/8=', 'EARTH')
true
```
