
# Install grumphp - https://github.com/phpro/grumphp/blob/master/doc/installation/global.md

composer global require phpro/grumphp
composer global update phpro/grumphp

add
export PATH="$HOME/.composer/vendor/bin:$PATH"
export PATH="$HOME/.config/composer/vendor/bin:$PATH"
to .bashrc

# Install tasks - https://github.com/phpro/grumphp/blob/master/doc/tasks.md

- php7cc - https://github.com/phpro/grumphp/blob/master/doc/tasks/php7cc.md
composer global require --dev sstalle/php7cc

- php mess detector - https://github.com/phpro/grumphp/blob/master/doc/tasks/phpmd.md
composer global require --dev phpmd/phpmd

- php code sniffer - https://github.com/phpro/grumphp/blob/master/doc/tasks/phpcs.md
composer global require --dev squizlabs/php_codesniffer

composer global require --dev sebastian/phpcpd


# Commands - https://github.com/phpro/grumphp/blob/master/doc/commands.md

- Sniff commits
php ~/.composer/vendor/bin/grumphp git:init --config=~/coding-standard-files/grumphp/grumphp.yml
grumphp git:init --config=~/coding-standard-files/grumphp/grumphp.yml

or

php ~/.composer/vendor/bin/grumphp git:init
grumphp git:init
<!-- composer.json -->
{
  "extra": {
    "grumphp": {
      "config-default-path": "/~/coding-standard-files/grumphp/grumphp.yml"
    }
  }
}

- Stop sniffing commits
php ~/.composer/vendor/bin/grumphp git:deinit
grumphp git:deinit