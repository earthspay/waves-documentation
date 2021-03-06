# Export and import of the blockchain

**Note:** This functionality available since version 0.8.


## Export existing blocks to a binary file 

**Note:** You have to stop the node before starting export of blocks.


To export existing blockchain to the binary file run following command. Export is quite a fast operation, but resulting binary file could additionally take up to 1/3 of`data`folder size on disk.

On Windows:

```
java -cp earths-all-<version>.jar com.earthspay.Exporter [configuration-file-name] [output-file-name] [height]
```

On Linux:

```
sudo -u earths[-testnet] java -cp '/usr/share/earths[-testnet]/lib/*' -Dearths.directory=/var/lib/earths[-testnet] com.earthspay.Exporter /etc/earths[-testnet]/earths.conf [output-file-name] [height]
```

By default, the Testnet configuration file will be used.

If parameter`height`was not given all blocks will be exported. In another case, only blocs up to the height will be exported to the output file.

The output file name parameter is optional, name 'blockchain' is used by default. As a result, a file named '&lt;output-file-name&gt;-&lt;height&gt;' will be created in the current folder.

## Import blocks from the binary file 

| Warning | This operation will completely overwrite existing node data. Do not forget to make a backup of your node’s`data`folder. |


To import the blockchain and fully rebuild the state run the following command.

On Windows:

```
java -cp earths-all-<version>.jar com.earthspay.Importer [configuration-file-name] [binary-file-name]
```

On Linux:

```
sudo -u earths[-testnet] java -cp '/usr/share/earths[-testnet]/lib/*' -Dearths.directory=/var/lib/earths[-testnet] com.earthspay.Importer /etc/earths[-testnet]/earths.conf [binary-file-name]
```

Import is a heavy operation and could take few hours to complete.

## Downloading exported blockchain

You can download recent exported blockchain here: 
* TestNet: http://blockchain.testnet.earthsnodes.earths.ga/
* MainNet: http://blockchain.earthsnodes.earths.ga/


