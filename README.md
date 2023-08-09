# zfxyu-spec: ZFXYU specifications (Work in Progress)

# Definition
Four-dimentional spatial identifier candidate ZFXYU of a point with longitude _lng_ [decimal degrees], latitude _lat_ [decimal degrees] (_lat_rad_ in radians), elevation _h_ [m], and unix time _t_ [s] shall be encoded `{z}/{f}/{x}/{y}.{u}` when a zoom level _z_ is given as an integer and _f_, _x_, _y_, _u_ are given in the following formulae: 
- `f = floor(n * h / H)`
- `x = floor(n * ((lng + 180) / 360))`
- `y = floor(n * (1 - log(tan(lat_rad) + (1 / cos(lat_rad))) / PI) / 2)`
- `u = floor(t / 1800)`
- where `n = 2 ^ z`, `Z = 25` and `H = 2 ^ Z [m]`.

Definitions of _z_, _x_, _y_ are the same as ones in the industry standard [Slippy Map Tilenames](https://wiki.openstreetmap.org/wiki/Slippy_map_tilenames).

# Characteristics
- Height of a voxel represented by a ZFXYU with z=Z is 1 [m].

# Future considerations
- More compact encodings of ZFXYU may be considered in future. 
- The value of `Z` is still subject to change.
