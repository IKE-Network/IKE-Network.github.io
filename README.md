# IKE-Network.github.io

Published landing page for the IKE Network organization, served at
https://ike.network/.

This repository holds **rendered output only**. The source — Maven
project, AsciiDoc content, sentry-maven-skin configuration, and CSS
theme — lives in
[IKE-Network/ike-network-site](https://github.com/IKE-Network/ike-network-site).

To update the landing page, edit the source there, then run:

```bash
mvn clean site
```

and copy the contents of `target/site/` into the root of this
repository (preserving `CNAME`).
