Mirror debugging:

- Start http server in mirror folder: python -m http.server

- In manifest.json set "content_security_policy": "script-src 'self' 'unsafe-eval' http://localhost:8000/ https://ssl.google-analytics.com/  https://community.allmangasreader.com/ https://www.google.com/ https://platform.twitter.com/ https://www.facebook.com/ https://raw.githubusercontent.com/ https://rawgit.com/ ; object-src 'self'",

- In mgEntry.js change mirrors to localhost
    var amrc_repository = "http://localhost:8000/";
    var amrc_root = "http://localhost:8000/";
    var amrc_repository_backup = "http://localhost:8000/";

- In mgEntry.js change validURL to accept http

Force All Mirror reload:
- MgEntry.js in line 180 add true to if check of revisions
- MgEntry.js in line 484 add docache = false; to not use the cache while loading mirrors