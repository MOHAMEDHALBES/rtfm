# App enhancement format ```WIP```

All app enhancements on appdb need to have the following format in order to be easily published and combined with apps.

## Structure

appdb does not compile enhancements in runtime, as it will require lots of processing power and increases security risks. Instead, we ask you to provide complied binary forms alongside with your app enhancement source code (if it is included).

Each enhancement is a **ZIP** archive that contains:

1. Required: Binaries, dylibs, frameworks, supporting files in ```dist``` folder in the root of ZIP. This folder can also include **.deb** packages, that will be unpacked and added in runtime.
2. Required: A ```VERSION.txt``` file in the root of ZIP that defines enhancement version number.
3. Required: A ```NAME.txt``` file in the root of ZIP that defines enhancement name.
4. Required: A ```DEVELOPER.txt``` file in the root of ZIP that defines enhancement developer name.
5. Required: A ```icon.png``` file in the root of ZIP. An app enhancement icon to be displayed.
6. Required: A ```DESCRIPTION.md``` file in the root of ZIP, containing app enhancement description. Otherwise, you have to fill it manually.
7. Optional: A ```RELEASE.md``` file in the root of ZIP, containing what's new and release notes. Otherwise, you have to fill it manually.
8. Optional: A ```LICENSE.txt``` file in the root of ZIP, containing app enhancement licensing terms. Otherwise, you have to fill it manually or app enhancement will be considered as public domain.
9. Other files (source code, any other instructions, etc) in the root of ZIP that will be available if user downloads an archive, but ignored when appdb combines an enhancement and app on demand of the user.

## Additional notes

If app enhancement requires Cydia Substrate, appdb detects it and bundles automatically. You don't need to put it inside ```dist``` folder.

## Sample code

Sample [app enhancement is published on appdb](#).

Last updated 3 Mar 2024.
