# Version

Describes the current version of the database document in question, in string format. This is quite often left blank, but it is highly recommended to follow [semantic versioning](https://semver.org) (semver) to keep track of your changes/progress between versions and releases.

## Symbol

    VERSION

## Syntax

    VERSION "[major].[minor].[patch][-<pre>.<id>]"

## Examples

    VERSION "2021.06.08"
    VERSION "3.11.0"
    VERSION "0.1.1-beta.1"
    VERSION "1.0.0-rc.10"
