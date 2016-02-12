Overview
===============
**osrm-api-client** is a an open source PHP implementation of the 
[OSRM Server API](https://github.com/DennisOSRM/Project-OSRM/wiki/Server-api).

###Features
- viaroute (computation of the shortest path on the road network between two coordinates)
- nearest (nearest point on any street segment of the road network)

###Installation
To add <tt>osrm-api-client</tt> as a locally per-project dependency you can insert the
following code to your composer.json file:

    {
        "require": {
            "bryan072/osrm-api-client": "dev-master",
            "jens-na/osrm-api-client": "dev-master"
        },
        "repositories": [
            {
               "type": "vcs",
               "url": "https://github.com/bryan072/osrm-api-client"
            }
        ]
    }

###API Usage Policy
If you are using the server **router.project-osrm.org** with this API client, please read the 
[API Usage Policy](https://github.com/DennisOSRM/Project-OSRM/wiki/API%20Usage%20Policy) of Project-OSRM.
Usage 
=====

###viaroute
    $client = new Osrm\OsrmClient('http://server:5000');
    $from = new Osrm\Coordinate(50.142739,9.122257);
    $to = new Osrm\Coordinate(50.139631,9.107151);
    $route = $client->getRoute($from, $to);

###nearest

    $client = new Osrm\OsrmClient('http://server:5000');
    $mylocation = new Osrm\Coordinate(9.305283, 50.344735);
    $nearestStreet = $client->getNearestStreetPoint($mylocation);

References
==========
- [OSRM API Client] (https://github.com/jens-na/osrm-api-client)
- [OSRM Server API](https://github.com/DennisOSRM/Project-OSRM/wiki/Server-api)
- [OSRM Json Output](https://github.com/DennisOSRM/Project-OSRM/wiki/Output-json)
- [OSRM Turn instructions](https://github.com/DennisOSRM/Project-OSRM/blob/master/DataStructures/TurnInstructions.h)
- [OSRM API Usage Policy](https://github.com/DennisOSRM/Project-OSRM/wiki/API%20Usage%20Policy)

License and Copyright
=====================
Licensed under the GNU General Public License 3.

(c) Jens Nazarenus, 2013 | Bryan Steyns, 2016
