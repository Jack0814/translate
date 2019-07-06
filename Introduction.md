# Introduction to CKB Script Programming 1: Validation Model

As of now, the cell validation model in CKB has been more or less stablized, hence I’m starting a series of article introducing CKB script programming here. My goal here is to fill in all the missing implementation details one need to write CKB scripts after reading the whitepaper, so you can start exploring this beautiful wonderland CKB presents.

You might noticed that I call the code running on CKB as `script`, not `smart contract`. This is because smart contract is quite a confusing term to me, and I want to use a different word here to indicate CKB’s unique programmability. A script in CKB’s sense need not be just a script we see in scripting languages such as Ruby, JS, it actually refers to the RISC-V format binary you run on CKB VM.

This first post here, is dedicated to the brand [new verification model](https://github.com/nervosnetwork/ckb/pull/913) introduced in CKB v0.14.0. It might sound boring but I promise you this is the last post without actual examples to play with :P

Note even though I believe CKB’s programming model is quite stable now, development is still happening so there might be changes. I will try my best to make sure this post is updated but if anything confuses you, this post is describing CKB as of [this commit](https://github.com/nervosnetwork/ckb/commit/a02c675c50c5969a588fa7f6356f08861d8f5f92) now.

