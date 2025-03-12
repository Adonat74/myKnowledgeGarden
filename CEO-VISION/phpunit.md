# PHPUnit utils 

## Different type of tests

|Test types|What they are for|
|-|-|
|Unit tests|Test functions, methods, and classes without requiring a database connection to run.|
|Kernel tests|PHPUnit-based tests with a bootstrapped kernel, and a minimal number of extensions enabled.|
|Functionnal tests|PHPUnit-based tests with a booted Drupal instance.|
|FunctionnalJavascript tests|PHPUnit-based tests that use Webdriver (Chromedriver) to perform tests of Javascript functionality.|


## Setting up phpunit

- ### core dev :

dl/activate drupal core dev dependencies : `composer require drupal/core-dev`

It will create  a phpunit binary at : `vendor/bin/phpunit`

- ### phpunit.xml.dist :

copy `core/phpunit.xml.dist` to `core/phpunit.xml`

it's a config file for phpunit


## Running the tests (units)

naviguate to the drupal project root : `cd /var/www/site`

the run : `./vendor/bin/phpunit -v -c ./core/phpunit.xml ./modules/custom/ceo_vision/tests/src/Unit/CeovisionControllerTest.php`












