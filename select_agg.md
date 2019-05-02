Aggregation functions in SQL allows us to perform calculations on our table.
Some of the most commonly used functions are:
<table>
  <tr>
    <th>Function</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>COUNT</td>
    <td>Count number of rows</td>
  </tr>
  <tr>
    <td>MIN</td>
    <td>Find the minimum value of a column</td>
  </tr>
  <tr>
    <td>MAX</td>
    <td>Find the maximum value of a column</td>
  </tr>
  <tr>
    <td>SUM</td>
    <td>Sum all values in a column</td>
  </tr>
  <tr>
    <td>AVG</td>
    <td>Calculate the average value of a column</td>
  </tr>
</table>

Suppose we have a **solar_system** table:
<table>
  <tr>
    <th>position_from_sun</th>
    <th>planet</th>
    <th>mass_kg_e24</th>
    <th>num_of_moons</th>
    <th>diameter_km</th>
    <th>has_ring_system</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Mercury</td>
    <td align='right'>0.330</td>
    <td align='right'>0</td>
    <td align='right'>4879</td>
    <td>NO</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Venus</td>
    <td align='right'>4.870</td>
    <td align='right'>0</td>
    <td align='right'>12104</td>
    <td>NO</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Earth</td>
    <td align='right'>5.970</td>
    <td align='right'>1</td>
    <td align='right'>12756</td>
    <td>NO</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Mars</td>
    <td align='right'>0.642</td>
    <td align='right'>2</td>
    <td align='right'>6792</td>
    <td>NO</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Jupiter</td>
    <td align='right'>1898.000</td>
    <td align='right'>79</td>
    <td align='right'>142984</td>
    <td>YES</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Saturn</td>
    <td align='right'>568.000</td>
    <td align='right'>62</td>
    <td align='right'>120536</td>
    <td>YES</td>
  </tr>
  <tr>
    <td>7</td>
    <td>Uranus</td>
    <td align='right'>86.800</td>
    <td align='right'>27</td>
    <td align='right'>51118</td>
    <td>YES</td>
  </tr>
  <tr>
    <td>8</td>
    <td>Neptune</td>
    <td align='right'>102.000</td>
    <td align='right'>14</td>
    <td align='right'>49528</td>
    <td>YES</td>
  </tr>
  <tr>
    <td>9</td>
    <td>Pluto</td>
    <td align='right'>0.0146</td>
    <td align='right'>5</td>
    <td align='right'>2370</td>
    <td>NO</td>
  </tr>
</table>

### How many planets are in the solar system?
(get the number of rows in the table)
```sql
SELECT
    COUNT(*) AS row_count
FROM
    solar_system
```
Result:
<table>
   <tr>
      <th>row_count</th>
   </tr>
   <tr>
      <td align='right'>9</td>
   </tr>
</table>

### What is the weight of the lightest planet in the solar system?
(get the minimum weight of the planets)
```sql
SELECT
    MIN(mass_kg_e24) AS min_mass
FROM
    solar_system
```
Result:
<table>
   <tr>
      <th>min_mass</th>
   </tr>
   <tr>
      <td align='right'>0.0146</td>
   </tr>
</table>

### What is the weight of the heaviest planet in the solar system?
(get the maximum weight of the planets)
```sql
SELECT
    MAX(mass_kg_e24) AS max_mass
FROM
    solar_system
```
Result:
<table>
   <tr>
      <th>max_mass</th>
   </tr>
   <tr>
      <td align='right'>1898.000</td>
   </tr>
</table>

### What is the total weight of all planets in the solar system?
(sum all weights of the planets)
```sql
SELECT
    SUM(mass_kg_e24) AS total_mass
FROM
    solar_system
```
Result:
<table>
   <tr>
      <th>total_mass</th>
   </tr>
   <tr>
      <td align='right'>2665.8266</td>
   </tr>
</table>

### What is the average weight of all planets in the solar system?
(calculate the average weights of the planets)
```sql
SELECT
    AVG(mass_kg_e24) AS avg_mass
FROM
    solar_system
```
Result:
<table>
   <tr>
      <th>avg_mass</th>
   </tr>
   <tr>
      <td align='right'>296.203</td>
   </tr>
</table>

### Get the number planets in the solar system, their total weight, average diameter, nearest and furthest position from the sun
```sql
SELECT
    COUNT(*) AS planet_count
    , SUM(mass_kg_e24) AS total_weight
    , AVG(diameter_km) AS avg_diameter
    , MIN(position_from_sun) AS nearest_position_from_sun
    , MAX(position_from_sun) AS furthest_position_from_sun
FROM
    solar_system
```
Result:
<table>
   <tr>
     <th>planet_count</th>
     <th>total_weight</th>
     <th>avg_diameter</th>
     <th>nearest_position_from_sun</th>
     <th>furthest_position_from_sun</th>
   </tr>
   <tr>
     <td align='right'>9</td>
     <td align='right'>2665.8266</td>
     <td align='right'>44785.222</td>
     <td align='right'>1</td>
     <td align='right'>9</td>
   </tr>
</table>
