# Onestic Coding Standard #
## php ##

Onestic php code will be bases on PSR-2 standards defined in https://www.php-fig.org/psr/psr-2/ and will be applied on Magento 1 developments by adapting ruleset defined in https://github.com/magento-ecg/coding-standard and customized in https://github.com/onestic/coding-standard

This rules will apply to php and phtml files.

As there are some standards hard to validate by ruleset or needed to be open because of working with legacy code, some highlighted rules will be defined in this document:

### Indenting ###

Code always be indented with white space, never with tab character.  
Indent and tab size will be 4 white spaces.

Max line size will be 120 chars.

### Definitions ###

Properties and functions should not be prefixed with a single underscore to indicate protected or private visibility.

Align consecutive assignments is optional for vars, array elements, etc.

Arrays definition will be in "modern" short way.  
In array declarations, each element will be in a line ended by comma char (",").

#### Non standard code ####

    <?php
    $someArray       = array('firstElement' => 'Z', 'secondElement' => 'Y', 'thirdElement' => 'X');
    $anotherArray    = array('firstElement' => 'Z');
    $anotherOneArray = ['firstElement' => 'ZZ', 'secondElement' => 'YY', 'thirdElement' => 'XX'];
    
#### Standard code ####

    <?php    
    $someArray = [
        'firstElement' => 'Z',
        'secondElement' => 'Y',
        'thirdElement' => 'X',
    ];    
    $anotherArray    = ['firstElement' => 'Z'];
    $anotherOneArray = [
        'firstElement'  => 'ZZ',
        'secondElement' => 'YY',
        'thirdElement'  => 'XX',
    ];


### Control structures ###

Control structures will always have a blank space after and before, except if a control structures is the first element of another structure.
 
Always open and close control structures with "{" and "}". Even for 1 line code blocks.

Avoid ":" and "end;" for opening an closing structures in php files. They're allowed in phtml files, but CS rules are no set yet and warnings are still showing.

Avoid use of ternary operators for check conditions.


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
    