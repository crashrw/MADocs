# Gamedata
___

Gamedata flags & values are case insensitive.

Gamedata is written as `Flag=Value`. Defining an entity to be a Mil Grunt would be...

    type=botgrunt

## Shared Flags
Flags shared between almost all types of entities

| **Required**  | **Flag**             | **Value(s)**   | **Example**                     | **Description** |
| ---           | ---                  | ---            | ---                             | ---             |
| Optional      | [Name](#name)        |                | Name=Goff                       | Tags an entity with a name used by other entities or in scripting |
| Optional      | Attach               |                | Attach=Goff                     | Parents entity with another entity so they move together |
| Optional      | AttachBone           |                | AttachBone=Head                 | Parents entity with the name of another entity’s bone |
| Optional      | InWorld              | True \| False  | InWorld=False                   | Makes an entity invislbe and intangible. Useful if you want to spawn entity with a script |
| Optional      | Tripper              | On \| Off      | Tripper=on                      | If tripper=on, allows the entity to activate tripwire triggers |
| Optional      | Include              |                | Include=vlax01                  | Includes a specified CSV file. Can be used by bots for external User Properties like Vlax |
| Optional      | Health               | 0.0 to 1.0     | Health=0.6                      | Sets an entities health. For bots with batteries (Glitch) 1 = one full battery |
| Optional      | ArmorProfile         |                | ArmorProfile=pred               | Uses an entry in armor.csv as armor. Use nohitpoint if entity recieves no damage |
| Optional      | ArmorExplosion       | 0 to 100       | ArmorExplosion=50               | Vulnerability to explosion damage. 100 = invulnerable |
| Optional      | ArmorFlame           | 0 to 100       | ArmorFlame=75                   | Vulnerability to flame damage. 100 = invulnerable |
| Optional      | ArmorBullet          | 0 to 100       | ArmorBullet=100                 | Vulnerability to bullet damage. 100 = invulnerable |
| Optional      | GoodieBag=1, one     |                |                                 | Gives entity a “goodiebag” containing an item dropped on death |
| Optional      | Goodie1              | ItemName,1,1,1 | Washer,6,6,1                    | Item in bag, first two digits are amount of item and must be the same |
| Optional      | Goodie2              | ItemName,1,1,1 | Washer,6,6,1                    | Additional goodie in bag. Entity can carry up to 6 goodies. |
| Optional      | Sound_Ambient_Tag    | Sound name     | Sound\_Ambient\_Tag=L15\_convey | Sound Wav name or sfb tag to play |
| Optional      | Sound_Ambient_Volume | 0.0 to 1.0     | Sound\_Ambient\_Volume=0.5      | Sound volume |
| Optional      | Sound_Ambient_Radius |                | Sound\_Ambient\_Radius=15       | Radius sound can be heard |
| Optional      | Sound_Ambient_Off    | 0 \| 1         | Sound\_Ambient\_Off=1           | Whether the sound should start off |

### <u>Name</u>
To give the entity a name that can be referenced by another entity and by the game code, use the "name=" command. This is optional. Don't give it a name if you don't have to. If you're not sure whether your entity needs a name or not, then don't give it one.


## Bot flags
Flags used by bots

| **Required** | **Flag**                                        | **Value(s)** | **Example** | **Description** |
| ---          | ---                                             | ---       | ---         | ---             |
| Required     | type                                            | [Bot Types](userdata.md#bot-types)          | type=botgrunt | The type of bot this is. Refer below for list of bot types |
| Optional     | ArmorModifier                                   | -1.0 to 1.0                                 | ArmorModifier= -0.9 | Changes strength of bot’s armor |
| Optional     | NPCWeapon0                                      | Laser                                       | NPCWeapon0=spew | Primary weapon used by this bot. (Grunt and Droid Miner only) |
| Optional     | NPCWeapon1                                      | grenade                                     | NPCWeapon1=grenade | Secondary weapon used by this bot. (Grunt only) |
| Optional     | DropWeapon                                      | True \| False                               | DropWeapon=False | If set to false, this bot will never drop it's weapon when killed |
| Optional     | DataPort                                        | Open \| Closed                              | DataPort=Open | If set to open, this bot gains a dataport that Glitch can use to possess this bot through the Control Tether, otherwise Glitch cannot use the control tether on this bot |
| Optional     | PossessDist                                     | Integer                                     | PossessDist=250 | Max distance this bot can travel from it's point of possession before ejecting Glitch |
| Optional     | Shield                                          | On \| Off                                   | Shield=On | (Grunts and Titans only) <br> Spawns this bot with a shield <br> A Titan will gain a L3 Rocket Launcher |
| Optional     | DisguiseTime                                    | Time in seconds                             | DisguiseTime=21 | How long in seconds before this bot realizes Glitch is disguised as a Mil |
| Optional     | Sleeping                                        | True \| False                               | Sleeping=True | (Grunt & Trooper Only) <br> Grunt: Sit down in a bored expression <br> Trooper: Perch upside down levitating in position, upon waking up the trooper will drop down |
| Optional     | PowerDownUntilPosessed                          | True \| False                               |  | If set to true, this bot will always be powered down unless possessed by Glitch |
| Optional     | CanBeRecruited                                  | True \| False                               |  | If set to true, this bot can be affected by a recruiter grenade |
| Optional     | CanBeRecruitedWithoutDataport                   | True \| False                               |  | If set to true, this bot can be affected by a recruiter grenade even if DataPort=Closed |
| Optional     | NoEMP                                           | True \| False                               | NoEMP=True | Whether this bot is affected by EMP grenades |
| Optional     | SpotLightOn                                     | True \| False                               | SpotLightOn=True | When this bot is spawned, should it have it's spotlight enabled |
| Optional     | disablelight                                    | True \| False                               | disablelight=True | When this bot is spawned, should it have it's spotlight disabled |
| Optional     | KeepLimb                                        | All \| None                                 | KeepLimb=All | Prevents specified limbs from breaking off |
| Optional     | MeshReplace                                     | .ape name                                   | | Change the bot mesh to the one provided |
| Optional     | MeshVersion                                     | 0 \| 1                                      | MeshVersion=1 | Swaps to alternate mesh for bot. Only used for Corrosive |
| Optional     | Vlax                                            | True \| False                               | Vlax=True | (Grunts Only) <br> Whether this bot is Vlax |
| Optional     | AI\_Job                                         | Wait \| Patrol \| Wander                    | AI\_Job=Wait | Tells the bot to wait, use a Patrol Path, or wander around |
| Optional     | AI\_WanderRadius                                |                                             | AI\_WanderRadius=40 | Radius bot is allowed to wander (Only if AI\_Job=Wander) |
| Optional     | AI\_WanderStayInRoom                            | True \| False                               | AI\_WanderStayInRoom=True | Bot only wanders in this room (Only if AI\_Job=Wander) |
| Optional     | AI\_WanderPoints                                | A, B, C                                     | Point1, Point2 | Use names of entities as points to wander between (Only if AI\_Job=Wander) |
| Optional     | AI\_PatrolPath                                  |                                             | AI\_PatrolPath=PatrolPath01 | Use the name of a spline entity as patrol path (Only if AI\_Job=Patrol) |
| Optional     | AI\_PatrolDir                                   | Forward \| Backward                         | AI\_PatrolDir=Forward | Direction to move on patrol path (Only if AI\_Job=Patrol) |
| Optional     | AI\_PatrolSpeed                                 | 0 - 100                                     | AI\_PatrolSpeed=70 | % of bots base movement speed to use when patrolling (Only if AI\_Job=Patrol) |
| Optional     | AI\_FollowLeader                                |                                             | AI\_FollowLeader=Goff | Name of bot to treat as leader |
| Optional     | AI\_BaseSpeed                                   | 0 - 100                                     | AI\_BaseSpeed =60 | % of bots base movement speed the bot is capable of |
| Optional     | AI\_TorsoAlignmentSpeedConstraint               | 0 - 100                                     |  | How much speed is limited by poor "forward" torso alignment |
| Optional     | AI\_TorsoAlignmentVelConstraint                 | 0 - 100                                     |  | How much the direction of movement is limited by poor "forward" torso alignment |
| Optional     | AI\_TorsoAlignmentConstraintIgnorable           | True \| False                               |  | Whether to ignore poor “forward” torso alignment entirely |
| Optional     | AI\_Race                                        | Ambient \| Droid \| Good \| Bad             | AI\_Race=Droid | Race bot is affiliated with. Ambient means friendly unless attacked |
| Optional     | AI\_AttackWho                                   | A, B                                        | AI\_AttackWho=Players, Enemy | Use at least one of (Enemy, Neutral, Friendly) and one of (Players, NPC)<br>Use an exclamation point to excluse one. Example !Players, NPC, Enemy |
| Optional     | AI\_Aggression                                  | 0 - 100                                     | AI\_Aggression=50 | How likely bot is to go on attack when seeing an enemy |
| Optional     | AI\_Courage                                     | 0 - 100                                     | AI\_Courage=100 | How likely bot is to flee when threatened |
| Optional     | AI\_Intelligence                                | 0 - 100                                     | AI\_Intelligence=100 | How well bot retains and applies knowledge |
| Optional     | AI\_WeaponBurstDelay                            | 0 - 100                                     | AI\_WeaponBurstDelay=1 | Delay between bursts of weapon fire |
| Optional     | AI\_WeaponBurstCount                            | 0 - 100                                     | AI\_WeaponBurstCount=6 | Number of bursts of weapon fire |
| Optional     | AI\_WeaponAccuracy                              | 0 - 100                                     | AI\_WeaponAccuracy=70 | Weapon accuracy |
| Optional     | AI\_NumGrenadesAtStart                          |                                             | AI\_NumGrenadesAtStart=25 | Number of grenades bot starts with (only if using NPCWeapon1=grenade) |
| Optional     | AI\_OddsOf\_Ignoring\_Nearby\_Grenades          | 0 - 100                                     |  | Odds of bot reacting to a nearby grenade |
| Optional     | AI\_Grenade\_Use                                | Whenever \| Smart \| EnemySight             | AI\_Grenade\_Use=First\_Contact | When and how bot uses grenades |
| Optional     | AI\_Grenade\_Use\_First\_Contact                | True \| False                               |  | Whether bot uses a grenade upon first contact with enemy |
| Optional     | AI\_Attack\_Notify\_Radius                      |                                             | AI\_Attack\_Notify\_Radius=90 | Radius to notify allies when spotting or attacking enemy |
| Optional     | AI\_WaitLookAt                                  |                                             | AI\_WaitLookAt=LookAtMe | Name of an entity bot will look at when waiting (only if AI\_Job=Wait) |
| Optional     | ai\_waitLookAroundOdds                          | 0 - 100                                     | ai\_waitLookAroundOdds=50 | % chance of bot looking around every 30 seconds (only if AI\_Job=wait) |
| Optional     | AI\_Eye\_Scan\_Dist                             |                                             | AI\_Eye\_Scan\_Dist=1200 | Distance bot will scan when using eyes |
| Optional     | AI\_EyeCosHalfFOV                               |                                             | AI\_EyeCosHalfFOV=0.0f | \-1.0f = 360 FOV. 0.0f = 180 FOV. 0.707 = 90 FOV. 1.0f = 0 FOV (no vision) |
| Optional     | AI\_EyeCosHalfFOV\_Alert                        |                                             | AI\_EyeCosHalfFOV\_Alert=0.0f |  |
| Optional     | AI\_Bonus\_Eye\_Scan\_Dist\_For\_Players        |                                             |  | Additional distance added to AI\_Eye\_Scan\_Dist when searching for player |
| Optional     | AI\_Bonus\_Eye\_Scan\_Dist\_For\_Players\_Alert |                                             |  |  |
| Optional     | AI\_HearingScale                                |                                             | AI\_HearingScale=230 | The radius of all sounds in the world become magnified by this value for this bot |
| Optional     | AI\_HearingScale\_Alert                         |                                             |  |  |
| Optional     | AI\_StartleMin                                  | 0 - 100                                     | AI\_StartleMin=12 | Minimum time between startles. Default 10 |
| Optional     | AI\_StartleMax                                  | 0 - 100                                     | AI\_StartleMax=25 | Maximum time between startles. Default 30 |
| Optional     | AI\_WakeUp\_Min\_Rad                            |                                             | AI\_WakeUp\_Min\_Rad=20 | Radius for bot being woken up. Default 35 |
| Optional     | AI\_AttackMaxDistFromOrigin                     |                                             | AI\_AttackMaxDistFromOrigin=100 | Max distance (feet) bot will travel from spawn point to attack. |
| Optional     | AI\_PreferStopAndShoot                          | True \| False                               | AI\_PreferStopAndShoot=False | Whether bot prefers to attack on the move, or stop moving when attacking |
| Optional     | AI\_UseVehicleWhen                              | Never \| Init                               | AI\_UseVehicleWhen=Never | Whether or when to use a nearby vehicle. Init = on level start |
| Optional     | AI\_UseVehicleType                              | Loader \| Sentinel \| Rat \| Ratgun \| Pill | AI\_UseVehicleType=Pill | Type of vehicle bot will use |
| Optional     | AI\_UseVehicleRadius                            |                                             | AI\_UseVehicleRadius=100 | Radius bot will search for a vehicle |
| Optional     | AI\_Buddy\_Ctrl                                 | Never \| Auto \| OnAction                   | AI\_Buddy\_Ctrl=Auto | Behavior of allied bots. OnAction = when told, buddy up. Auto = Auto buddy with friendlies |
| Optional     | Sci\_Friends\_In\_Need\_Scan\_Dist              |                                             |  | Distance Mil Scientist will search for allies who need help |
| Optional     | ZombieStartFormed                               | True \| False                               | ZombieStartFormed=True | Whether ZombieBot should start formed on level start |
| Optional     | PredSpeed                                       | 0 - 100                                     | PredSpeed=75 | % of base speed Predator can move |
| Optional     | MaxAltitude                                     |                                             |  | Max height Predator can go to |
| Optional     | EntityRange                                     |                                             | EntityRange=200 | Range of the Mortar bots attack |

### Bot Types
Bots are specified in gamedata by the bot name. If I wanted X entity to be a grunt, I would add to gamedata...

    type=botgrunt
    
| **Bot Name**                  | **Value(s)**         | **Description** |
| ---                           | ---               | ---             |
| Droid Miner                   | botblink          | |
| Droid Krunk                   | botkrunk          | |
| Droid Miner                   | botminer          | |
| Droid Slosh                   | botslosh          | |
| Mil Grunt                     | botgrunt          | Use NPCWeapon0= flag to change this bot's weapon |
| Mil Elite Guard               | boteliteguard     | |
| Mil Titan                     | bottitan          | |
| Mil Jump Trooper              | botjumper         | |
| Mil Predator                  | botpred           | |
| Mil Leech                     | botprobe          | |
| Mil Scientst                  | botscientist      | |
| Mil Snarq                     | botsnarq          | |
| Mil General Corrosive         | botcorrosive      | |
| Mil Anti Air Gun              | botAAgun          | |
| Mil Mortar                    | botmortar         | |
| Mil Sentry                    | SiteWeapon        | |
| Swarmer                       | botswarmer        | |
| Zombiebot                     | botzombie         | |
| Zombiebot King                | botzombieboss     | |

## Goodie Flags
Flags used for item and weapon pickups

| **Required** | **Flag** | **Value(s)** | **Example** | **Description** |
| ---          | ---      | ---          | ---               | ---             |
| Required     | type=goodie |  |  | Required for this entity type |
| Required     | GoodieType | [Goodie Types](userdata.md#goodie-types) | GoodieType=pup\_energy | Type of goodie. |
| Optional     | GoodieDuration | Seconds | Goodieduration=20 | How long a powerup will last in seconds |
| Optional     | SpawnTime | Seconds | Spawntime=5 | How long in seconds before goodie respawns |
| Optional     | Ammo |  |  |  |
| Optional     | BatteryNum | 1 to 6 | Batterynum=1 | Which battery number to use if GoodieType=Battery (Required) |

### Goodie Types

| **Uses Levels**   | **Value(s)** | **Goodie Name** | **Example** | **Description** |
| ---               | ---       | ---             | ---         | ---             |
| <h2>Health</h2>   | | | | |
| No                | pup\_energy  | Health                |                         | Restore 1 battery of health to Glitch |
| No                | mega health  | Mega Health           |                         | Restore all of Glitch's batteries for full health |
| <h2>Powerups</h2> |              |                       |                         | GoodieDuration controls how long this powerup will last for |
| No                | pup\_armor   | Shield / Armor        |                         |  |
| No                | pup\_weapon  | X2 Weapon Damage      |                         |  |
| No                | pup\_speed   | Speed Boost           |                         |  |
| No                | pup\_hijump  | Super Jump            |                         |  |
| <h2>Campaign</h2> |              |                       |                         |  |
| No                | chip         | Blue Chip             |                         |  |
| No                | secret chip  | Secret Chip           |                         | Worth 1 value of currency |
| No                | washer       | Washer                |                         | Worth 25 value of currency |
| No                | megawasher   | Gold Washer           |                         | Used to unlock Multiplayer levels |
| No                | Det Pack     | Det Pack              |                         |  |
| No                | Battery      | Battery               |                         | LOOK INTO battery [1-6]     Battery (make sure to include batterynum) |
| Yes               | Arm Servo    | Arm Servo upgrade     | goodietype=Arm Servo L2 |  |
| Yes               | EUK          | Equipment Upgrade Kit | EUK laser L2            | EUK as the prefix, then the weapon name, finally the weapon level as the suffix |
| No                | goffhead     | Agent Goff’s Head     |                         |  |
| No                | gofftorso    | Agent Goff’s Torso    |                         |  |
| No                | goffleg      | Agent Goff’s legs     |                         |  |
| <h2>Primary Weapons</h2>         |                       |                         |  | Weapons that use levels MUST have L1, L2, or L3 after their name |
| Yes              | laser         | Mining Laser          | laser L2                |  |
| Yes              | spew          | Spew                  | Spew L3                 |  |
| Yes              | rocket        | Rocket Launcher       | rocket L3               |  |
| Yes              | blaster       | Scatter Blaster       | blaster L1              |  |
| Yes              | ripper        | Ripper                | ripper L2               |  |
| Yes              | tether        | Control Tether        | tether L3               |  |
| Yes              | flamer        | Toaster               | flamer L1               |  |
| No               | mortar        | Slingshot             |                         |  |
| Yes              | rivet         | Rivet Gun             | rivet L2                |  |
| <h2>Secondary Weapons</h2>       |                       |                         |  | Weapons that use levels MUST have L1, L2, or L3 after their name |
| No               | coring charge | Coring Charge         |                         |  |
| No               | cleaner       | Cleaner               |                         |  |
| No               | emp grenade   | EMP                   |                         |  |
| No               | magma bomb    | Magma Bomb            |                         |  |
| No               | recruiter     | Recruiter Grenade     |                         |  |
| Yes              | scope         | Scope                 | scope L1                |  |
| No               | wrench        | Wrench                |                         |  |


## Door flags 
Flags used for door entities

| **Required** | **Flag** | **Value(s)** | **Example** | **Description** |
| ---          | --- | --- | --- | --- |
| Required     | type=door    |                    |  | Required for door entities |
| Required     | BehaveType   | Door / Other       | BehaveType=Door | Behavior type. Other is used for behaviors other than a normal door |
| Optional     | ActiveRadius |                    | ActiveRadius=12 | Door opens when bot is within specified radius around door |
| Optional     | Displace     | X, Y, Z            | Displace=0, 0, 14.5 | X Y Z distances to displace when moving |
| Optional     | RotateY      |                    | RotateY=180 | Amount to rotate door as it moves |
| Optional     | Anim         | Animation MTX name | Anim=aodmdor01 | Animation to play when door opens or closes (Plays in reverse for closing) |
| Optional     | AnimSpeed    | Float              | Animspeed=0.8 | Animation speed. Higher numbers = slower speeds. |
| Optional     | IsPortal     | True \| False      | IsPortal=True | Culls cells behind door when closed (use in conjunction with a portal placed between cells) |
| Optional     | AutoClose    | True \| False      | AutoClose=False | Whether door should close automatically |
| Optional     | AIAccess     | True \| False      | AIAccess=False | Whether bots are allowed to use this door |
| Optional     | PlayerAccess | True \| False      | PlayerAccess=False | Whether the player is allowed to use this door |
| Optional     | SseAccel     | True \| False      | SseAccel=False | Whether to use acceleration |
| Optional     | open\_start  | Sound name         | open\_start=BD\_Open | Sound Wav name or sfb tag to play when door opens |
| Optional     | open\_loop   | Sound name         | open\_loop=BD\_Loop | Sound Wav name or sfb tag to play when door is opening |
| Optional     | open\_stop   | Sound name         | open\_stop=BD\_Close | Sound Wav name or sfb tag to play when door finished opening |
| Optional     | close\_start | Sound name         | close\_start=BD\_Open | Sound Wav name or sfb tag to play when door starts closing |
| Optional     | close\_loop  | Sound name         | close\_loop=BD\_Loop | Sound Wav name or sfb tag to play when door is closing |
| Optional     | close\_stop  | Sound name         | close\_stop=BD\_Close | Sound Wav name or sfb tag to play when door finishes closing |


## Elevator flags
Flags used for elevator entities

| **Required** | **Flag** | **Value(s)** | **Example** | **Description** |
| -------------| --- | --- | --- | --- |
| Required     | Type=Lift           |                    |  | Required for lift entities |
| Required     | BehaveType          | Elevator / Other   |  | Behavior type. Other is used for behaviors other than a normal lift |
| Optional     | Displace            | X, Y, Z            | Displace=0, 0, 14.5 | X Y Z distances to displace when moving |
| Optional     | Anim                | Animation MTX name | Anim=LiftAnim | Animation to play when elevator is activated |
| Optional     | AnimSpeed           | Float              | Animspeed=0.8 | Animation speed. Higher numbers = slower speeds |
| Optional     | MoveTime1           | Float              | MoveTime1=1 | Time to open in seconds |
| Optional     | MoveTime2           | Float              | MoveTime2=1 | Time to close in seconds. Defaults to same value as MoveTime1 |
| Optional     | AutoClose           | True \| False      | AutoClose=False | Whether lift should return to default position automatically |
| Optional     | AutoOpenFront       | True \| False      | AutoOpenFront=True | Auto open if bot enters radius near default position |
| Optional     | AutoOpenBack        | True \| False      | AutoOpenBack=True | Auto close if opened and bot enters radius near opened position |
| Optional     | AutoCloseDelay      | Time in seconds    | AutoCloseDelay=2 | Time in seconds before auto closing |
| Optional     | ActiveRadius        |                    | ActiveRadius=12 | Radius around default position. Activates when bot enters this radius |
| Optional     | ActiveRadius2       |                    | ActiveRadius2=12 | Radius around opened position. If in default position and bot enters radius, lift will open |
| Optional     | NoLiftBlockChecking | True \| False      | NoLiftBlockChecking=False |  |
| Optional     | lift\_start         | Sound name         | lift\_start=SOM\_MliIn | Sound Wav name or sfb tag to play when lift starts moving |
| Optional     | lift\_loop          | Sound name         | lift\_loop=SOM\_MliLp | Sound Wav name or sfb tag to play when lift is moving |
| Optional     | lift\_stop          | Sound name         | lift\_stop=SOM\_MliSp | Sound Wav name or sfb tag to play when lift stops moving |


## Destructible flags
Flags used for destructible entities

| **Required** | **Flag** | **Value(s)** | **Example** | **Description** |
| -------------| --- | --- | --- | --- |
| Required     | Type=Destruct |  |  | Required for destructible entities |
| Required     | Mesh | A, B | Mesh=Generator0, GenDestroyed | Ape mesh name to start as, ape mesh to become when destroyed. Optionally B leave blank |
| Optional     | Anim | Animation MTX name | anim=aom\_gen\_04 | Looping animation to play while object is alive |
| Optional     | AnimSpeed | Float | Animspeed=0.8 | Animation speed. Higher numbers = slower speeds. Use negative numbers to make the<br>Animation play in reverse. |
| Optional     | ArmorProfile |  | ArmorProfile=pred | Uses an entry in armor.csv as armor |
| Optional     | Health | 0.0 to 1.0 | Health=0.6 | Amount of health |
| Optional     | SoundAlive | Sound name | SoundAlive =L15\_generat | Sound Wav name or sfb tag to play while object is alive |
| Optional     | SoundDead | Sound name |  | Sound Wav name or sfb tag to play while object is destroyed |
| Optional     | Targetable | True \| False | Targetable=False | Whether the reticle turns red when targeting this entity |
| Optional     | ProjReact | HurtMe | ProjReact=HurtMe | Needed for destructible entities tied to scripted events |
| Optional     | Particle1 | Seconds, ParticleName, Bone | particle1=60,flameyjr2 | Time in seconds particle can play. Bone is what particle is attached to on dead mesh |
| Optional     | Particle2 | Seconds, ParticleName, Bone | particle2=20,flameyjr2,exp1 | Can have up to 4 particles on destructible entity. If optional bone name is specified, the<br>Particle will emit from that bone’s Z axis (Y axis in Max/Blender) If no bone is specified,<br>The particle will emit from the center of the object emitting upward |
| Optional     | Explosion | Explosion type, Bone | explosion=SuperManKiller,exp1 | Use one of the explosion types listed in xgrp\_lev.csv. Bone name is optional |


## Switch flags
Flags used for switch entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| Required                                                                                                                        | Type=switch |  |  | Required for switch entities |
| Required                                                                                                                        | TriggerEvent | True \| False | TriggerEvent=True | Enables triggering events when pressed |
| Optional                                                                                                                        | ReqChip | True \| False | ReqChip=True | Whether this switch requires a blue chip to be used |
| Optional                                                                                                                        | UseBy | Mil | UseBy=Mil | Whether this switch is restricted to Mils only (default is False) |
| Optional                                                                                                                        | DoorName |  | DoorName=door01 | Open this door in the world when switch is pressed |
| Optional                                                                                                                        | DoorAction | Open \| Close \| Lock \| Unlock \| Toggle | DoorAction=Open | Action for the door to perform when switch is pressed |


## Tripwire flags
Flags used for tripwire entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| Required                                                                                                                        | TripWireBuild | On \| Off | TripWireBuild=On | Required for tripwire entities |
| Required                                                                                                                        | TripWireEvent | Enter \| Exit \| Inside \| All \| None | TripWireEvent=Enter | When / how to trigger event. Can use multiple, separate with commas |
| Optional                                                                                                                        | TripWireWho | Player \| Enemy \| Friendly \| All | TripWireWho=Player | Who is allowed to trigger this tripwire. Can use multiple, separate with commas |
| Optional                                                                                                                        | TriggerMode | Once \| Multiple | TriggerMode=Once | Whether to trigger once, or every time tripwire is tripped. Default is multiple |
| Optional                                                                                                                        | TripWireFilterEntityName |  | TripWireFilterEntityName=Goff | Only the entity in the world with the specified name can activate this tripwire |
| Optional                                                                                                                        | TripWireKillMode | Volume \| Plane | TripWireKillMode=Volume | Turn tripwire into a kill volume |
| Optional                                                                                                                        | TripWireDamageBuild | 0 \| 1 | TripWireDamageBuild=1 | Required for Tripwires that do damage |
| Optional                                                                                                                        | TripWireDamageEnable | 0 \| 1 | TripWireDamageEnable=1 | Required for Tripwires that do damage |
| Optional                                                                                                                        | TripWreDamageNormIntensity | 0 to 1 | TripWreDamageNormIntensity=1 | Intensity of Tripwire damage |
| Optional                                                                                                                        | DamageProfile |  | DamageProfile=FlamerBurnL1 | Damage type from damage.csv |
| Optional                                                                                                                        | TripWireSpawnDeathEffects | True \| False | TripWireSpawnDeathEffects=False | Whether to spawn special affects when an entity is killed by this tripwire |
| Optional                                                                                                                        | TripWireIsAIZone | True \| False | TripWireIsAIZone=True | Controls the behavior of bots while they’re on patrol. MUST be parented to patrol path<br>Object in Max/Blender |
| Optional                                                                                                                        | AIZone\_Behavior | Wait \| Look \| Speed \| Anim | AIZone\_Behavior=Wait,Look | What behavior to use.<br>Wait = Bot will stop when entering zone.<br>Look = Bot will look at entity listed in Aizone\_ParamName (only allows one entity)<br>Speed = Speed the bot will change to inside zone. Speed returns to normal when exiting<br>Anim = BotTalk file to use when entering zone |
| Optional                                                                                                                        | AIZone\_Param1min |  |  |  |
| Optional                                                                                                                        | AIZone\_Param1Max |  |  |  |
| Optional                                                                                                                        | AIZone\_Param2 |  |  |  |
| Optional                                                                                                                        | AIZone\_ParamName |  |  |  |
| Optional                                                                                                                        | AIZone\_ParamTime |  |  |  |


## LiquidVolume flags
Flags used for liquid volume entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| Required                                                                                                                        | Type= | LiquidVolume |  | Required for liquid volume entities |
| Required                                                                                                                        | LiqType | Water \| Texture \| Molten \| Mercury | LiqType=Texture | Type of liquid |
| Optional                                                                                                                        | DropFreq | 0 to 200 | DropFreq=5.5 | Drops per second. Controls how active the liquid is |
| Optional                                                                                                                        | Opacity | 0 to 100 | Opacity=75 | Opacity of liquid texture |
| Optional                                                                                                                        | Texture1 | Texture Name | Texture1=tedm\_rok13 | Texture to use as liquid surface. If LiqType=Molten, texture is emissive |
| Optional                                                                                                                        | Texture2 | Texture Name | Texture2=tf\_lava | If LiqType=Molten, Texture2 is the crust of the lava |
| Optional                                                                                                                        | Tile | 0 to 128 | Tile=2 | How much the texture tiles (not the reflection texture) |
| Optional                                                                                                                        | CurrentX | Integer | CurrentX=0.2 | Current in X direction in feet per sec |
| Optional                                                                                                                        | CurrentY | Integer | CurrentY=0.5 | Current in Y direction in feet per sec |
| Optional                                                                                                                        | EnableRender | 0 \| 1 | EnableRender=0 | Whether to render the liquid |
| Optional                                                                                                                        | EnableSplashes | 0 \| 1 | EnableSplashes=0 | Whether to enable water splash effects |
| Optional                                                                                                                        | ColorRed | 0 to 255 | ColorRed=0 | RGB tint |
| Optional                                                                                                                        | ColorGreen | 0 to 255 | ColorGreen=128 | RGB tint |
| Optional                                                                                                                        | ColorBlue | 0 to 255 | ColorBlue=255 | RGB tint |
| Optional                                                                                                                        | PartImpact | Particle name | partimpact=e\_lava\_expl | Particle to emit for liquid impact |
| Optional                                                                                                                        | PartExplode | Particle name | PartExplode=e\_lava\_expl | Particle to emit for liquid explosion |


## AlarmNet flags
Flags used for AlarmNet entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| Required                                                                                                                        | XA\_AlarmNetName |  | XA\_AlarmNetName=alarm01 | Tag used for this AlarmNet network. All alarms/doors/switches that are a part of this AlarmNet network must use the same name |
| Required                                                                                                                        | XA\_IsVisible\_Spawn\_Pts | Yes \| No | XA\_IsVisible\_Spawn\_Pts=Yes | Bots will spawn regardless if the player can see them spawning |
| Required                                                                                                                        | XA\_IsHidden\_Spawn\_Pts | Yes \| No | XA\_IsHidden\_Spawn\_Pts=Yes | Bots will only spawn on points the player cannot see or if they’re not looking |
| Required                                                                                                                        | XA\_AlarmNet\_Ctrl | No\_Timer | XA\_AlarmNet\_Ctrl=no\_timer | Use if this AlarmNet is not controlled by a timer |
| Required                                                                                                                        | XA\_AlarmNet\_Max\_Living\_Autobots | 0 to 255 | XA\_AlarmNet\_Max\_Living\_Autob-<br>Ots=3 | Maximum amount of bots alive at any given time |
| Required                                                                                                                        | XA\_AlarmNet\_TotalBotsToAutoSpawn | 0 to 255 | XA\_AlarmNet\_TotalBotsToAutoSp-<br>Awn=6 | Maximum total number of bots spawned by this AlarmNet |
| Optional                                                                                                                        | XA\_AlarmNet\_Bot\_Group |  | XA\_AlarmNet\_Bot\_Group=Group\_<br>Mils | By default, AlarmNets will spawn ANY bots in the world with the prefix “xa\_autobot\_” in their Name as well as using the flag InWorld=False. Autobots can be respawned infinitely, but Only one instance of an autobot can exist at a time.<br><br>This flag will instead only use bots from a group. Grouped bots are named<br>“xa\_autobot\_group\_name\_” where “group\_name” is used by this flag |
| Optional                                                                                                                        | XA\_Spawn\_Delay\_Min | Seconds | XA\_Spawn\_Delay\_Min=2 | Minimum time in seconds before spawning a bot |
| Optional                                                                                                                        | XA\_Spawn\_Delay\_Max | Seconds | XA\_Spawn\_Delay\_Max=6 | Maximum time in seconds before spawning a bot |
| <h2>Switches</h2> | | | | |
| Required                                                                                                                        | XA\_AlarmNetName |  | XA\_AlarmNetName=alarm01 | Tag used by the AlarmNet network that this switch is a part of |
| Required                                                                                                                        | XA\_IsAlarmSwitch | Yes \| No | XA\_IsAlarmSwitch=Yes | Whether this entity is a switch used in an AlarmNet network |
| Optional                                                                                                                        | XA\_AlarmNet\_OnTime\_Min | Seconds | XA\_AlarmNet\_OnTime\_Min=20 | Minimum time alarm will be on |
| Optional                                                                                                                        | XA\_AlarmNet\_OnTime\_Max | Seconds | XA\_AlarmNet\_OnTime\_Max=30 | Maximum time alarm will be on |
| Required                                                                                                                        | XA\_Switch\_PressTime | Seconds | XA\_Switch\_PressTime=1 | How long in seconds bot must be pressing switch before alarm is turned on |
| Optional                                                                                                                        | XA\_AlarmNet\_Max\_Num\_TurnOns | 1 to 255 | XA\_AlarmNet\_Max\_Num\_TurnO-<br>Ns=1 | Maximum number of times the alarm can be turned on from this switch |
| Optional                                                                                                                        | UseBy | Mil | UseBy=Mil | AlarmNet switches are typically only used by Mils. This flag is optional |
| <h2>Doors</h2> | | | | |
| Required                                                                                                                        | XA\_AlarmNetName |  | XA\_AlarmNetName=alarm01 | Tag used by the AlarmNet network that this door is a part of |
| Required                                                                                                                        | XA\_IsAlarmDoor | Yes \| No | XA\_IsAlarmDoor=Yes | Whether this entity is a door used by an AlarmNet network |
| Optional                                                                                                                        | XA\_AlarmDoor\_Ctrl | Alarm\_On\_Opens<br>| Alarm\_On\_Shuts<br>| Alarm\_On\_Locks<br>| Alarm\_On\_Unlocks<br>| Alarm\_Off\_Opens<br>| Alarm\_Off\_Shuts<br>| Alarm\_Off\_Locks<br>| Alarm\_Off\_Unlocks | XA\_AlarmDoor\_Ctrl=Alarm\_On\_<br>Opens | How the AlarmNet affects this door |
| <h2>Mesh Entities</h2> | | | | |
| Optional                                                                                                                        | Mesh | A, B | Mesh=gom\_lightA1,gom\_lightA0 | Ape mesh this entity uses when AlarmNet is off, ape mesh when AlarmNet is activated |
| Optional                                                                                                                        | Anim | Animation MTX name | Anim=GOM\_lightA0 | Animation to use when AlarmNet is activated |
| Optional                                                                                                                        | AnimSpeed | Float | Animspeed=0.8 | Animation speed. Higher numbers = slower speeds |
| Required                                                                                                                        | XA\_IsAlarm | Yes \| No | XA\_IsAlarm=Yes | Whether this mesh entity is used in an AlarmNet network. When AlarmNet is activated, the Mesh changes from A to B specified by Mesh= and Sound\_Ambient\_Off\_ is set to On |
| Optional                                                                                                                        | XA\_AlarmNetName |  | XA\_AlarmNetName=alarm01 | Tag used by the AlarmNet network that this mesh is a part of |
| Optional                                                                                                                        | XA\_Alarm\_Notify\_Rad |  | XA\_Alarm\_Notify\_Rad=75 | Distance to alert bots of this alarm |
| Optional                                                                                                                        | Sound\_Ambient\_Tag | Sound name | Sound\_Ambient\_Tag=L07\_almext | Sound Wav name or sfb tag to play when the AlarmNet is activated |
| Optional                                                                                                                        | Sound\_Ambient\_Volume | 0.0 to 1.0 | Sound\_Ambient\_Volume=1 | Volume of the sound |
| Optional                                                                                                                        | Sound\_Ambient\_Radius |  | Sound\_Ambient\_Radius=100 | Distance the sound can be heard |
| Optional                                                                                                                        | Sound\_Ambient\_Off | 0 \| 1 | Sound\_Ambient\_Off=1 | If set to 1, sound will be off by default until AlarmNet is activated |


## Spawn System flags
Flags used for spawn system entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| Required                                                                                                                        | SS\_Net\_Name |  | SS\_Net\_Name=spawnnet01 | Tag used for this spawn system network. All components of this network must share this<br>Name |
| Optional                                                                                                                        | SS\_Net\_BotType | Swarmer | Vermin | SS\_Net\_BotType=Swarmer | Type of bot spawned by this spawn net |
| Optional                                                                                                                        | SS\_Net\_NumLiving\_Limit\_0 | 0 to 255 | SS\_Net\_NumLiving\_Limit\_0=50 | Maximum number of living bots spawned at this defcon level.<br>The defcon level can be set automatically by the game based on various factors, or forced To a specified defcon level by a tripwire.<br>Level 0 = No spawn point on the network is in the Active list, or visible |
| Optional                                                                                                                        | SS\_Net\_NumLiving\_Limit\_1 | 0 to 255 | SS\_Net\_NumLiving\_Limit\_1=50 | Maximum number of living bots spawned at this defcon level.<br>Level 1 = at least one spawn pt on the network is in the active list |
| Optional                                                                                                                        | SS\_Net\_NumLiving\_Limit\_2 | 0 to 255 | SS\_Net\_NumLiving\_Limit\_2=50 | Maximum number of living bots spawned at this defcon level<br>Level 2 = at least one spawn pt on the network is in the visible list |
| Optional                                                                                                                        | SS\_Net\_NumLiving\_Limit\_3 | 0 to 255 | SS\_Net\_NumLiving\_Limit\_3=50 | Maximum number of living bots spawned at this defcon level.<br>Level 3 = the player is in the same volume as at least one spawn pt |
| Optional                                                                                                                        | SS\_Net\_Bot\_Wander\_Dist |  | SS\_Net\_Bot\_Wander\_Dist=150 | Distance bots spawned by this net are allowed to wander from their spawn point |
| Optional                                                                                                                        | SS\_Net\_Bot\_Attack\_Dist |  | SS\_Net\_Bot\_Attack\_Dist=500 | Distance bots spawned by this net are allowed to go while attacking the player |
| Optional                                                                                                                        | SS\_Net\_Hidden\_Pt\_Spline | True \| False | SS\_Net\_Hidden\_Pt\_Spline=True | Bots can only be spawned on points that the player cannot see or if they’re not looking |
| Optional                                                                                                                        | SS\_Visible\_Pt\_Spline | True \| False | SS\_Visible\_Pt\_Spline=True | Bots can spawn even if their spawn points are visible to the player |
| Optional                                                                                                                        | SS\_Net\_Ctrl | No\_Auto\_Defcon | SS\_Net\_Ctrl=No\_Auto\_Defcon | Prevents game from changing defcon level automatically |
| Optional                                                                                                                        | SS\_NET\_DEFCONTRIPWIRE | Yes \| No | SS\_NET\_DEFCONTRIPWIRE=<br>Yes | Only used on tripwires. The defcon level of a spawn net will be forced to the specified<br>Number. SS\_Net\_Name MUST be used on the tripwire as well |
| Optional                                                                                                                        | SS\_DEFCONTRIPWIRE\_DEFCON | 0 to 3 | SS\_DEFCONTRIPWIRE\_DEFCO-<br>N=3 | Only used on tripwires. The defcon level the spawn net will be forced to. SS\_Net\_Name<br>MUST be used on the tripwire as well |


## Control Console flags
Flags used for Control Console entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| Required                                                                                                                        | Type=Console |  |  | Required for control console entities |
| Required                                                                                                                        | SocketCount=5 |  |  | Number of chip sockets. Do not change |
| Required                                                                                                                        | SocketName=chip |  |  | Name of socket. Do not change |
| Required                                                                                                                        | InsertedChipCount | 0 to 5 | InsertedChipCount=4 | Amount of chips already inserted in control console. Player must have chips to insert before Using this console |
| Required                                                                                                                        | ChipScale=.5 |  |  | Scale of inserted chip. Do not change |
| Required                                                                                                                        | EnemyName |  | EnemyName=xa\_autobot\_Goff | Name of bot controlled by this console. If the bot is created by a dispenser, the name must Have the prefix “xa\_autobot\_” otherwise bot can only be controlled once until it dies |
| Optional                                                                                                                        | Dispenser |  | Dispenser=disp01 | Name of dispenser entity this control console is linked to, if controlled bot is built by a<br>Dispenser every time console is used |
| Optional                                                                                                                        | UseOnce | True \| False | UseOnce=True | Prevent console from being used more than one time |

## Dispenser flags
Flags used for dispenser entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| Required                                                                                                                        | XA\_IsDispenser=True |  |  | Required for dispenser entities |
| Required                                                                                                                        | include=t\_dispense |  |  | Required for dispenser entities. Specifies CSV file with needed property flags |
| Required                                                                                                                        | name= |  | name=disp01 | Tags this entity with a name used by other entities or in scripting |
| Optional                                                                                                                        | XA\_Dispenser\_Bot1Name |  | XA\_Dispenser\_Bot1Name=xa\_<br>autobot\_Goff1 | The name of the bot entity spawned by this dispenser. Bot name MUST use prefix<br>“xa\_autobot\_” so it can be spawned again after death. |
| Optional                                                                                                                        | XA\_Dispenser\_Bot2Name |  | XA\_Dispenser\_Bot1Name=xa\_<br>autobot\_Goff2 | Additional bot(s) to spawn from this dispenser |
| Optional                                                                                                                        | XA\_Dispenser\_Bot3Name |  | XA\_Dispenser\_Bot1Name=xa\_<br>autobot\_Goff3 | Additional bot(s) to spawn from this dispenser |
| Optional                                                                                                                        | XA\_Dispenser\_Wait\_For\_Bot\_Death | True \| False |  | Wait for bot to die before spawning another |
| Optional                                                                                                                        | XA\_Dispenser\_Randomize\_Bots | True \| False |  | Randomize bots |
| Optional                                                                                                                        | XA\_Dispenser\_Bots\_Per\_Session | 0 to 255 |  | Number of bots spawned at once |
| Optional                                                                                                                        | XA\_Dispenser\_Secs\_Between\_Spawns | Seconds | XA\_Dispenser\_Secs\_Between\_S-<br>pawns=3 | Seconds between spawning bots |
| Optional                                                                                                                        | XA\_Dispenser\_Only\_Specified\_Bots | True \| False |  | Only spawn the bots specified |
| Optional                                                                                                                        | XA\_AlarmNetName |  | XA\_AlarmNetName=alarm01 | AlarmNet network this dispenser is linked to.<br>If this dispenser is for spawning a bot used by a control console, the value MUST be<br>Consolegrunt |

## Sound Entity flags
Flags used for sound entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| Sound emitter entities in the world must use prefix sound\_                                                                     |
| Optional                                                                                                                        | Sound\_Ambient\_Tag | Sound name | Sound\_Ambient\_Tag=L09\_Consol<br>2 | Sound Wav name or sfb tag to play |
| Optional                                                                                                                        | Sound\_Ambient\_Volume | 0.0 to 1.0 | Sound\_Ambient\_Volume=0.5 | Sound volume |
| Optional                                                                                                                        | Sound\_Ambient\_Radius |  | Sound\_Ambient\_Radius=15 | Radius sound can be heard |
| Optional                                                                                                                        | Sound\_Ambient\_Off | 0 \| 1 | Sound\_Ambient\_Off=1 | Whether the sound should start off |


## Particle flags
Flags used for sound entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| Particle emitter entities in the world must use prefix part\_                                                                   |
| Required                                                                                                                        | Type=particle |  |  | Required for particle entities |
| Required                                                                                                                        | PartDef | Particle fpr name | PartDef=steam | Name of the particle fpr file |
| Required                                                                                                                        | Intensity | 0 to 100 | Intensity=75 | Intensity of the particle emitter |
| Optional                                                                                                                        | DelaySpawn | True \| False | DelaySpawn=True | Whether particle emitter should start disabled |
| Optional                                                                                                                        | CanEliminateOnLesserSystems | 0 \| 1 | CanEliminateOnLesserSystems=1 |  |


## DetPack flags
Flags used for detpack receptacle entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| Required                                                                                                                        | Type=detpackdrop |  |  | Required for detpack receptacle entities |
| Required                                                                                                                        | Mesh=gwdmdetholo,gwdmdetpack |  |  | Meshes used. Does not need to be changed |
| Required                                                                                                                        | CountDown\_Time | Seconds | CountDown\_Time=6 | Countdown timer until explosion |
| Required                                                                                                                        | Activate\_Sound=swdmdetpset |  |  | Activation sound. Does not need to be changed |
| Required                                                                                                                        | Beep\_Sound=swdmdetblip |  |  | Beeping sound. Does not need to be changed |
| Optional                                                                                                                        | Master |  | Master=detpack1 | Sets another DetPack as this ones master |


## ZipLine flags
Flags used for zipline spline entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| Required                                                                                                                        | Type=zipline |  |  | Required for zipline entities |
| Required                                                                                                                        | Give | 0.0 to 1.0 | Give=0.02 | The amount the zipline should give |
| Required                                                                                                                        | Friction | 0.0 to 1.0 | Friction=0 | Amount of friction |
| Required                                                                                                                        | Visible | 0 \| 1 | Visible=1 | Whether the zipline is visible or invisible. 1 = visible |
| Required                                                                                                                        | Colorbias | R,G,B,A | Colorbias=200,200,200,255 | The color of the zipline |
| Required                                                                                                                        | Texture | Texture Name | Texture=tf\_zip02 | Texture to use for the zipline |
| Optional                                                                                                                        | TextureRepeat | 0.0 to 1.0 |  | Amount of times to repeat the texture per foot |
| Optional                                                                                                                        | Accel | 1.0 to 2.0 | Accel=1.3 | Amount of acceleration. 1.0 = none, 2.0 = max |


## Vehicle flags
Flags used for vehicle entities
Vehicles can use flags similar to bots such as AI\_Job=Patrol etc, useful for changing behavior of a bot when driving a vehicle

| **Required**             | **Flag** | **Value(s)** | **Example**       | **Description** |
| ---                      | ---      | ---          | ---               | ---           |
| <h2>Shared flags</h2>    |
| Optional                 | No\_Player\_Drive  | True \| False |                        | Prevents player from entering vehicle |
| Optional                 | No\_Entity\_Drive  | True \| False |                        | Prevents all entities from entering vehicle |
| Optional                 | DriverExit         | True \| False |                        | Whether driver is allowed to exit the vehicle |
| Optional                 | GunnerExit         | True \| False |                        | Whether the gunner is allowed to exit the vehicle (Rat only) |
| <h2>Rat</h2>             |                                
| Required                 | Type=vehiclerat    |               |                        | Required for Rat vehicle |
| Optional                 | DroidRatMesh       | 0 \| 1        | DroidRatMesh=1         | Whether to use the Droid version of the Rat |
| Optional                 | ZobbyGunning       | 0 \| 1        | ZobbyGunning=1         | If Zobby is using the turret |
| Optional                 | ArmorProfile       |               | ArmorProfile=PlayerRat | Uses entries from armor.csv. Use nohitpoint if vehicle recieves no damage |
| Optional                 | RatDeadFlip        | 0 \| 1        | RatDeadFlip=1          | Whether an enemy Rat should flip when it dies |
| <h2>Loader</h2>          |
| Required                 | Type=vehicleloader |               |                        | Required for Loader vehicle |
| Optional                 | Gun                | On \| Off     | Gun=Off                | Turns the Loaders gun on or off |
| <h2>Sentinel Tank</h2>   |
| Required                 | Type=vehicletank   |               |                        | Required for tank entities |
| <h2>Pillbox Turret</h2>  |                                                             
| Required                 | Type=SiteWeapon    |               |                        | Required for Pillbox turret vehicles |
| Required                 | WeaponType=Pillbox |               |                        | Specifies this as a Pillbox turret |
| <h2>AAGun</h2>           |                                                                      
| Required                 | Type=botAAgun      |               |                        | Required for AAGun vehicle |
| Required                 | AAGun\_Full360     | True \| False | AAGun\_Full360=False   | If the gun is allowed to rotate a full 360 |
| Optional                 | AAGun\_MaxHeeading | 0 to 100      | AAGun\_MaxHeeading=100 | Number of degrees to turn to the right |
| Optional                 | AAGun\_MaxPitch    | 0 to 100      | AAGun\_MaxPitch=100    | Number of degrees to aim down |
| Optional                 | AAGun\_Morter      | True \| False | AAGun\_Morter=True     | Whether the AAGun has a mortar launcher |

## Sentry flags
Flags used for sentry entities

| **Required**                                                                                                                    | **Flag** | **Value(s)** | **Example** | **Description** |
| ------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- | --- |
| <h2>Ground Sentry</h2> |
| Required                                                                                                                        | Type=SiteWeapon |  |  |  |
| Required                                                                                                                        | WeaponType=FloorSentry |  |  |  |
| Optional                                                                                                                        | PatrolMinYaw | \-360 to 0 | PatrolMinYaw=-45 |  |
| Optional                                                                                                                        | PatrolMaxYaw | 0 to 360 | PatrolMaxYaw=45 |  |
| Optional                                                                                                                        | SpotLight | On | Off | SpotLight=Off |  |
| Optional                                                                                                                        | SpotLightRange |  | SpotLightRange=250 |  |
| Optional                                                                                                                        | VisionDistance |  | VisionDistance=200 |  |
| Optional                                                                                                                        | RadarDistance |  | RadarDistance=200 |  |
| Optional                                                                                                                        | AttackDelayTime |  | AttackDelayTime=2 |  |
| <h2>Ceiling sentry</h2> |
| Required                                                                                                                        | Type=SiteWeapon |  |  |  |
| Required                                                                                                                        | WeaponType=wallsentry |  |  |  |