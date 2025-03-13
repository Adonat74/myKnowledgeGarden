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



## Example tests simple pour le module ceo_vision

```php
<?php

namespace Drupal\Tests\ceo_vision\Unit;

use Drupal\Tests\UnitTestCase;
use Drupal\ceo_vision\Controller\CeovisionController;
use Drupal\Core\Render\RendererInterface;
use Symfony\Component\HttpFoundation\Response;



class CeovisionControllerTest extends UnitTestCase {
  
    public function testNewsletterRoute () {

        $controller = new CeovisionController();

        $this->assertEquals(['#theme' => 'ceo_vision_newsletter',], $controller->newsletter());
        $this->assertIsArray($controller->newsletter());
    }


    public function testNewsletter_blankRoute () {

        $renderer = $this->createMock(RendererInterface::class);
        $renderer->method('render')
            ->willReturn('<div>Rendered Content</div>');

        \Drupal::setContainer(
            new \Symfony\Component\DependencyInjection\ContainerBuilder()
        );
        \Drupal::getContainer()->set('renderer', $renderer);

        $controller = new CeovisionController();

        $response = $controller->newsletter_blank();

        $this->assertInstanceOf(Response::class, $response);
        $this->assertEquals($response->getContent(), '<div>Rendered Content</div>');
    }
}
```








