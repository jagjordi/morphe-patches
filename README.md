# jagjordi Patches

Patches for use with Morphe. The bundle currently contains one patch for Flightradar24.

## About

The Flightradar24 patch is derived from the "Unlock Business Premium" patch in
[rushiranpise/morphe-patches](https://github.com/rushiranpise/morphe-patches) (GPLv3) and adds
one change: the app's "is free user" helper is forced to false, so the unlock also applies when
no Flightradar24 account is logged in. Upstream, that helper returned true for a missing login
before the patched tier logic ran, which left the promo popups and the aircraft detail locks in
place for logged-out users.

What stays locked: aircraft serial number (MSN) and aircraft age. The Flightradar24 server
withholds those fields from non-subscribers, so no client patch can display them.

### Options

`mapsApiKey` (optional): a Google Maps Android API key injected into the app manifest. Only set
it if the map renders blank after patching. Left empty, the original key is kept.

### How to use these patches

Add this source in Morphe Manager: https://morphe.software/add-source?github=jagjordi/morphe-patches

Automated builds for a non-rooted device are published by
[ShrirajHegde/Morphe-Builds](https://github.com/ShrirajHegde/Morphe-Builds).

## Patches list

<!-- PATCHES_START EXPANDED -->

<!-- Do not modify this section by hand. The patch list is generated when release.yml creates a new release. -->

#### A list of the patches will automatically be shown here after the first patches release is created.

<!-- PATCHES_END -->

### Building locally

- Run `./gradlew buildAndroid` with `GITHUB_ACTOR` and `GITHUB_TOKEN` set so Gradle can read the
  Morphe package registry.
- The built patches `.mpp` file is found in `patches/build/libs/patches-*.mpp`.
- Patch the mpp file using [Morphe-Desktop](https://github.com/MorpheApp/morphe-desktop)
  like any other patch bundle.

See the [Morphe documentation](https://github.com/MorpheApp/morphe-documentation) for more information.

## License

jagjordi Patches are licensed under the [GNU General Public License v3.0](LICENSE).
