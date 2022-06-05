# MinMicroG Auto Builder

Free computing power to the masses, and laziness to me!

This repo (ab)uses Github's CI mechanism to automatically create MinMicroG
builds whenever something is updated. This offloads the work of manually
checking for updates regularly, as well as making builds for every small
update for people that live on the bleeding edge.

## !!!

These are NOT official releases. For official releases see
[here](https://github.com/FriendlyNeighborhoodShane/MinMicroG_releases)

## !!!

This is NOT the way to self-build MinMicroG (although it can be a shortcut
to do that). For self-building see
[here](https://github.com/FriendlyNeighborhoodShane/MinMicroG)

## !!!

These zips are NOT created by me; I give no guarantees about their legitimacy
or functionality. The script does do signature verification with the last
official release's certificates, however, to the best of its ability.

## What is this?

Every midnight (UTC), Github server VMs will run the `run` shell script.
It will see if something has changed since the last time a CI build or
official release was made, and if it has, it will create a release with
all variants. The release will be tagged on the commit of the binary
assets it was made from.

The release note will be a human-readable list of changes generated by the
`diffmsg` awk script, by feeding on `git diff --raw` outputs with both the
last CI build and the last official release. The update and build log
outputs will be attached as release assets, along with a diff file that
contains the `git diff --stat --patch` outputs.

The
[`refs/volatile/current`](https://github.com/FriendlyNeighborhoodShane/MinMicroG-abuse-CI/tree/refs%2fvolatile%2fcurrent)
branch of this repo holds the entire resdl binary history of official
MinMicroG releases. But the last commit always holds the binaries from the
last CI build.

