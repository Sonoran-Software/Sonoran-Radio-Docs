---
description: >-
  Let Sonoran Radio handle your pursuit location and direction callouts
  automatically!
---

# Pursuit Auto-Callouts

## Video Example

{% embed url="https://www.youtube.com/embed/G4OvM1hRfz8?si=F-JjEWZH4LEtm2jG" %}

## Enabling Auto-Callouts

Auto-callouts can be enabled using the in-game keybind (configurable in the `config.lua`) or by using the `/sonradtogglecallouts` command in-game

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

When your radio is powered, auto-callouts are enabled, and you're in a vehicle - Sonoran Radio will automatically callout street and direction changes over the radio. If configured, it will also callout average your speeds

Example: "Westbound, East Joshua Road, Speeds 85"

## Configuration

You can [change settings for auto-callouts (`Config.autoCallouts`) in the `config.lua` file](../../getting-started/installing-the-in-game-resource.md#updates).

### **Keybinds**

You can [edit the default keybinding under the `Config.keybinds['toggleAutoCallouts']` setting](../../getting-started/installing-the-in-game-resource.md#updates). By default, it is unset.

### **Speeds**

You can [configure the type of speed announced in the auto-callout using the `Config.autoCallouts.speedUnit` config option](../../getting-started/installing-the-in-game-resource.md#updates). By default, it is in miles per hour, but can be changed to kilometers per hours (`kmh`), or speed callouts can be disabled by setting it to `none`.

### **Languages**

Below is a complete list of all languages and words. If a street name or language needed is not listed below, [create a support ticket](https://support.sonoransoftware.com/) to have them added.

<details>

<summary>English</summary>

```
// Directions
Northbound
Eastbound
Southbound
Westbound

// GTAV Roads
Runway1
Plaice Pl
Voodoo Place
Buccaneer Way
Cavalry Blvd
El Burro Blvd
New Empire Way
Signal St
Abattoir Ave
Elysian Fields Fwy
Exceptionalists Way
Chupacabra St
Miriam Turner Overpass
Chum St
Hanger Way
South Shambles St
Orchardville Ave
Popular St
Greenwich Pkwy
Sustancia Rd
La Puerta Fwy
Dry Dock St
Autopia Pkwy
Dutch London St
Great Ocean Hwy
Davis Ave
El Rancho Blvd
Jamestown St
Carson Ave
Del Perro Fwy
Roy Lowenstein Blvd
Little Bighorn Ave
Grove St
Labor Pl
Covenant Ave
Red Desert Ave
Brouge Ave
Macdonald St
Bay City Ave
Tower Way
Mutiny Rd
Palomino Ave
Alta St
Innocence Blvd
Amarillo Way
South Arsenal St
Strawberry Ave
Amarillo Vista
Forum Dr
Goma St
Fudge Ln
Magellan Ave
Melanoma St
Rub St
Capital Blvd
Aguja St
Shank St
Vitus St
Tug St
Olympic Fwy
Crusade Rd
Tackle St
Olympic Fwy
Power St
Elgin Ave
South Rockford Dr
Cortes St
Calais Ave
Palomino Fwy
Invention Ct
Prosperity St
Adam's Apple Blvd
Conquistador St
Vespucci Blvd
Sinner St
Fantastic Pl
Imagination Ct
Del Perro Fwy
Supply St
Ginger St
Sandcastle Way
Lindsay Circus
Atlee St
San Andreas Ave
Decker St
Low Power St
Equality Way
Utopia Gardens
Peaceful St
Mirror Park Blvd
East Mirror Dr
Sinners Passage
West Mirror Drive
North Rockford Dr
Los Santos Freeway
Integrity Way
Mirror Pl
Marathon Ave
Nikola Pl
Las Lagunas Blvd
Swiss St
Movie Star Way
Nikola Ave
Boulevard Del Perro
Bay City Incline
Ineseno Road
Cougar Ave
Bridge St
Liberty St
Heritage Way
Playa Vista
Abe Milton Pkwy
Morningwood Blvd
Dorset Dr
San Vitus Blvd
Glory Way
Occupation Ave
West Eclipse Blvd
Dorset Pl
Meteor St
Rockford Dr
Hawick Ave
Boulevard Del Perro
Carcer Way
Portola Dr
South Boulevard Del Perro
Perth St
Mad Wayne Thunder Dr
Eastbourne Way
Tangerine St
York St
Spanish Ave
Alta Pl
Laguna Pl
Mad Wayne Thunder Dr
Vinewood Park Dr
Milton Rd
Sam Austin Dr
Vinewood Blvd
Kortz Dr
Caesars Place
Strangeways Dr
Americano Way
Picture Perfect Drive
South Mo Milton Dr
North Archer Ave
Edwood Way
Steele Way
Richman St
Clinton Ave
Hardy Way
Eclipse Blvd
Fenwell Pl
Dunstable Dr
Gentry Lane
Greenwich Pl
Dunstable Ln
North Conker Ave
Greenwich Way
Didion Dr
Ace Jones Dr
Cox Way
Cockingend Dr
Wild Oats Dr
Baytree Canyon Rd
Barbareno Rd
Hillcrest Ridge Access Rd
Senora Rd
Whispymound Dr
Marlowe Dr
North Sheldon Ave
Hangman Ave
Hillcrest Ave
Kimble Hill Dr
Lake Vinewood Dr
Normandy Dr
Banham Canyon Dr
Mt Haan Rd
Lake Vinewood Est
Mt Haan Dr
Mt Vinewood Dr
Tongva Dr
Galileo Park
East Galileo Ave
Senora Way
West Galileo Ave
Senora Fwy
Buen Vino Rd
Galileo Rd
Zancudo Grande Valley
Zancudo Barranca
Zancudo Rd
Route 68
Fort Zancudo Approach Rd
Joshua Rd
Chianski Passage
Route 68 Approach
Panorama Dr
Cat-Claw Ave
Smoke Tree Rd
Calafia Rd
Cholla Rd
Nowhere Rd
Marina Dr
East Joshua Road
Algonquin Blvd
Alhambra Dr
Cassidy Trail
Meringue Ln
Zancudo Ave
Lesbos Ln
Mountain View Dr
Lolita Ave
Cholla Springs Ave
Niland Ave
Armadillo Ave
North Calafia Way
Seaview Rd
Union Rd
Grapeseed Main St
Grapeseed Ave
Catfish View
Joad Ln
O'Neil Way
Procopio Promenade
Paleto Blvd
Duluoz Ave
Procopio Dr
Pyrite Ave
Cascabel Ave

// Speeds (MPH/KMH - Every 5)
Zero  
Five  
Ten  
Fifteen  
Twenty  
Twenty-five  
Thirty  
Thirty-five  
Forty  
Forty-five  
Fifty  
Fifty-five  
Sixty  
Sixty-five  
Seventy  
Seventy-five  
Eighty  
Eighty-five  
Ninety  
Ninety-five  
One hundred  
One hundred five  
One hundred ten  
One hundred fifteen  
One hundred twenty  
One hundred twenty-five  
One hundred thirty  
One hundred thirty-five  
One hundred forty  
One hundred forty-five  
One hundred fifty  
One hundred fifty-five  
One hundred sixty  
One hundred sixty-five  
One hundred seventy  
One hundred seventy-five  
One hundred eighty  
One hundred eighty-five  
One hundred ninety  
One hundred ninety-five  
Two hundred  
Two hundred five  
Two hundred ten  
Two hundred fifteen  
Two hundred twenty  
Two hundred twenty-five  
Two hundred thirty  
Two hundred thirty-five  
Two hundred forty  
Two hundred forty-five  
Two hundred fifty  
Two hundred fifty-five  
Two hundred sixty  
Two hundred sixty-five  
Two hundred seventy  
Two hundred seventy-five  
Two hundred eighty  
Two hundred eighty-five  
Two hundred ninety  
Two hundred ninety-five  
Three hundred
```

</details>
