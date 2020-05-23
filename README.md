# Maps in JavaScript.
```
<script type="text/javascript">
        var mymap = L.map('mapa').setView([54.444766, 18.554891], 17);
        L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', {
            maxZoom: 18,
            attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, ' +
                '<a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
                'Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
            id: 'mapbox.streets' }).addTo(mymap);

        L.marker([54.44505, 18.55491]).addTo(mymap)
            .bindPopup("<b>Uniwersytet Gdański</b><br />Wydział Ekonomiczny").openPopup();

        L.marker([54.44509, 18.55355]).addTo(mymap)
            .bindPopup("<b>Uniwersytet Gdański</b><br />Centrum dydaktyczne").openPopup();

        L.marker([54.4429, 18.55574]).addTo(mymap)
            .bindPopup("<b>Uniwersytet Gdański</b><br />Wydział Zarządzania").openPopup();
    
        L.circle([54.44484, 18.55722], 50, {
            color: 'red',
            fillColor: '#f03',
            fillOpacity: 0.5
        }).addTo(mymap).bindPopup("Policja");
    
        L.polygon([
            [54.44541, 18.55236],
            [54.44543, 18.55313],
            [54.44527,18.55318],
            [54.44522, 18.55240]
        ]).addTo(mymap).bindPopup("Parking dla studentów");

        L.polygon([
            [54.44518, 18.55241],
            [54.44523, 18.55321],
            [54.44505, 18.55323],
            [54.44496, 18.55252]
        ]).addTo(mymap).bindPopup("Parking dla pracowników");
    
        var popup = L.popup();
    
        function onMapClick(e) {
            popup
                .setLatLng(e.latlng)
                .setContent("You clicked the map at " + e.latlng.toString())
                .openOn(mymap);
        }
        mymap.on('click', onMapClick);
  </script>
```
