#### The current results of this code can be seen in [tipa.li](http://tipa.li/)

#### How this works (so far)


The main challenge is to get the geolocations for all the Tipat Halav stations. The list of stations themselves can be scraped - or, for now, I used milkdrop.json file compiled by @SharonMoravi.

The goal is to get from [milkdrop.json](https://github.com/niryariv/tiptipa/blob/master/data/milkdrop.json) to something that looks like [stations.geojson](https://github.com/niryariv/tiptipa/blob/master/data/stations_demo.geojson).

[geoencode.py](https://github.com/niryariv/tiptipa/blob/master/geoencode.py) tries to acheive this by taking the address/city info and feeding it to ~~[Nominatim](http://nominatim.openstreetmap.org/) - an Open Street Map project~~ Google Maps API (turns out to be faster & more reliable than Nominatim) for translating addresses to geolocations.

Google's Geoencoder returns the lon/lat which are then entered into the geojson file, with the rest of the station data entered to the features dictionary of each point. 

As it turns out, 176 out of 989 addresses in milkdrop.json aren't recognized by the geoencoder. In that case, we store them in the geojson file with ```error:True``` so we can later manually fix them later on.

###Contributing

**YOU can help!:** Help us verify, clean and optimize the information. 

We use a google fusion [table](https://www.google.com/fusiontables/DataSource?docid=1zpsJz8BGY5uSWbQC6CLgXQka1vhHyHqtrUMHas8) with the data.
ping us in the issues section or by email to grant an editing permission.

Data from the fusion table would be loaded into the app

###אתם יכולים לעזור!

עזרו לנו למטב את הgoogle fusion table עם הנתונים.
כנסו ל [טבלה](https://www.google.com/fusiontables/DataSource?docid=1zpsJz8BGY5uSWbQC6CLgXQka1vhHyHqtrUMHas8) בשביל להבין באיזה נתונים מדובר וכו'
שמסיימים דחפו חזרה לGithub repo  
