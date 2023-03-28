---
description: Verifying your deployed contract is always a good idea!
---

# Contract Verification

Once verified, a smart contract or token contract's source code becomes publicly available and verifiable. This creates transparency and trust. Plus, it's easy to do! Verification is available for both Solidity and Vyper contracts.&#x20;

There are multiple methods for verification using the BESCSCAN UI - all are cataloged below.&#x20;

[verify flatten source code](https://docs.blockscout.com/for-users/verifying-a-smart-contract#via-flattened-source-code)

[verify standard json file ](https://docs.blockscout.com/for-users/verifying-a-smart-contract#via-standard-json-input)

## Smart Contract Verification with Blockscout

1\) On contract creation, you will receive an address to check a pending transaction. If it does not redirect you to https://bescscan.io , go to bescscan, verify you are on the chain where the contract was deployed, and type the contract's address into the search bar. Your contract details should come up.

2\) Select the `Code` tab to view the bytecode, click the **Verify & Publish** button. You will see several options for verification.

## Via Flattened Source Code

* **Contract Address:** The `0x` address supplied on contract creation.&#x20;
* **Contract Name:** Name of the class whose constructor was called in the .sol file. For example, in `contract MyContract {..` **MyContract** is the contract name.&#x20;
* **Include Nightly Builds**: Yes if you want to show nightly builds.
* **Compiler:** derived from the first line in the contract `pragma solidity X.X.X`. Use the corresponding compiler version rather than the nightly build.
* **EVM Version:** [See EVM version information](broken-reference)
* **Optimization:** If you enabled optimization during compilation, check yes.
* **Optimization Runs:** 200 is the Solidity Compiler default value. Only change if you changed this value while compiling.
* &#x20;**Enter the Solidity Contract Code:** You may need to flatten your solidity code if it utilizes a library or inherits dependencies from another contract. We recommend the [POA solidity flattener](https://github.com/poanetwork/solidity-flattener) or the [truffle flattener](https://www.npmjs.com/package/truffle-flattener).
* **Try to fetch constructor arguments automatically**: If similar contracts exist these may be available.
* **ABI-encoded Constructor Arguments:** [See this page for more info](broken-reference).
* **Add Contract Libraries:** Enter the name and 0x address for any required libraries called in the called in the .sol file.
* Click the `Verify and Publish` button.
* If all goes well, you will see a checkmark :white\_check\_mark: next to Code in the code tab, and an additional tab called `Read Contract`. The contract name will now appear in BESCSCAN with any transactions related to your contract.

## Via standard JSON input

{% embed url="https://youtu.be/4Ld3j8vTfH4" %}
Verify contract with remix with JSON file super-fast and easy.
{% endembed %}

1. **Contract Name**. There are several options:
   1. Leave blank.
   2. Enter contract name: `MyContract`.
   3. Enter path to the contract and it's name: `path/to/file.sol:MyContract` (path should match what is written in your JSON file).
2. **Include nightly builds**. You can choose **Yes** or **No** depending on your compiler.
3. **Compiler.** Choose the compiler version used to compile your smart contract.
4. **Standard Input JSON.** Attach your Standard Input JSON file. File should follows solidity [format](https://docs.soliditylang.org/en/latest/using-the-compiler.html#input-description) and all the sources must be in Liternal Content format, not an URL.
5. **Try to fetch constructor arguments automatically.** Select No if you want to provide ABI-encoded Constructor Arguments or the contract does not have any.
6. **ABI-encoded Constructor Arguments.** Fill it with ABI-encoded Constructor Arguments or leave blank.

After filling the form click the **Verify & publish** button and wait for the response.

## Troubleshooting

If you receive the dreaded `There was an error compiling your contract` message this means the bytecode doesn't match the supplied sourcecode. Unfortunately, there are many reasons this may be the case. Here are a few things to try:

1\) Double check the compiler version is correct.

{% hint style="info" %}
Check all version digits - for example 0.5.1 is different from 0.5.10
{% endhint %}

2\) Check that an extra space has not been added to the end of the contract. When pasting in, an extra space may be added. Delete this and attempt to recompile.

3\) Copy, paste and verify your source code in Remix. You may find some exceptions here.

### Verification in a dev environment

The [Hardhat verification plugin](broken-reference) supports BlockScout. You can also choose to use the [Sourcify plugin](broken-reference) to verify with Sourcify from your hardhat environment.
