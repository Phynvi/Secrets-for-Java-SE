This program allows a standard Java-SE platform to decode
[Secrets for Android](http://code.google.com/p/secrets-for-android/)
files.

# Compilation instructions
Run ``ant`` on the project's root directory.
You will need an internet connection, because the build will
download a cryptography provider library from
http://www.bouncycastle.org/java.html.
The executable jar will be placed in the ``lib`` directory.

# Execution
To decode an existing file run

``java -jar lib/secrets.jar`` _inputfile_ _outputfile_

Sadly the default installation of the Jav 6 Java runtime environment doesn't offer
cryptographic services, nor does it play particularly well with existing
providers.
If you install ``secrets.jar`` in another location you will need to
copy alongside the appropriate
[Legion of the Bouncy Castle](http://www.bouncycastle.org/)
crypto provider library ``bcprov-jdk....jar``.
Note that the JDK 7 seems to include the required cryptographic functionality out of the box.

Furthermore, to avoid an exceception
``java.security.InvalidKeyException: Illegal key size`` you must modify
your Java runtime installation to support strong cryptography.
For that download the _strong cryptography policy files_ from
the location where you downloaded your Java runtime environment
and install them according to the supplied instructions.
