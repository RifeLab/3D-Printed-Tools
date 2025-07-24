# Dispenser

<figure class="image">
    <p>
        <img src="./img/penspring-version-side.png" width="500" />
        <img src="./img/penspring-version-front.png" width="400" />
    </p>
</figure>

Manual loading of beads and seeds into multi-well plates is labor-intensive, error-prone, and is a rate-limiting step in many protocols like DNA extractions and seed germination assays.
This highly-customizable model can be adapted to myriad applications and contains multiple components: main body, top plate, dropper plate, and gate.
The hole size of the top plate and dropper plate can be controlled independently, but the diameter of the top plate holes cannot exceed the diameter of the dropper plate holes.
The height of the top plate is adjustable up to 30mm allowing for multiple beads/seeds to be dispensed per hole or to accommodate non-spherical seeds.
The entire main body height can be adjusted to allow for even more height in the top plate, but modifying this value is not recommended since it can break the design.

You should only need to print the Main Body and Gate parts once.
A small brim around the main body will help with bed adhesion and minimize print warping.
The Dropper Plate does adjust some when Particle Diameter is changed, but in our experience printing a single dropper plate with `Particle_Diameter` = 5mm works for most bead sizes.

##  Customization
The location of the holes in the top and dropper plates can be adjusted using the `Well_Offset_X` and `Well_Offset_Y` parameters.
To ensure you are placing the holes appropriately we recommend using the [Opentrons Labware Library](https://labware.opentrons.com/) which contains measurements for these parameters for many commonly used plates.
`Well_Spacing` controls the width between the centerpoints of each well.
In nearly all purchaseable plates and tube racks the X and Y spacing are equal, but the measurements can be manually input to adjust as needed.

## Parameters

| Parameter Name | Suggested Value/Range | Notes |
| -------------- | --------------------- | ----- |
| `Well_Count` | 12, 24, 48, 96 | Well plate number of wells; Use 24 for the Opentrons Tube Rack |
| `Particle_Diameter` | 0.2-7.0mm | Use the seed sizing squares or calipers to determine this value; Precise measurement of the particles you plan to use |
| `Tolerance` | 0.4mm | Adjust for your specific printer's limitations |
| `BeadsPerWell` | 1-5 | Determines the thickness of the top plate based on your well diameter; Can be used to allow non-spherical seeds to fall through the holes in a vertical orientation based on seed length (`BeadsPerWell` = Seed Length/Seed Width; e.g. for 3x7mm wheat, `BeadsPerWell` = (7mm/3mm)) |
| `Well_Offset_X` | ( `Plate_Width_X` - ( ( `Well_Count_X` - 1 ) * `Well_Spacing` ) ) / 2 for centered; 16.19 mm for Opentrons Tube Rack | Can be manually input, see Adjusting Hole Location Note above |
| `Well_Offset_Y` | ( `Plate_Width_Y` - ( ( `Well_Count_Y` - 1 ) * `Well_Spacing` ) ) / 2 for centered; 6.725 mm for Opentrons Tube Rack | Can be manually input, see Adjusting Hole Location Note above |
| `Well_Spacing` | ( if(`Well_Count` == 12; 26; if(`Well_Count` == 24; 18; if(`Well_Count` == 48; 13; if(`Well_Count` == 96; 9; 1)))) ) * 1 mm | Automatically adjusts based on the `Well_Count` parameter; can be manually input, see Adjusting Hole Location Note above |
