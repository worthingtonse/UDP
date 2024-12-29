# UDP
This is an attempt to make UDP work better by adding a few tweaks. 



<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-vswx{background-color:#fd6864;border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-uqo3{background-color:#efefef;text-align:center;vertical-align:top}
.tg .tg-cmwg{background-color:#ffccc9;text-align:center;vertical-align:top}
.tg .tg-yj5y{background-color:#efefef;border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-dvid{background-color:#efefef;border-color:inherit;font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-b3sw{background-color:#efefef;font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-dusx{background-color:#efefef;color:#3166ff;text-align:left;vertical-align:top}
.tg .tg-bolj{background-color:#ffccc9;border-color:inherit;text-align:center;vertical-align:top}
</style>
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
