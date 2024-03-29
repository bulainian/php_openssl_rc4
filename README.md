php_openssl_rc4
===============

php rc4 encrypted as openssl c
I wrote this RC4/ARCFOUR implementation in PHP - based on the original C source
code posted on usenet in 1994. The rc4() call itself is completely
self-contained, two other methods rc4_test() and rc4_benchmark() have been
provided for testing and are optional.

Examples:

1. Simple encryption & decryption

<?php
   require_once( "rc4.php" );
   $key = "0123456789abcdef";
   $plaintext = "Hello World!";
   $ciphertext = rc4( $key, $plaintext );
   $decrypted = rc4( $key, $ciphertext );
   echo $decrypted . " - " . $plaintext . "\n";
?>

2. Execute the tests and display the results

<?php
   require_once( "rc4tests.php" ); // Auto includes rc4.php
   echo rc4_tests();
?>

3. Execute the tests as benchmarks and display the results

<?php
   require_once( "rc4tests.php" ); // Auto includes rc4.php
   echo rc4_benchmark();
?>

http://cotdp.com/blog/2006/03/rc4-arcfour-implementation-in-php.html
I changed this rc4.php to use like the openssl c and has two interfaces:
RC4_set_key
RC4()
