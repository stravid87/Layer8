# layer8
Layer8 Proof of Concept

# Instructions to Run
## With Relative Paths
1) Open two VSCode Windows:  ReverseProxy folder and the ServiceProvider folder
2) `npm install` in ReverseProxy folder
3) run `$node RP_server.js`
4) `npm install` in the ServiceProvider folder
5) Run  `$node ServiceProvider.mjs`
6) Navigate to localhost:3000
7) Check out the poems anonymously
8) Login, choose an identity (at this time you will have to choose a randomly generated <adjective + animal> identity provided)
9) Use the crypto poems site to browse poems without exposing to the service provider who you really are, rather only your chosen identity. 
Note: User "ravster" is hard coded. You can, however, add your own user name / id.

## With Absolute Paths
If the browser is unable to locate the various resources, update the following paths to absolutes:
1) In ./RP_server.js, 
- Line 16, change the absolute path to the "views" folder
- Line 19, change the absolute path to the "public" folder
- Line 54, change the absolute path to the "CDN" folder
- Line 66, change the absolute path to the "CDN" folder

2) In ./ServiceProvider.mjs,
- Line 15, change the absolute path to the "views" folder

3) Run both servers.
4) Follow steps 5 - 9 above.
