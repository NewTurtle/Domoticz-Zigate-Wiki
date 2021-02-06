# Comment construire/maintenir un bon réseau maillé Zigbee

Mesh Network = Réseau maillé = topologie réseau décentralisée - [Voir Wikipedia Reseau maillé](https://fr.wikipedia.org/wiki/Topologie_mesh)

## Comment construire votre réseau Zigbee (et le maintenir)

Si vous utilisez des objets Zigbee, vous devez comprendre que le réseau maillé Zigbee est la pierre angulaire de votre domotique.
Ce réseau maillé permet aux objets Zigbee de communiquer entre eux et avec la passerelle Zigbee (ZiGate). Bien que les objets construisent automatiquement le maillage, cette opération n'est pas instantannée. Il est donc nécessaire d'attendre que le réseau s'élabore avant de commencer à automatiser vos objets.
En automatisant trop précipitamment, vous risquez, notamment, d'etre confronté à des pertes de objets.

**A noter :** La constitution de votre maillage Zigbee peut prendre plusieurs jours afin de trouvrer les routes optimales, cependant en stoppant le module central (ZiGate) durant 20 minutes, vous relancez le process de re-découverte du maillage réseau.

Pour disposer, tous les objets Zigbee doivent etre accessibles de la ZiGate. En ajoutant les objets à proximité de votre ZiGate (routeur principal), puis en le déplaçant à l'emplacement final conduit souvent à une perte du objet au sein du réseau. Il est donc recommandé de toujours appairer vos objets depuis leur emplacement final.

Même si votre Zigate supporte jusqu'à 40 objets connectés directement, un ou plusieurs objets router contribueront à maintenir une bonne communication entre les objets et la Zigate. Considerons votre environnement! La distance avec les objets les plus éloignés, les obstructions du signal (murs épais, zones metalliques, etc...) et la performance intrinsèque du objet vont déterminer le nombre de objet router nécessaire pour un bon maillage.
Un router Zigbee est un objet alimenté sur le secteur, généralement des prises (plug) ou interrupteurs (wall switches). Par conséquent les objets Zigbee alimentés sur baterie ne permettent pas de repeter le signal Zigbee, ils sont designés en tant que objets terminaux (end devices) à contrario des routeurs qui eux repetent le signal Zigbee.

Voici quelques procédures à suivre lors de la découverte des objets Zigbee pour constituer un réseau solide... La patience reste la clef du succès.

### Jusqu'à 40 objets alimentés sur batterie
1. Faites l'appairage de vos objets l'un après l'autre; attendez la fin de l'appairage de l' objet pour tenter l'appairage du suivant. Voir les intructions d'appairage propres à votre materiel pour plus de détail.
2. La distance entre le objet et la ZiGate mais également les matériaux de construction (murs), les objets métalliques et les performances du composant vont déterminer l'éloignement maximum du objet sans perte de connexion avec la Zigate

### Au delà de 32 objets
La ZiGate supporte jusqu'à 40 objets en connexion directe. Vous pouvez étendre cette limitations en utilisant les objets alimentés sur le secteur disposant de la fonction répéteur/routeur; on appelle ces objets, des objets routeurs.
Les objets connectés alimentés sur batterie n'écoutent pas le réseau Zigbee et de ce fait ne peuvent exercer une fonction de routeur; on appelle aussi ces objets des objets terminaux.
Les objets terminaux ne communiquent qu'avec un parent qui peut être soit la ZiGate elle même ou bien un objet routeur. Les objets routeurs, quant à eux, communiquent avec la ZiGate et les objets terminaux.
Bien entendu, votre environnement, la distance entre la ZiGate et le plus éloigné des objets, le nombre d'objets routeurs intégrés dans votre réseau va déterminer le nombre maximun d'objets que pourra contenir votre réseau ZigBee sous réserve d'avoir suffisament d'objets routeur correctement répartis en distance avec la ZiGate mais également entre eux.


### La construction du réseau
Appairer vos objets routeur l'un après l'autre; même si cela peut vous paraitre long (journée), stabilisez votre réseau entre chaque appairage. Une fois tous les objets routeur appairés et le réseau Zigbee stabilisé, vous pouvez commencer l'appairage des objets terminaux

Pair your Zigbee repeating devices one at a time. See Discovering your Devices for detail instructions on adding devices to your Hubitat Elevation™ hub.
Now pair your Zigbee battery powered devices one at a time, in their intended location, within range of either the hub or a Zigbee router. See Discovering your Devices for detail instructions on adding devices to your Hubitat Elevation™ hub.
When all of your devices have been added, power down your hub for 20 minutes. After booting Hubitat Elevation™ again, your Zigbee mesh will automatically choose the best route for your devices within approximately a 24 hour period. Alternatively, you can wait several days for the Zigbee mesh to establish the best path for communication between the hub and your devices by itself.
How Zigbee Repeaters (Routers) Work
A Zigbee repeater or router, is a messenger that relays information, until the messages between end devices and the hub have reached one another.

Zigbee repeaters may be any device that will always powered by mains voltages (but be cautious with Zigbee bulbs that may repeat; see Tips for designing your Zigbee mesh). A Zigbee outlet is an example of a repeater acting as a relay point for devices that are too far from the hub to reliably send and receive signals. ZigBee and Z-Wave are two different wireless protocols, therefore a mains powered ZigBee device can only function as a repeater for other ZigBee devices, and Z-Wave devices only act as repeaters for other Z-Wave devices.

Devices too far from the hub or obstructions will result in dropped connections from weak Zigbee signals.


Ceci est une traduction francaise de cette page [How to Build a Solid Zigbee Mesh](https://docs.hubitat.com/index.php?title=How_to_Build_a_Solid_Zigbee_Mesh)
