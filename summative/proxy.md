# Connecting to the game server via SOCKS5 proxy (OPTIONAL)

* **This content is not relevant to the coursework. Please ignore this if you can connect to the game server or you don't know what a proxy is.**
* It's always a good option to use the standalone (offline) version of the game if you couldn't connect to the game server.
* You should already have a shadowsocks (SOCKS5)  proxy and it should **already** be working. (If you are using VPN or TUN/TAP, you don't need to do anything)
* You need to know what port the system proxy is using.
  * For Windows users, open `Setting` -> `Network & internet` -> `Proxy`, the port is under `Port`
  * For Mac users, open `System Preferences` -> `Network` -> `Advanced` -> `Proxies` -> `Web Proxy (HTTP)`, the port is under `Web Proxy Server`

* Start ScotlandYard Remote game via proxy

  ```shell
  java -jar <path_to_the_game_jar_file_you_have_just_downloaded_from_above> --proxy=127.0.0.1:<the_port_you_got>
  ```

  e.g. for ClashX, the default port is 7890

  ```shell
  java -jar <path_to_the_game_jar_file_you_have_just_downloaded_from_above> --proxy=127.0.0.1:7890
  ```
