<p align="center">
  <img src="../img/Logo.png" alt="How to deal with Passwords">
  <br>
  <h1>How to Deal with Passwords for Developers</h1>
</p>

+ Never store the password itself.
+ Force users to choose a longer password, not a difficult to remember password -> [xkcd.com/936/](http://xkcd.com/936/)
+ Ask your users to change their password according to importance of their account / your site on a yearly/quarterly/monthly basis.
+ Use HTTPS at least for Login/Signup/Reset and related pages.
+ Never send plain password of users to their email.
+ Double check `chmod``of your files and folders.
+ Your partner(designer) will use the same validation as you, but with javascript. You should run the server-side validation, too. You [can't trust](https://en.wikipedia.org/wiki/User_agent#User_agent_spoofing) user-agent.
+ Use [strong](../Everybody/README.md) passwords for accessing the developping land! After all you are an important person.
+ Use hash functions, not encryption functions. They aren't safe.
    + `bcrypt` -> [How to safely store a password](http://codahale.com/how-to-safely-store-a-password/) / Also read [this](http://security.stackexchange.com/questions/4781/do-any-security-experts-recommend-bcrypt-for-password-storage)
    + `scrypt`
+ Create delays:
    + Add punishment! If a user can't login after trying 20 times(It depends on importance of your system), punish them for about an hour or like that...
    + Force a delay for each login, like 5 seconds. Users won't feel it, but an Attacker does.
+ Don't allow these in Password:
    + common passwords (```apple```, ```password```, ```aaaaaaaaaaa```, etc.)
    + U+0000 (Null)
    + U+202e -> [explainxkcd.com](http://www.explainxkcd.com/wiki/index.php/1137:_RTL)
    + Depending to if you have character limits(ASCII,...) [don't allow other Unicodes](http://security.stackexchange.com/questions/5694/why-limit-passwords-to-ascii-printable-characters), too.
+ You can provide a third thing:
    + Use 2 factor Auth (SMS)
    + Second password (pass1, pass2)
    + Second username (known_username = what others see, unknown_username = for login)
    + Login with email (which you'll stop user from sharing that email in site -> It looks like paranoia, but some systems may need such a thing!)
