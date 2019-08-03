# LPoS Client

You can utilise the LPoS 'Create Contract' screen to create both Cold Staking and Leased Proof-of-Stake smart contracts that operate in a trustless manner until you decide to cancel the contract. 

This means any coin owner can lease their staking power to any third-party staking merchant \(who may charge a fee for their services\) to receive regular staking rewards - without needing to worry about the technicalities of keeping a wallet open, updated and unlocked for staking. Such LPoS service can be found in the [NIX marketplace](https://nixplatform.io/marketplace).

## Create Contract 

**Cold Staking -** Simply point the 'Lease to' address to your VPS hot wallet address, specify an amount you wish to stake and click 'Send NIX'. You'll be required to input your encryption password if one is set.

**Leased Proof of Stake -** If a merchant doesn't charge a fee for their staking services, then the process is exactly the same as Cold Staking. If they do charge a fee then you'll need to click the 'Enable fee payout' box before being able to enter a Fee Percent and Reward Address. Failure to use the merchants requested Fee Percent and Reward Address will result in your contract being unable to properly stake and earn rewards.

![NIX LPoS &apos;Create Contract&apos; Screen](../../.gitbook/assets/lpos-create.PNG)

**`Lease to:`** Defines the external address allowed to stake the coins. This address is supplied by the merchant.

**`Contract Label:`** A display tag for easier identification in the 'Active Contracts' tab.

**`Amount:`** The amount of NIX you wish to stake. Amounts follow coin control selections if enabled.

**`Fee Percent:`** Amount of reward share allocated to the leasing merchant. This info is provided by the merchant. If the fee is greater than zero, check the "Enable fee payout" box to enter the proper percentage.

**`Reward Address:`** The merchants address for their share of the stake reward when your contract successfully stakes. This address is supplied by the merchant.

## Active Contracts

![NIX LPoS &apos;Active Contract&apos; Screen](https://lh6.googleusercontent.com/PJmItHhSOiRKmdO9rOvCMImoZKV8dFvUJyRfDoY_Zhi533k6LJPxdM9ImYZ6U-igIsmF0a62xM-8mGlgK-zcckkBITnWKTlBkrCo_qrEh0WSgeqI__HqcjWu0_QvrR0muC6a2P1-)

