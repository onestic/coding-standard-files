# Onestic Coding Standard #
## php ##

Onestic php code will be bases on PSR-2 standards defined in https://www.php-fig.org/psr/psr-2/ and will be applied on Magento 1 developments by adapting ruleset defined in https://github.com/magento-ecg/coding-standard and customized in https://github.com/onestic/coding-standard

As there are some standards hard to validate by ruleset or needed to be open because of working with legacy code, some highlighted rules will be defined in this document:

### Control structures ###

Always open and close control structures with "{" and "}". Even for 1 line code blocks.

Avoid ":" and "end[XX];" for opening an closing if, while, for, ... structures.

Also avoid use of ternary operators for check conditions.

This also applies to phtml files

#### Non standard code ####

    <?php
    $exampleParam = $this->getParam('example');
    
    $exampleParam > 10 ? return false;
    
    $anotherExampleParam = $this->getParam('anotherExample');
    
    if ($anotherExampleParam > 10):
        $someVar    = false;
        $anotherVar = false;
    endif;
    
    $anotherOneExampleParam = $this->getParam('anotherOneExample');
    
    if ($anotherOneExampleParam > 10)
        $anotherOneVar = false;    
    
    
#### Standard code ####

    <?php
    $exampleParam = $this->getParam('example');
    
    if ($exampleParam > 10) {
        return false;
    }
    
    $anotherExampleParam = $this->getParam('anotherExample');
    
    if ($anotherExampleParam > 10) {
        $someVar    = false;
        $anotherVar = false;
    }
    
    $anotherOneExampleParam = $this->getParam('anotherOneExample');
    
    if ($anotherOneExampleParam > 10) {
        $anotherOneVar = false;
    }

    