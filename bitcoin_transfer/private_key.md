## Private key {#private-key}

Private keys are often represented in Base58Check called a **Stratis Secret** (also known as **Wallet Import Format** or simply **WIF**), like Stratis Addresses.  

![](../assets/StratisSecret.png)  

```cs  
Key privateKey = new Key(); // generate a random private key
StratisSecret mainNetPrivateKey = privateKey.GetStratisSecret(Network.Main);  // get our private key for the mainnet
StratisSecret testNetPrivateKey = privateKey.GetStratisSecret(Network.TestNet);  // get our private key for the testnet
Console.WriteLine(mainNetPrivateKey); // L5B67zvrndS5c71EjkrTJZ99UaoVbMUAK58GKdQUfYCpAa6jypvn
Console.WriteLine(testNetPrivateKey); // cVY5auviDh8LmYUW8AfafseD6p6uFoZrP7GjS3rzAerpRKE9Wmuz

bool WifIsStratisSecret = mainNetPrivateKey == privateKey.GetWif(Network.Main);
Console.WriteLine(WifIsBitcoinSecret); // True
```  

Note that it is easy to go from **StratisSecret** to private **Key**. On the other hand, it is impossible to go from a Stratis Address to Public Key because the Stratis Address contains a hash of the Public Key, not the Public Key itself.  
Process this information by examining the similarities between these two codeblocks:  

```cs
Key privateKey = new Key(); // generate a random private key
StratisSecret StratisSecret = privateKey.GetWif(Network.Main); // L5B67zvrndS5c71EjkrTJZ99UaoVbMUAK58GKdQUfYCpAa6jypvn
Key samePrivateKey = StratisSecret.PrivateKey;
Console.WriteLine(samePrivateKey == privateKey); // True
```  

```cs
PubKey publicKey = privateKey.PubKey;
StratisPubKeyAddress StratisPubicKey = publicKey.GetAddress(Network.Main); // 1PUYsjwfNmX64wS368ZR5FMouTtUmvtmTY
//PubKey samePublicKey = StratisPubicKey.ItIsNotPossible;
```  

### Exercise:
1. Generate a private key on the mainnet and note it.
2. Get the corresponding address.
3. Send Stratis to it. As much as you cannot afford to lose, so it will keep you focused and motivated to get them back during the following lessons. 


 





