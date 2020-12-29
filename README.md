# Private Key Converter
This tool converts WIF (Wallet Import Format) keys to have a version (sometimes called prefix) of 128 (0x80)

## How do I use it?
Open the index.html folder and input your private key. If it is a valid private key, it will return with uncompressed and compressed versions of your private key with a version (prefix) of 128. The uncompressed version will start with 5 and uncompressed will start with K or L.

You can read more about prefixes here:  
https://en.bitcoin.it/wiki/List_of_address_prefixes

## Why was this created?
Some users have had trouble sweeping old address wallets where the version used had changed over time. I have seen this happen quite a few times for some Vertcoin users. This is intended to be a lightweight way of easily converting to the newer format, which can be swept into wallets.

It is only 173 lines (totalling HTML, JS, CSS).

## Is it safe to use?
I'd like to think so, but can't guarantee it in every situation. It can be ran offline in a black box (machine with no connection to the internet). It does not depend on any packages or any external source / calls so all of the code you see is local to either the HTML document or included with your browser. The cryptographic functions used are done via the SubtleCryptp digest API from your browser (read more: https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/digest). To allow for larger integers in conversion, BigInt is also used (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt).

## It doesn't work for me
A lot of the functionality (BigInt, SubtleCrypto) of the code used depends on your browser being up to date. I have tested it on Chrome and Edge v86, Firefox v81. I am not sure how it works in Safari or other browsers. I also haven't tested it on a 32 bit operating system so I do not know how well that is supported.

If you find other errors and have the technical knowhow, you may want to look into the source code and see if you can fix it! I have tried to make it quite readable but it can always be improved!