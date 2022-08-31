# did-ipns-spec

The Git repository for the DID-IPNS spec document.

It defines a new [DID](https://www.w3.org/TR/did-core/) method, namely DID-IPNS,
which uses IPFS for decentralised, trustless (files are uniquely identified by
the hash of their contents), document storage; and
[IPNS](https://github.com/ipfs/specs/blob/main/IPNS.md) -- an IPFS subsystem --
for a DID naming system.

There is a competing DID-over-IPNS spec which can be found
[here](https://github.com/did-ipid/ipid-method-spec), which has been seemingly
abandoned. All differences between this technical document with the spec for
DID-IPID are given below and justified.

# Differences from the DID-IPID spec

## Method Name

The original spec uses the `IPID` name and `did:ipid:` name space. This spec
uses `IPNS` and `did:ipns:` instead.

This is to avoid unnecessary confusion due to awkward naming. "IPID" implies a
subsystem different from what is used to implement it, or at least an additional
wrapping around IPNS.

However, the [reference librar(ies)](https://www.npmjs.com/package/ipns-did),
all calls are passed through to IPFS facilities, except for adaptations to the
DID spec.

Calling it the IPID method, instead of the IPNS method, would be -- in my
opinion -- like calling an HTTP API - HRPC. There _are_ terms in the IPLD/IPNS
world which don't have a name, but the onus is on the upstream maintainers to
assign them.

## DNSLink Support

The original spec mentions nothing of [DNSLink](https://dnslink.dev). I assume
this is because it didn't exist at the time.

It's a system that can be transparently used alongside IPNS, although a fair bit
of words are needed to handle the two cases.

DNS zone administration can be much more preferrable than keypair handling. It
gives for a nicer DID, and -- unlike IPNS whose sole guarantee is a probability
distribution -- uses the monopoly on force of the government to ensure the
records aren't tampered with. The pros and cons can be found
[here](https://dnslink.dev/#why-dns).

## JSON-LD

The original spec has support for JSON Linked Data, and the `@context` field.
While I admire the Semantic Web idea, and would much prefer it over many of the
"Web 3.0" solutions we're seeing currently being developed, I did not mention it
in the spec.

This is mostly because of my lack of understanding (of the purpose) of the W3C
Semantic Web. I'd like to see this change, and support for the Semantic Web
included in the final spec.

# Open Issues

There a few open issues, which you'll find in the issues tab on the repository.
There are probably other issues which don't have their issue in the issue
tracker. If you find one of these unreported issues, feel free to report them.

The sooner all issues are resolved, the sooner this spec will see production
usage, and the sooner it will be finalised.
