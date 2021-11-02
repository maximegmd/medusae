Guide développeur
================

.. _node:

Créer un noeud
_____________

Pour créer un noeud il vous faudra installer `Geth <https://geth.ethereum.org/docs/install-and-build/installing-geth>`_.

Une fois Geth installé créez un dossier dans lequel vous créez un fichier ``genesis.json`` dont le contenu doit être:

.. code-block::
   :caption: genesis.json

   {
      "config": {
         "chainId": 46834,
         "homesteadBlock": 0,
         "eip150Block": 0,
         "eip155Block": 0,
         "eip158Block": 0,
         "byzantiumBlock": 0,
         "constantinopleBlock": 0,
         "petersburgBlock": 0,
         "ethash": {}
      },
      "difficulty": "1",
      "gasLimit": "8000000",
      "alloc": {
         "7Cd23BE1C507Da85ABF0B05c7A3C03e6d3d0233B":{ "balance" : "10000000000000000000000000" }
      }
   }

Dans ce même dossier executez la commande d'initialisation :

``geth init --datadir data genesis.json``

Il ne reste plus qu'à lancer le noeud :

``geth --datadir data --networkid 46834``

Il faudra probablement quelques minutes pour qu'il trouve d'autres noeuds et commence a se synchroniser.

.. _mining:

Minage
------

En supposant que vous avez effectué l'installation ci-dessus, il suffit d'ajouter quelques arguments à votre
noeud :

``geth --datadir data --networkid 46834 --mine --miner.etherbase=0xAAAAAAAAA``

Bien sur n'oubliez pas de remplacer ``0xAAAAAAAA`` par l'adresse publique qui recevra les récompenses.
