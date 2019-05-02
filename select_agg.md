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

### How many planets are in solar system?
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
