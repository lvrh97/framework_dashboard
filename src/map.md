---
theme: dashboard
title: Leaflet kaart
toc: false
---

# Kaart

Dit is om te oefenen met leaflet.

```js
import * as L from "npm:leaflet";
```

```js
function displayMap() {
  const div = display(document.createElement("div"));
  div.style = "height: 400px;";

  const map = L.map(div).setView([51.505, -0.09], 13);

  L.tileLayer("https://tile.openstreetmap.org/{z}/{x}/{y}.png", {
    attribution:
      '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a>',
  }).addTo(map);

  L.marker([51.5, -0.09])
    .addTo(map)
    .bindPopup("A nice popup<br> indicating a point of interest.")
    .openPopup();

  return div;
}
```

<div class="grid grid-cols-2">
<div class="card">
    <svg width="400" height="400" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
        <style>
          @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
          }
          .smiley {
            animation: rotate 2s linear infinite;
            transform-origin: center;
          }
        </style>
        <g class="smiley">
          <circle cx="100" cy="100" r="80" fill="yellow" stroke="black" stroke-width="5"/>
          <circle cx="75" cy="80" r="10" fill="black"/>
          <circle cx="125" cy="80" r="10" fill="black"/>
          <path d="M 70 130 Q 100 160, 130 130" stroke="black" stroke-width="5" fill="none"/>
        </g>
      </svg>

</div>

<div class="card">
    ${displayMap()}
</div>
</div>
