# layer8
Layer8 Proof of Concept

# instructions to run
1) Open two VS. Code Windows:  ReverseProxy folder & ServiceProvider folder

2) `npm install` in ReverseProxy & update the following paths: 
- Line 16 ./RP_server.js, change the absolute path to the "views" folder
- Line 19 ./RP_server.js, change the absolute path to the "public" folder
- Line 54 ./RP_server.js, change the absolute path to the "CDN" folder
- Line 66 ./RP_server.js, change the absolute path to the "CDN" folder

3) run `$node RP_server.js`

4) `npm install` in the directory ServiceProvider
- Line 15 ./ServiceProvider.mjs, change the absolute path to the "views" folder

5) run  `$node ServiceProvider.mjs`

6) navigate to localhost 3000

7) check out the poems anonymously

8) login, choose and identity (at this time you will have to choose a randomly generated <adjective + animal> identity provided)

9) use the crypto poems site to browse poems without exposing to the service provider who you really are, rather only your chosen identity. 
