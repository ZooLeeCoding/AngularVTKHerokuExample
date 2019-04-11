# Angular7 - NodeJS Heroku Deploy

Az alábbi projekt mutatja be, hogyan tudunk egy Angularban megírt webalkalmazást NodeJS szerver segítségével futtatni Herokun. Az alábbi projekt mintaként, kiindulási alapként is használható. Lépések:

1. a deployolni kívánt Angular alkalmazás mappájában futtassuk le az `ng build --prod` parancsot, amely generál egy dist/project-name mappát, benne az alkalmazás bundle-be konvertált változatával
2. a dist/project-name tartalmát másoljuk be a frontend mappába úgy, hogy onnan előtte törlünk mindent
3. commitoljuk és pusholjuk fel az appot egy github repositoryba, esetleg a package.json és az app.json-ben szereplő leírásokat változtassuk meg (bár ez opcionális)
3. ha még nem tettük volna meg, regisztráljunk be Herokun, tegyük fel a gépre a Heroku CLI-t, lépjünk be e `heroku login` parancs segítségével
4. Hozzunk létre Herokun egy új projektet (ne a `heroku create` parancssori futtatásával, hanem a Heroku Dashboardon, amit login után látunk - new - Create new App)
5. a Deploy fülön deployment methodként válasszuk ki a githubot, kössük össze a Github fiókunkat a Heroku profilunkkal, majd adjuk meg, hogy pontosan melyik repositoryt, azon belül melyik branchet szeretnénk CI-vel rákötni erre a Heroku projektre
6. mentsük el a projektet, várjuk meg a pár másodpercet, amíg a Heroku végez az első deployyal, majd nyissuk meg az appot (a neve a <heroku-app-name>.heroku.com séma alapján fog generálódni)
7. a CI-nek köszönhetően valahányszor pusholunk a megfelelő githubos branchbe, a Heroku automatikusan újra fogja buildelni és deployolni a projektet
