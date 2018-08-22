# Basic Coding Standard

This section of the standard comprises what should be considered the standard
coding elements that are required to ensure a high level of technical
interoperability between shared Game Maker Code

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be
interpreted as described in [RFC 2119].

[RFC 2119]: http://www.ietf.org/rfc/rfc2119.txt

## 1. Projects

- GM Projects MUST be GML-only (Not Drag & Drop)

## 1.1. Versioning

- Versioning of packages / projects MUST be [Semantic Versioning 2.0.0]

[Semantic Versioning 2.0.0]: https://semver.org/

## 2. Assets

## 2.1. Prefixing

- Sprites MUST be prefixed with `spr_`
- Tilesets MUST be prefixed with `ts_`
- Sounds MUST be prefixed with `snd_`
- Paths MUST be prefixed with `path_`
- Scripts SHOULD NOT be prefixed with `scr_`
- Shaders MUST be prefixed with `sh_`
- Fonts MUST be prefixed with `fnt_`
- Timelines MUST be prefixed with `tl_`
- Objects MUST be prefixed with `obj_`
- Rooms MUST be prefixed with `room_`

## 2.2. Naming

- All names after the prefixes SHOULD BE `camelCase` or `snake_case`. 
This MUST BE consistent throughout the project scope. (Example: `snd_pickup_item` or `snd_pickupItem`)

## 3. GML declarations

- Macro's / Constants MUST be declared in all upper case with underscore seperators.
- Enums MUST be declared in `snake_case` (lower case with underscore seperators), prefixed with `e_`.
- Global variables MUST use the `global.` prefix.
- `globalvar` MUST NEVER be used. 

For example:
```gml
#macro LIVE_CODING false
#macro acceptance:LIVE_CODING false
#macro debug:LIVE_CODING true

enum e_team_colours {
    red,
    blue,
    green,
    yellow,
    light_blue,
}
```

## 4. Package prefixing

All asset names and global variables in packages SHOULD be prefixed with a uppercase, short abbreviation. 
Example: ``Fast Particle System`` will be ``FPS_obj_controller`` and ``FPS_sh_vertexShader``.
Enums and macro definitions MUST follow this standard as well;
```gml
#macro FPS_DEBUG_FLAG_SHOW_OUTLINE 1
#macro FPS_DEBUG_FLAG_SHOW_CENTER_OF_MASS 2
#macro FPS_DEBUG_FLAG_SHOW_VELOCITY 4 

enum FPS_e_team_colours {
    red,
    blue,
    green,
    yellow,
    light_blue,
}
```

An example of where this SHOULD NOT apply would be extra functions that are similar / extensions to GM's internals, 
and are tended to be used like such: ``string_explode``, ``string_reverse``, ``xml_encode``, ``xml_decode``.

### 5. Properties

This guide intentionally avoids any recommendation regarding the use of
`var StudlyCaps`, `global.camelCase`, or `under_score` property names.

Whatever naming convention is used SHOULD be applied consistently within a
reasonable scope. That scope may be vendor-level, package-level, project-level,
or object-level.