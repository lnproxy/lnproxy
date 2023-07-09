# lnproxy

## What

lnproxy is a simple privacy tool that makes invoices more private.
Users of custodial Lightning wallets get better payment destination privacy
and sovereign node runners with enhanced receiver privacy.
lnproxy works like a
["Poor man's rendez-vous"](https://www.mail-archive.com/lightning-dev@lists.linuxfoundation.org/msg02667.html),
providing privacy for users without taking custody of their funds.

## Why

Lightning network invoices reveal the destination of payments.

-	Users who operate public Lightning Network nodes reveal the identity of their node
	with every Lightning invoice they generate.
	With lnproxy, these users can obfuscate the destination of their payment from their custodian.

-	Users of custodial Lightning wallets reveal the destination
	of every Lightning invoice they pay to their custodians.
	With lnproxy, these users can obfuscate the identity of their Lightning nodes
	from their transaction counterparties.

## How

Proxy invoices are hodl invoices.
When an lnproxy relay accepts an htlc for the proxy invoice,
it immediately pays the original invoice
and uses the revealed preimage to settle the proxy invoice.
This ensures that you don't need to trust lnproxy relays
with your payments.
