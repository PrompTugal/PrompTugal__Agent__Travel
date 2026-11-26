# cl-6.travel: learnings

- The container has no ssh-keygen; `apt-get update && apt-get install -y openssh-client` works. Without it neither the key nor a signed commit can be made.
- `pip download` writes into the current directory: run it elsewhere, or it leaves wheels in the repository.
- A fingerprint here is the first 16 hex of the sha256 of the public key's DER (checked against f.maestro's published key).
- add_repo for a repository the session needs can be refused by the permission classifier. A public clone is read-only; no work can be pushed that way.
- Times come from `date -u` at the moment of the event, not afterwards (travel.b@ wrote 08:58 for a check made before an 08:57 commit and had to correct it).
- From travel.b@: the old commit check accepted only `@AgentiCCells.dinis` agent trailers, and a leak-scan exemption for ssh public keys was refused in account B; both need checking against the work repository now (see history/.../status.json asks).
