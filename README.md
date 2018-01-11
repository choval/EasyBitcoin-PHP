EasyBitcoin-PHP
===============

A simple class for making calls to Bitcoin's API using PHP.

Tested against Bitcoin-ABC.

Getting Started
---------------
1. Include Bitcoin.php into your PHP script:

    ```php
    require('Bitcoin.php');
	# or 
    require('vendor/autoload.php');
    ```
2. Initialize Bitcoin connection/object:

    ```php
    $bitcoin = new \Bitcoin('username','password');
    ```

    Optionally, you can specify a host, port. Default is HTTP on localhost port 8332.

    ```php
    $bitcoin = new \Bitcoin('username','password','localhost','8332');
    ```

    If you wish to make an SSL connection you can set an optional CA certificate or leave blank
    ```php
    $bitcoin->setSSL('/full/path/to/mycertificate.cert');
    ````

3. Make calls to bitcoind as methods for your object. Examples:

    ```php
    $bitcoin->getinfo();
    $bitcoin->getrawtransaction('0e3e2357e806b6cdb1f70b54c3a3a17b6714ee1f0e68bebb44a74b1efd512098',1);
    $bitcoin->getblock('000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f');
    ```

Additional Info
---------------

* When a call fails for any reason, it will throw an exception.

