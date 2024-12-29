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
    <td class="tg-uqo3" colspan="16">Source Port</td>
    <td class="tg-yj5y" colspan="16">Destination Port</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">4</td>
    <td class="tg-b3sw" colspan="2">8</td>
    <td class="tg-uqo3" colspan="16">Length</td>
    <td class="tg-vswx" colspan="16">Checksum</td>
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
    <td class="tg-cmwg" colspan="16">Port (Sending and Receiving)</td>
    <td class="tg-cmwg" colspan="8">Packet's Sequence Number</td>
    <td class="tg-cmwg" colspan="8">Totoal Packets in Sequence</td>
  </tr>
  <tr>
    <td class="tg-b3sw" colspan="2">4</td>
    <td class="tg-b3sw" colspan="2">32</td>
    <td class="tg-cmwg" colspan="16">Length</td>
    <td class="tg-cmwg" colspan="8">Sequence ID</td>
     <td class="tg-cmwg" colspan="8">Flags</td>
  </tr>
</tbody></table>
