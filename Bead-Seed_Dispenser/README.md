# Dispenser

| Parameter Name | Suggested Value/Range | Notes |
| -------------- | --------------------- | ----- |
| Well_Count | 12, 24, 48, 96 | Well plate number of wells; Use 24 for the Opentrons Tube Rack |
| Particle_Diameter | 0.2-7.0mm | Use the seed sizing squares or calipers to determine this value; Precise measurement of the particles you plan to use |
| Tolerance | 0.4mm | Adjust for your specific printer's limitations |
| BeadsPerWell | 1-5 | Determines the thickness of the top plate based on your well diameter; Can be used to allow non-spherical seeds to fall through the holes in a vertical orientation based on seed length (BeadsPerWell = Seed Length/Seed Width; e.g. for 3x7mm wheat, BeadsPerWell = (7mm/3mm)) |
