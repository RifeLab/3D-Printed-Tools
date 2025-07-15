# Dispenser

You should only need to print the Main Body and Gate parts once. The Dropper Plate does adjust some when Particle Diameter is changed, but in our experience printing a single dropper plate with Particle_Diameter = 5mm works for most bead sizes. 

##  Adjusting Hole Locations
The location of the holes in the top and dropper plates can be adjusted using the **Well_Offset_X** and **Well_Offset_Y** parameters. To ensure you are placing the holes appropriately we highly recommend using the [Opentrons Labware Library](https://labware.opentrons.com/#/) which houses precise measurements of these parameters for many commonly used plate styles.

**Well_Spacing** controls the width between the centerpoints of each well. In nearly all purchaseable plates and tube racks the X and Y spacing are equal and the measurements for either may be input to this setting manually to adjust as needed. See the [Opentrons Labware Library](https://labware.opentrons.com/#/) for precise measurements of your labware.

| Parameter Name | Suggested Value/Range | Notes |
| -------------- | --------------------- | ----- |
| Well_Count | 12, 24, 48, 96 | Well plate number of wells; Use 24 for the Opentrons Tube Rack |
| Particle_Diameter | 0.2-7.0mm | Use the seed sizing squares or calipers to determine this value; Precise measurement of the particles you plan to use |
| Tolerance | 0.4mm | Adjust for your specific printer's limitations |
| BeadsPerWell | 1-5 | Determines the thickness of the top plate based on your well diameter; Can be used to allow non-spherical seeds to fall through the holes in a vertical orientation based on seed length (BeadsPerWell = Seed Length/Seed Width; e.g. for 3x7mm wheat, BeadsPerWell = (7mm/3mm)) |
| Well_Offset_X | ( Plate_Width_X - ( ( Well_Count_X - 1 ) * Well_Spacing ) ) / 2 for centered; 16.19 mm for Opentrons Tube Rack | Can be manually input, see Adjusting Hole Location Note above |
| Well_Offset_Y | ( Plate_Width_Y - ( ( Well_Count_Y - 1 ) * Well_Spacing ) ) / 2 for centered; 6.725 mm for Opentrons Tube Rack | Can be manually input, see Adjusting Hole Location Note above |
| Well_Spacing | ( if(Well_Count == 12; 26; if(Well_Count == 24; 18; if(Well_Count == 48; 13; if(Well_Count == 96; 9; 1)))) ) * 1 mm | Automatically adjusts based on the Well_Count parameter; can be manually input, see Adjusting Hole Location Note above |
