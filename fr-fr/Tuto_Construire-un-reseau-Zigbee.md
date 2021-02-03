# Comment construire/maintenir un bon réseau maillé Zigbee

Mesh Network = Réseau maillé = topologie réseau décentralisée - [Voir Wikipedia Reseau maillé](https://fr.wikipedia.org/wiki/Topologie_mesh)

## Comment construire votre réseau Zigbee (et le maintenir)

Si vous utilisez des dispositifs Zigbee, vous devez comprendre que le réseau maillé Zigbee est la pierre angulaire de votre domotique.
Ce réseau maillé permet aux dispositifs Zigbee de communiquer entre eux et avec la passerelle Zigbee (ZiGate). Bien que les dispositifs construisent automatiquement le maillage, cette opération n'est pas instantannée. Il est donc nécessaire d'attendre que le réseau s'élabore avant de commencer à automatiser vos dispositifs.
En automatisant trop précipitamment, vous risquez, notamment, d'etre confronté à des pertes de dispositifs.

**A noter :** La constitution de votre maillage Zigbee peut prendre plusieurs jours afin de trouvrer les routes optimales, cependant en stoppant le module central (ZiGate) durant 20 minutes, vous relancez le process de re-découverte du maillage réseau.

Pour disposer, tous les dispositifs Zigbee doivent etre accessibles de la ZiGate. En ajoutant les dispositifs à proximité de votre ZiGate (routeur principal), puis en le déplaçant à l'emplacement final conduit souvent à une perte du dispositif au sein du réseau. Il est donc recommandé de toujours appairer vos dispositifs depuis leur emplacement final.

Même si votre Zigate supporte jusqu'à XXXX dispositifs connectés directement, un ou plusieurs dispositifs router contribueront à maintenirunbe bonne communication entre les dispositifs et la Zigate. Considerons votre environnement! La distance avec les dispositifs les plus éloignés, les obstructions du signal (murs épais, zones metalliques, etc...) et la performance intrinsèque du dispositif vont déterminer le nombre de dispositif router nécessaire pour un bon maillage.
Un router Zigbee est un dispositif alimenté sur le secteur, généralement des prises (plug) ou interrupteurs (wall switches). Par conséquent les dispositifs Zigbee alimentés sur baterie ne permettent pas de repeter le signal Zigbee, ils sont designés en tant que dispositifs terminaux (end devices) à contrario des routeurs qui eux repetent le signal Zigbee.

Voici quelques procédures à suivre lors de la découverte des dispositifs Zigbee pour constituer un réseau solide... La patience reste la clef du succès.

### Jusqu'à 32 dispositifs alimentés sur batterie
1. Faites l'appairage de vos dispositifs l'un après l'autre; attendez la fin de l'appairage du dispositif pour tenter l'appairage du suivant. Voir les intructions d'appairage propres à votre materiel et au dispositif pour plus de détail.
2. La distance entre le dispositif et la Zigate, les matériaux de construction (murs), les objets métalliques et les performances du composant vont déterminer l'eloignement maximum du dispositif sans perte de connexion avec la Zigate

### Au dela de 32 dispositifs

32 or more Zigbee devices
Hubitat Elevation™ can support up to 32 end devices (devices connected directly to the hub without the help of a repeating device). Beyond 32 battery powered or non-repeating end devices, you must add mains powered repeating devices. A Zigbee repeating device is one that is plugged into an outlet or powered by mains voltages. Battery powered Zigbee devices do not repeat signals. End devices only communicate with a parent device, which could be the hub or it could be a repeater. Zigbee repeating devices (Routers) communicate with both the hub and End devices. Your environment, distance to the furthest device from the hub, and the range of the Zigbee repeating devices will determine the correct number of repeating devices required. Unlike Z-Wave, there is no limit to the number of Zigbee devices that can be added to your network, as long as there are an adequate number of repeating devices and they are properly distanced from each other.

Pair your Zigbee repeating devices one at a time. See Discovering your Devices for detail instructions on adding devices to your Hubitat Elevation™ hub.
Now pair your Zigbee battery powered devices one at a time, in their intended location, within range of either the hub or a Zigbee router. See Discovering your Devices for detail instructions on adding devices to your Hubitat Elevation™ hub.
When all of your devices have been added, power down your hub for 20 minutes. After booting Hubitat Elevation™ again, your Zigbee mesh will automatically choose the best route for your devices within approximately a 24 hour period. Alternatively, you can wait several days for the Zigbee mesh to establish the best path for communication between the hub and your devices by itself.
How Zigbee Repeaters (Routers) Work
A Zigbee repeater or router, is a messenger that relays information, until the messages between end devices and the hub have reached one another.

Zigbee repeaters may be any device that will always powered by mains voltages (but be cautious with Zigbee bulbs that may repeat; see Tips for designing your Zigbee mesh). A Zigbee outlet is an example of a repeater acting as a relay point for devices that are too far from the hub to reliably send and receive signals. ZigBee and Z-Wave are two different wireless protocols, therefore a mains powered ZigBee device can only function as a repeater for other ZigBee devices, and Z-Wave devices only act as repeaters for other Z-Wave devices.

Devices too far from the hub or obstructions will result in dropped connections from weak Zigbee signals.


Ceci est une traduction francaise de cette page [How to Build a Solid Zigbee Mesh](https://docs.hubitat.com/index.php?title=How_to_Build_a_Solid_Zigbee_Mesh)
