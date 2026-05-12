# engeen-services

Vendor organisation for the **DataArpeggio** appliance — an offline-installable, ontology-driven data migration platform.

Source code: [engeen-services/data-arpeggio](https://github.com/engeen-services/data-arpeggio)

## Vendor Cosign signing key — current fingerprint

DataArpeggio release bundles, container images, and update channel manifests are signed with the vendor's Cosign key. Pin the fingerprint at first install and re-verify after every upgrade.

**Current fingerprint** (SHA-256 of the public key DER, rotated 2026-05-12):

```
47:6e:32:7e:0c:73:1d:24:29:09:94:9d:26:fa:b3:db:a0:e9:16:a8:ee:d9:b6:34:93:40:ca:9e:35:8c:94:28
```

This page is one of the three out-of-band locations where the vendor publishes the current fingerprint (the other two: the vendor website, and the customer-facing operator handbook shipped inside each release bundle). Compare any two of the three against the fingerprint you compute from `scripts/deploy/vendor-cosign.pub` after install:

```bash
openssl pkey -in scripts/deploy/vendor-cosign.pub -pubin -outform DER \
  | openssl dgst -sha256 -c
```

If at least two of the three locations match, the key is pinned. Record the fingerprint in your own deployment notes so you can re-verify after future upgrades.

Rotations happen once per major release or after a suspected compromise. The vendor announces rotations separately; you verify the new fingerprint against the freshly-published value here and on the other two locations before accepting the upgrade.

## Rotation history

| Date | Fingerprint (SHA-256 DER) | Reason |
|---|---|---|
| 2026-05-12 | `47:6e:32:7e:0c:73:1d:24:29:09:94:9d:26:fa:b3:db:a0:e9:16:a8:ee:d9:b6:34:93:40:ca:9e:35:8c:94:28` | Post-Forgejo→GitHub migration |
