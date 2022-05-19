# Star Commands

___

A set of special commands appended to the names of

- Materials
- Objects
- Lights
- Portals
- World Terrain

that expose extended functionality

- Star commands applied to a object / terrain will be applied to all it's materials
- Star commands applied to a composite material will be applied to both it's children       

## Material Star Commands    
| Flag | Description |
| ---- | ----------- |
| \*id(nID)" | |                                                                                                   
|*id(nID)                                                                                                                                                         | |
|*collid(nID)                                                                                                                                                     | |
|*sort                                                                                                                                                            | |
|*order(nOrderNum)                                                                                                                                                | |
|*shader(nShaderNum)                                                                                                                                              | |
|*motif(nEmissiveMotifID, bUseEmissiveColor, nSpecularMotifID, bUseESpecularColor, nDiffuseMotifID, bUseDiffuseColor)                                             | |
|*anim(nNumTexFrames, fFramesPerSec)                                                                                                                              | |
|*rotate(fDeltaUVRotationPerSec, vRotateAroundU, vRotateAroundV)                                                                                                  | |
|*scroll(nXDirection, fXSpeed, nYDirection, fYSpeed)                                                                                                              | |
|*z(nZTugValue)                                                                                                                                                   | Used for drawing material above other materials and preventing z-fighting. Commonly used with decals. |
|*nocoll                                                                                                                                                          | |
|*coll(bPlayer, bNPC, bObstructLineOfSight, bThinProjectiles, bThickProjectiles, bCamera, bObjects, bWalkable, bObstructSplashDamage, bCDebris, bVehicles bHover) | |
|*noascroll                                                                                                                                                       | |
|*tint                                                                                                                                                            | |
|*writez                                                                                                                                                          | |
|*nomeshtint                                                                                                                                                      | |
|*bumptile(fBumpMapTileFactor)                                                                                                                                    | |
|*detailtile(fDetailMapTileFactor)                                                                                                                                | |
|*light(R, G, B, I)                                                                                                                                               | |
|*nodraw                                                                                                                                                          | Causes material to be invisible. Will not block lights in lightmaps. |
|*notinlm                                                                                                                                                         | |
|*nolmblock                                                                                                                                                       | |
|*nolmuse                                                                                                                                                         | |
|*vertrad                                                                                                                                                         | |
|*noshadows                                                                                                                                                       | |
|*eangle(nAffectAngle)                                                                                                                                            | |
|*tangle(nAffectAngle)                                                                                                                                            | Causes material to only be visible from certain angles. Commonly used for things like light bloom effects. <br> `nAffectAngle`: The angle in degrees.  |
|*surf(nSurfaceType)                                                                                                                                              | Changes the surface type.  <br> 0 = Default  <br> 1 = Concrete  <br> 2 = Metal  <br> 3 = Metal grate  <br> 4 = Dirt  <br> 5 = Rock  <br> 6 = Glass  <br> 7 = Composite  <br> 8 = Electronics  <br> 9 = Junk  <br> 10 = Water  <br> 11 = Goop  <br> 12 = Acid  <br> 13 = Force field |
|*react(nReactType)                                                                                                                                               | |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            

## Object Star Commands
| Flag | Description |
| ---- | ----------- |
|*postery            | |
|*posterx            | |
|*posterz            | |
|*nocoll             | |
|*nofog // LEGACY    | |
|*nolight            | |
|*culldist(fCullDist)| |
|*tint(R, G, B)      | |
|*sort // LEGACY     | |
|*nodraw             | |
|*acceptlm           | |
|*vertrad            | |
|*acceptshadows      | |
|*castshadows        | |
|*dynamic            | |
|*nolmuse            | |
|*lightperpixel      | |

## Light Star Commands
| Flag | Description |
| ---- | ----------- |
|*self                          |  |
|*castshadows                   |  |
|*scalecorona(fCoronaScale)     |  |
|*fadingcorona(szCoronaTexture) |  |
|*corona(szCoronaTexture)       |  |
|*onlyppmesh                    |  |
|*onlydynamic                   |  |
|*lm                            |  |
|*uniquelm                      |  |
|*onlylm                        |  |
|*noterrain                     |  |
|*id(nLightID)                  |  |
|*motif(nMotifID)               |  |

## Portal Star Commands
| Flag | Description |
| ---- | ----------- |
|*mirror|	         |
|*sound	|	         |
|*1way	|            |
|*oneway|	         |
|*anti	|            |