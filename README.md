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
- Line 16, change the path to an absolute for the "views" folder
- Line 19, change the path to an absolute for the "public" folder
- Line 54, change the path to an absolute for the "CDN" folder
- Line 66, change the path to an absolute for the "CDN" folder

2) In ./ServiceProvider.mjs,
- Line 15, change the path to an absolute for the "views" folder

3) Run both servers.
4) Follow steps 5 - 9 above.

## Notes on Understanding the Repo
1) Be aware, if there is a Type Script file in the directory, the associate JS file is compiled and unreadable. 
2) "crypto.subtle.<function>" is a standard library provided by the browser.
3) during sign up, the password is never transmitted to the proxy. ONLY the hashed and salted password is sent with the salt. Only the salt is stored along with the userID by the authentication service. During login, only the salted and hashed password is sent for verification, not the actuall password. 
4) The use of session storage in the client browser requires a proper implementation in WASM so that it is sandboxed.
5) The client browser never communicates with the service provider directly. 

### The following files map to the proposed architecture
"ReverseProxy/CDN/L8_module_v1.ts" is equivalent to the client side WASM module.
"ReverseProxy\public\login.mjs" is equivalent to the popup to "Login with Google", "Login with Facebook", etc.

## Glossary
- keyPairDH_spa: "key pair diffie hellman single page application"
- pubSJWK_m2spa: "public signing jason web key module to single page application"
- pubDHJWK_m2spa: "public diffie-Helman jason web key module to single page applicaiton"
- privSJWK_c: "private signing jason web key client" 
- pubSJWK_c: "publsic signing jason web key client"
- pubSJWK_s: "public signing jason web key server"
- keyPairS_c: "key pair signing client"
- plaintextDataObj_spa2m_str: "plain text data object single page application to module as a string"
- encryptedDataObj_spa2m_b64: "encrypted data object single page application to module as base 64 encoded"
- signature_b64_spa2m: "signature as base 64, single page application to module"
- signedFullJWT_spa2p: "signed fulld jason web token single page application to proxy"
- keyPairDH_spa: "key pair for Diffie-Helman of the single page appliction (elliptic curve)"
