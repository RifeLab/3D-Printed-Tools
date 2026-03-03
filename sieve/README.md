# Sieve

<img src="./img/sieves-model.png" width="500" />

Commercial sieves can be expensive and often lack the flexibility to specify pore size for specific needs, limiting their utility in seed sorting.
These printable sieves are stackable, robust to potential damage, and easy to customize.
The depth of the sieve tray was intentionally set to 3mm to maximize strength and minimize filament usage but can be adjusted as needed.

## Parameters

| Parameter Name | Suggested Value/Range | Notes |
| -------------- | --------------------- | ----- |
| `SieveHeight` | ( `HoleLength` + `HoleWidth` ) / 2 | If unsure what height, use "( `HoleLength` + `HoleWidth` ) / 2"|
| `TrayHeight` | ( `WallThickness` * 3 ) + ( ( `HoleLength` + `HoleWidth` ) / 2 ) | Automatically adjusts, but can be manually input (i.e. to increase strength) |
| `Length` | 10-360mm | Use to control the overal size of the sieve based on your printers max print volume; minimum of 10mm and maximum of 360mm inclusive |
| `HoleLength` | ≥1mm | minimum of 1mm, maximum equal to `Length` |
| `HoleWidth` | ≥1mm | can be adjusted for non-circular holes; minimum of 1mm, maximum equal to `Length` |


<figure class="image">
    <p>
        <img src="./img/cotton-seed-sorted.jpg" width="500" />
        <img src="./img/cotton-chaff.jpg" width="500" />
    </p>
</figure>