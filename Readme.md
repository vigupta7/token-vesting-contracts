# Contracts for erc20-token distribution, bucket allocation and vesting.

This project demostrates how to create an ERC20 Token with fixed supply and mint/distribute the supply to different buckets or child contracts.

Each child contract may have a different token vesting and locking machanism.

The main token file is "token.sol". It creates an erc20 token using well defined @openzepplin standards. it has a "setAllocation" method which can be called only once by the owner.

The "setAllocation" method mints 100 million tokens and distibute it to below 6 buckets with differenr allocation.

1. Strategic Bucket : 39% i.e 39 million tokens
2. Founsation Bucket: 10% i.e 10 million tokens
3. Marketing Bucket : 25% i.e 25 million tokens
4. Liquidity Bucket : 10% i.e 10 million tokens
5. Team Bucket      : 10% i.e 10 million tokens
6. Advisers Bucket  : 5% i.e 5 million tokens

There are below 3 methods common in each bucket.

1. "GrantAllocation" : it allows the owner to grant specefic token allocation to multiple users at once from specefic bucket.

2. GetClaimableBalance: it gets the amount of tokens vested till time for a given address.

3. ProcessClaim: using this method the token alotee can claim the vested tokens available as per the locking and vesting login of that bucket.


In parallel, each bucket has below different locking and vesting mechanism and is created as a seperate contract to ensure better visibility.

Strategic Distribution - 10% shall be vested on-listing, Then daily vesting over a period of 365 days.

Foundational Reserve - Locked for 1 year then Daily vesting over 365 days.

Marketing/Business Development - 10% vested on listing, then daily vesting over 365 days.

Liquidity - No vesting, 10% of the total supply is allocated for liquidity.

Team - Locked for 1 year, then daily vesting over 365 days.

Advisors - Locked for 1 year then daily vesting over 365 days.