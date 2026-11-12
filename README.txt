Nesto Care policy website (static, no build step)

1. Replace the placeholders everywhere. From this folder in PowerShell run (edit the four values first):
   $m=@{'YOUR_SUPPORT_EMAIL'='you@example.com';'YOUR_PHONE'='+91 00000 00000';'YOUR_BUSINESS_NAME'='Your business name';'YOUR_BUSINESS_ADDRESS'='Town, Nagaon, Assam 782001';'YOUR_NAME'='Your full name'}; Get-ChildItem *.html | ForEach-Object { $t=Get-Content $_ -Raw; foreach($k in $m.Keys){$t=$t.Replace($k,$m[$k])}; Set-Content $_ $t -NoNewline }
2. Push this folder to a new GitHub repo and import it in Vercel. Framework preset: Other. No build command.
3. Pages after hosting: /privacy-policy  /terms-and-conditions  /refund-and-cancellation-policy  /account-deletion  /contact
