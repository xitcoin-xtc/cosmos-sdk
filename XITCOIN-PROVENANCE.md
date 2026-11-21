# Xitcoin dependency fork

Maintainer: xitcoin-xtc (formerly xitcoin-org). Upstream: https://github.com/cosmos/cosmos-sdk/releases/tag/v0.54.5 (commit 4c5119fe2514241b963a6eb75972761797a5cb1d).
Changed on 2026-09-13 for https://github.com/xitcoin-xtc/pos-chain/issues/33 and PR44, originally on v0.54.4 (dedeb7c80a91c47ae83f5352e29c3dd34e4a3fc6, fork commit 52ff14a25bee524f0e48ae7f00664443bcb22335). Rebased unchanged onto v0.54.5 on 2026-11-21 because upstream retracted v0.54.0 to v0.54.4; v0.54.5 adds the x/feegrant queue migration (consensus version 3).

Production armor imports ProtonMail/go-crypto v1.4.1. Historical formats and encryption remain unchanged. On 2026-09-14, full keyring tests identified that the maintained reader ignores CRC24; DecodeArmor now validates the historical checksum through the maintained encoder and requires the end line when a checksum is present. No obsolete OpenPGP code is imported or copied. make tidy-all propagates Go-generated sums to nested modules; Bash invocation is corrected.

Module declarations retain their original import identity. Downstream replacements must pin an immutable revision and retain advisory mapping to upstream; a renamed fork is not a vulnerability clearance. Current downstream review status is recorded in xitcoin-xtc/pos-chain (docs/security-assessment.json); no independent approval is implied.

Original copyright and license notices are preserved. SDK core: LICENSE (Apache-2.0); enterprise/group and enterprise/poa remain owned by Cosmos Labs US Inc. and governed by their respective LICENSE files (Source Available Evaluation License), only evaluated in qualification, not added to the Xitcoin application. Geth: COPYING.LESSER for library code and COPYING for GPL components/commands, subject to per-file notices. Dependencies retain their own licenses. This fork distributes corresponding source, not deployment binaries.

The fork commit is a qualification candidate until the complete required upstream checks and downstream review pass. No production suitability or global PASS is implied.
