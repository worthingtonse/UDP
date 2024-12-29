# UDP
This is an attempt to make UDP work better by adding a few tweaks. 

# Existing UDP
<table class="tg"><thead>
  <tr>
    <th class="tg-b3sw" colspan="2">Offset</th>
    <th class="tg-dusx" colspan="2">Octet</th>
    <th class="tg-b3sw" colspan="8">0</th>
    <th class="tg-dvid" colspan="8">1</th>
    <th class="tg-dvid" colspan="8">2</th>
    <th class="tg-dvid" colspan="8">3</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-b3sw" colspan="2">Octet</td>
    <td class="tg-dusx" colspan="2">Bit</td>
    <td class="tg-b3sw">0</td>
    <td class="tg-b3sw">1</td>
    <td class="tg-b3sw">2</td>
    <td class="tg-dvid">3</td>
    <td class="tg-b3sw">4</td>
    <td class="tg-b3sw">5</td>
    <td class="tg-b3sw">6</td>
    <td class="tg-b3sw">7</td>
    <td class="tg-dvid">0</td>
    <td class="tg-dvid">1</td>
    <td class="tg-dvid">2</td>
    <td class="tg-dvid">3</td>
    <td class="tg-dvid">4</td>
    <td class="tg-dvid">5</td>
    <td class="tg-dvid">6</td>
    <td class="tg-dvid">7</td>
    <td class="tg-dvid">0</td>
    <td class="tg-dvid">1</td>
    <td class="tg-dvid">2</td>
    <td class="tg-dvid">3</td>
    <td class="tg-dvid">4</td>
    <td class="tg-dvid">5</td>
    <td class="tg-dvid">6</td>
    <td class="tg-dvid">7</td>
    <td class="tg-dvid">0</td>
    <td class="tg-dvid">1</td>
    <td class="tg-dvid">2</td>
    <td class="tg-dvid">3</td>
    <td class="tg-dvid">4</td>
    <td class="tg-dvid">5</td>
    <td class="tg-dvid">6</td>
    <td class="tg-dvid">7</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">0</td>
    <td class="tg-b3sw" colspan="2">0</td>
    <td class="tg-cmwg" colspan="32">Source Address</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">4</td>
    <td class="tg-b3sw" colspan="2">32</td>
    <td class="tg-cmwg" colspan="32">Destination Address</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">8</td>
    <td class="tg-b3sw" colspan="2">64</td>
    <td class="tg-cmwg" colspan="8">Zeroes</td>
    <td class="tg-bolj" colspan="8">Protocol</td>
    <td class="tg-bolj" colspan="16">UDP Length</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">12</td>
    <td class="tg-b3sw" colspan="2">96</td>
    <td class="tg-uqo3" colspan="16">Source Port</td>
    <td class="tg-yj5y" colspan="16">Destination Port</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">16</td>
    <td class="tg-b3sw" colspan="2">128</td>
    <td class="tg-uqo3" colspan="16">Length</td>
    <td class="tg-vswx" colspan="16">Checksum</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">20</td>
    <td class="tg-b3sw" colspan="2">160</td>
    <td class="tg-uqo3" colspan="32" rowspan="3">Data</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">24</td>
    <td class="tg-b3sw" colspan="2">192</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">...</td>
    <td class="tg-b3sw" colspan="2">...</td>
  </tr>
</tbody></table>

# New UDP

<table class="tg"><thead>
  <tr>
    <th class="tg-b3sw" colspan="2">Offset</th>
    <th class="tg-dusx" colspan="2">Octet</th>
    <th class="tg-b3sw" colspan="8">0</th>
    <th class="tg-dvid" colspan="8">1</th>
    <th class="tg-dvid" colspan="8">2</th>
    <th class="tg-dvid" colspan="8">3</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-b3sw" colspan="2">Octet</td>
    <td class="tg-dusx" colspan="2">Bit</td>
    <td class="tg-b3sw">0</td>
    <td class="tg-b3sw">1</td>
    <td class="tg-b3sw">2</td>
    <td class="tg-dvid">3</td>
    <td class="tg-b3sw">4</td>
    <td class="tg-b3sw">5</td>
    <td class="tg-b3sw">6</td>
    <td class="tg-b3sw">7</td>
    <td class="tg-dvid">0</td>
    <td class="tg-dvid">1</td>
    <td class="tg-dvid">2</td>
    <td class="tg-dvid">3</td>
    <td class="tg-dvid">4</td>
    <td class="tg-dvid">5</td>
    <td class="tg-dvid">6</td>
    <td class="tg-dvid">7</td>
    <td class="tg-dvid">0</td>
    <td class="tg-dvid">1</td>
    <td class="tg-dvid">2</td>
    <td class="tg-dvid">3</td>
    <td class="tg-dvid">4</td>
    <td class="tg-dvid">5</td>
    <td class="tg-dvid">6</td>
    <td class="tg-dvid">7</td>
    <td class="tg-dvid">0</td>
    <td class="tg-dvid">1</td>
    <td class="tg-dvid">2</td>
    <td class="tg-dvid">3</td>
    <td class="tg-dvid">4</td>
    <td class="tg-dvid">5</td>
    <td class="tg-dvid">6</td>
    <td class="tg-dvid">7</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">0</td>
    <td class="tg-b3sw" colspan="2">0</td>
    <td class="tg-cmwg" colspan="16">Source Port</td>
    <td class="tg-cmwg" colspan="16">Destination Port</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">4</td>
    <td class="tg-b3sw" colspan="2">32</td>
    <td class="tg-cmwg" colspan="16">Length</td>
    <td class="tg-cmwg" colspan="16">CheckSum</td>
  </tr>
</tbody></table>
